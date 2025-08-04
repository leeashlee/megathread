<script lang="ts">
    import * as Sidebar from "$lib/components/ui/sidebar/index.js";
    import * as Collapsible from "$lib/components/ui/collapsible/index.js";
    import MinusIcon from "@lucide/svelte/icons/minus";
    import PlusIcon from "@lucide/svelte/icons/plus";

    //Popular items,
    const populars = [
        {
            title: "About RVZ files",
            url: "/Populars/about-rvz-files",
        },
        {
            title: "Metroid",
            url: "/Populars/metroid",
        },
        {
            title: "Mario",
            url: "/Populars/mario",
        },
        {
            title: "Fire Emblem",
            url: "/Populars/fire-emblem",
        },
        {
            title: "The Legend of Zelda",
            url: "/Populars/zelda",
        },
        {
            title: "Pokemon",
            url: "/Populars/pokemon",
        },
        {
            title: "Persona",
            url: "/Populars/persona",
        },
        {
            title: "Super Smash Bros",
            url: "/Populars/super-smash-bros",
        },
        {
            title: "Xenoblade",
            url: "/Populars/xenoblade",
        },
    ];

    //Nintendo items,
    const Nintendo = [
        {
            title: "Nintendo Games",
            url: "/Nintendo/nintendo-games",
        },
        {
            title: "Nintendo DS",
            url: "/Nintendo/nintendo-ds",
        },
        {
            title: "Nintendo 3DS",
            url: "/Nintendo/nintendo-3ds",
        },
        {
            title: "Nintendo GameCube",
            url: "/Nintendo/nintendo-gamecube",
        },
        {
            title: "Nintendo Wii",
            url: "/Nintendo/nintendo-wii",
        },
        {
            title: "Nintendo Wii U",
            url: "/Nintendo/nintendo-wii-u",
        },
    ];

    //Sony items,
    const sony = [
        {
            title: "NoPayStation",
            url: "/Sony/nopaystation",
        },
        {
            title: "Sony Playstation",
            url: "/Sony/sony-playstation",
        },
        {
            title: "Sony Playstation 2",
            url: "/Sony/sony-playstation-2",
        },
        {
            title: "Sony Playstation Portable",
            url: "/Sony/sony-playstation-portable",
        },
        {
            title: "Sony Playstation 3",
            url: "/Sony/sony-playstation-3",
        },
        {
            title: "Sony Playstation Vita",
            url: "/Sony/sony-playstation-vita",
        },
    ];

    //Microsoft items,
    const microsoft = [
        {
            title: "Microsoft Xbox",
            url: "#microsoft-xbox",
        },
        {
            title: "Microsoft Xbox 360",
            url: "#microsoft-xbox-360",
        },
    ];

    //Sega items,
    const sega = [
        {
            title: "Sega Games",
            url: "#sega-games",
        },
        {
            title: "Sega Dreamcast",
            url: "#sega-dreamcast",
        },
        {
            title: "Sega Saturn",
            url: "#sega-saturn",
        },
        {
            title: "Sega CD",
            url: "#sega-cd",
        },
    ];

    // Retro & Arcade items,
    const retroArcade = [
        {
            title: "Retro Games",
            url: "#retro-games",
        },
        {
            title: "Arcade",
            url: "#arcade-games",
        },
    ];

    //PC items,
    const pc = [
        {
            title: "PC Games",
            url: "#pc-games",
        },
    ];

    // Miscellaneous items,
    const misc = [
        {
            title: "ROM Sets",
            url: "#rom-sets",
        },
        {
            title: "BIOS Files",
            url: "#bios-files",
        },
    ];
</script>

<Sidebar.Root collapsible="offcanvas">
    <Sidebar.Content>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Popular</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each populars as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Nintendo</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each Nintendo as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Sony</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each sony as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Microsoft</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each microsoft as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Sega</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each sega as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Retro & Arcade</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each retroArcade as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>PC</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each pc as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Miscellaneous</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each misc as item}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href={item.url} {...props}>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
    </Sidebar.Content>
</Sidebar.Root>
