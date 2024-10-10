<script>
     import { page } from '$app/stores';
     import { Footer, Navbar } from 'flowbite-svelte';
     import { NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
     $: activeUrl = $page.url.pathname;
     import "../app.css";
</script>

<svelte:head>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous">
<link href="https://fonts.googleapis.com/css2?family=Afacad+Flux:wght@100..1000&family=Afacad:ital,wght@0,400..700;1,400..700&display=swap" rel="stylesheet">
</svelte:head>

<div class="flex flex-col min-h-screen">
     <Navbar let:hidden let:toggle>
       <NavBrand href="/">
         <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">
           Jmdlvns
         </span>
       </NavBrand>
       <NavHamburger on:click={toggle} />
       <NavUl {activeUrl}>
         <NavLi href="/">Home</NavLi>
         <NavLi href="/Portfolio-page">Portfolio</NavLi>
         <NavLi href="/About-page">About</NavLi>
         <NavLi href="/Contact-page">Contact</NavLi>
       </NavUl>
     </Navbar>
   
     <main class="container mx-auto px-4 flex-grow">
       <slot></slot>
     </main>
   
     <Footer class="mt-auto">
       <div class="w-full text-center">
         <p>© {new Date().getFullYear()} JDV. All rights reserved.</p>
       </div>
     </Footer>
   </div>
