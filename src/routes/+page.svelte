<script lang="ts">
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

<NavigationMenu.Root viewport={false}>
    <NavigationMenu.List>
        <NavigationMenuItem>
            <Button variant="ghost" href="/">/r/Roms Megathread</Button>
        </NavigationMenuItem>
        <NavigationMenu.Item>
            <NavigationMenu.Trigger>Popular</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#about-rvz-files"
                            >About RVZ files</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#metroid"
                            >Metroid</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#mario"
                            >Mario</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#fire-emblem"
                            >Fire Emblem</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#pokemon"
                            >Pokemon</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#persona"
                            >Persona</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#zelda"
                            >Zelda</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#super-smash-bros"
                            >Super Smash Bros</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#xenoblade"
                            >Xenoblade</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
            <NavigationMenu.Trigger>Nintendo</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#nintendo-games"
                            >Nintendo Games</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#nintendo-ds"
                            >Nintendo DS</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#nintendo-3ds"
                            >Nintendo 3DS</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#nintendo-gamecube"
                            >Nintendo GameCube</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#nintendo-wii"
                            >Nintendo Wii</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#nintendo-wii-u"
                            >Nintendo Wii U</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
            <NavigationMenu.Trigger>Sony</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#no-pay-station"
                            >NoPayStation</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#sony-playstation"
                            >Sony Playstation</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#sony-playstation-2"
                            >Sony Playstation 2</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#sony-playstation-portable"
                            >Sony Playstation Portable</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#sony-playstation-3"
                            >Sony Playstation 3</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#sony-playstation-vita"
                            >Sony Playstation Vita</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
            <NavigationMenu.Trigger>Microsoft</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#microsoft-xbox"
                            >Microsoft Xbox</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#microsoft-xbox-360"
                            >Microsoft Xbox 360</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
            <NavigationMenu.Trigger>Sega</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#sega-games"
                            >SEGA Games</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#sega-dreamcast"
                            >Sega Dreamcast</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#sega-saturn"
                            >Sega Saturn</NavigationMenu.Link
                        >ֿ
                        <NavigationMenu.Link href="#sega-cd"
                            >Sega CD</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
            <NavigationMenu.Trigger>Retro & Arcade</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#retro-games"
                            >Retro Games</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#arcade-games"
                            >Arcade</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
            <NavigationMenu.Trigger>PC</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#pc-games"
                            >PC Games</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
            <NavigationMenu.Trigger>Miscellaneous</NavigationMenu.Trigger>
            <NavigationMenu.Content>
                <ul class="grid w-[200px] gap-4 p-2">
                    <li>
                        <NavigationMenu.Link href="#rom-sets"
                            >ROM Sets</NavigationMenu.Link
                        >
                        <NavigationMenu.Link href="#bios-files"
                            >BIOS Files</NavigationMenu.Link
                        >
                    </li>
                </ul>
            </NavigationMenu.Content>
        </NavigationMenu.Item>
    </NavigationMenu.List>
</NavigationMenu.Root>
<Separator />
