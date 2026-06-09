
    <script lang="ts">
        // Import TailwindCSS with DaisyUI plugin
        import "./layout.css";
        
        // Page change animation
        import FadeTransition from "./FadeTransition.svelte";
        import { page } from "$app/state";
        
        const { children } = $props();
    </script>
    
    <svelte:head>
        <link rel="icon" href="/site-assets/47-46725-prodovolstvennoe_zerno-nebo-pole-zakat-semeystvo_travy-192.jpg" />
        <title>Self promotial page</title>
    </svelte:head>
    
    <!-- Navigation bar -->
    <header class="sticky top-0 z-50  w-full">
  <nav class="w-full grid grid-cols-[1fr_auto] items-center gap-4 rounded-none border border-base-content/10 bg-base-100 px-4 py-3 shadow-sm shadow-base-content/5 lg:grid-cols-[1fr_auto_1fr]">
    <a href="/" class="flex min-w-0 items-center gap-3 text-lg font-black tracking-[-0.03em] text-base-content">
      <span class="flex h-9 w-9 shrink-0 overflow-hidden rounded-xl border border-base-content/10 bg-base-200"><img src="/site-assets/47-46725-prodovolstvennoe_zerno-nebo-pole-zakat-semeystvo_travy-192.jpg" alt="" class="h-full w-full object-cover"></span>
      <span class="truncate">Self promotial page</span>
    </a>
    <ul class="menu menu-horizontal hidden flex-nowrap gap-2 p-0 lg:flex [&>li>a]:rounded-none [&>li>a]:border-b-2 [&>li>a]:border-transparent [&>li>a]:bg-transparent [&>li>a]:px-2 [&>li>a]:py-1 [&>li>a]:text-xs [&>li>a]:font-bold [&>li>a]:uppercase [&>li>a]:tracking-[0.18em] [&>li>a]:text-base-content/50 [&>li>a:hover]:border-primary [&>li>a:hover]:text-base-content">
      
    <li><a href="/About Us">About Us</a></li>
    </ul>
    <div class="flex justify-end">
      <a class="btn btn-primary btn-sm rounded-none px-5 uppercase tracking-widest whitespace-nowrap" href="/Home">Home</a>
    </div>
  </nav>
</header>
    
    <!-- Main content -->
    <FadeTransition key={page.url.pathname} hash={page.url.hash}>
        <div class=" mt-0 w-full flex flex-col gap-3 min-h-screen mb-24 ">
            {@render children()}
        </div>
    </FadeTransition>
    
    <!-- Footer -->
    <footer class=" border-t border-base-content/10 bg-base-100 px-5 py-8 text-base-content">
  <div class="w-full flex flex-col gap-6 md:flex-row md:items-center md:justify-between">
    <div class="flex min-w-0 items-center gap-3">
      <span class="flex h-10 w-10 shrink-0 overflow-hidden rounded-xl border border-base-content/10 bg-base-200"><img src="/site-assets/47-46725-prodovolstvennoe_zerno-nebo-pole-zakat-semeystvo_travy-192.jpg" alt="" class="h-full w-full object-cover"></span>
      <div class="min-w-0">
        <p class="truncate text-base font-black tracking-tight">Self promotial page</p>
        <p class="text-sm text-base-content/60">Copyright &copy; 2026 - All rights reserved by Self promotial page</p>
      </div>
    </div>
    <div class="flex flex-col gap-3 md:items-end">
      <nav class="flex flex-wrap items-center gap-x-5 gap-y-2 text-sm [&>a]:text-base-content/65 [&>a]:transition-colors [&>a:hover]:text-primary">
    <a class="font-semibold text-base-content hover:text-primary" href="/Home">Home</a>
    <a href="/About Us">About Us</a>
  </nav>
      
    </div>
  </div>
</footer>
    