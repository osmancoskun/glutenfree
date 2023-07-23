<script>
    import {
        Navbar,
        NavBrand,
        NavLi,
        NavUl,
        NavHamburger,
        DarkMode,
    } from "flowbite-svelte";
    import Wheat from "$lib/assets/wheat.svg";
</script>

<Navbar let:hidden let:toggle rounded color="form">
    <NavBrand href="/">
        <img src={Wheat} class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" />
        <span
            class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"
            >Glutensiz Hayat</span
        >
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <div class="flex">
        <NavUl {hidden}>
            <NavLi href="/" active={true}>Home</NavLi>
            <NavLi href="/about">About</NavLi>
            <NavLi href="/services">Services</NavLi>
            <NavLi href="/pricing">Pricing</NavLi>
            <NavLi href="/contact">Contact</NavLi>
        </NavUl>
        <DarkMode />
    </div>
</Navbar>
