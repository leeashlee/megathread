<script lang="ts">
    import "../app.css";
    import { ModeWatcher } from "mode-watcher";
    import * as NavigationMenu from "$lib/components/ui/navigation-menu/index.js";
    import { cn } from "$lib/utils.js";
    import NavigationMenuTrigger, {
        navigationMenuTriggerStyle,
    } from "$lib/components/ui/navigation-menu/navigation-menu-trigger.svelte";
    import type { HTMLAttributes } from "svelte/elements";
    import NavigationMenuItem from "$lib/components/ui/navigation-menu/navigation-menu-item.svelte";
    const components: { title: string; href: string; description: string }[] = [
        {
            title: "Alert Dialog",
            href: "/docs/components/alert-dialog",
            description:
                "A modal dialog that interrupts the user with important content and expects a response.",
        },
        {
            title: "Hover Card",
            href: "/docs/components/hover-card",
            description:
                "For sighted users to preview content available behind a link.",
        },
        {
            title: "Progress",
            href: "/docs/components/progress",
            description:
                "Displays an indicator showing the completion progress of a task, typically displayed as a progress bar.",
        },
        {
            title: "Scroll-area",
            href: "/docs/components/scroll-area",
            description: "Visually or semantically separates content.",
        },
        {
            title: "Tabs",
            href: "/docs/components/tabs",
            description:
                "A set of layered sections of content—known as tab panels—that are displayed one at a time.",
        },
        {
            title: "Tooltip",
            href: "/docs/components/tooltip",
            description:
                "A popup that displays information related to an element when the element receives keyboard focus or the mouse hovers over it.",
        },
    ];

    type ListItemProps = HTMLAttributes<HTMLAnchorElement> & {
        title: string;
        href: string;
        content: string;
    };
    import { Button } from "$lib/components/ui/button/index.js";
    import { Separator } from "$lib/components/ui/separator/index.js";
    import SunIcon from "@lucide/svelte/icons/sun";
    import MoonIcon from "@lucide/svelte/icons/moon";
    import { toggleMode } from "mode-watcher";
    import * as Sidebar from "$lib/components/ui/sidebar/index.js";
    import AppSidebar from "$lib/components/app-sidebar.svelte";

    let { children } = $props();
</script>

{#snippet ListItem({
    title,
    content,
    href,
    class: className,
    ...restProps
}: ListItemProps)}
    <li>
        <NavigationMenu.Link>
            {#snippet child()}
                <a
                    {href}
                    class={cn(
                        "hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors",
                        className,
                    )}
                    {...restProps}
                >
                    <div class="text-sm font-medium leading-none">{title}</div>
                    <p
                        class="text-muted-foreground line-clamp-2 text-sm leading-snug"
                    >
                        {content}
                    </p>
                </a>
            {/snippet}
        </NavigationMenu.Link>
    </li>
{/snippet}

<div class="mx-8 my-4 space-y-8 md:mx-16 lg:mx-24 xl:mx-32 bg-background">
    <div class="flex justify-end sticky top-0 bg-background">
        <NavigationMenu.Root viewport={false}>
            <NavigationMenu.List>
                <NavigationMenuItem></NavigationMenuItem>
                <NavigationMenuItem>
                    <Button variant="ghost" href="/">/r/Roms Megathread</Button>
                </NavigationMenuItem>
                <Button onclick={toggleMode} variant="outline" size="icon">
                    <SunIcon
                        class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 !transition-all dark:-rotate-90 dark:scale-0"
                    />
                    <MoonIcon
                        class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 !transition-all dark:rotate-0 dark:scale-100"
                    />
                    <span class="sr-only">Toggle theme</span>
                </Button>
            </NavigationMenu.List>
        </NavigationMenu.Root>
    </div>
    <Sidebar.Provider>
        <AppSidebar />
        <main>
            <Sidebar.Trigger />
            {@render children?.()}
        </main>
    </Sidebar.Provider>
    <ModeWatcher />
</div>
