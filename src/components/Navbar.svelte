<script>

    let drop = false;

    let showMenu = false;

    function toggleNavbar() {
        showMenu = !showMenu;
    }

    function toggle() {
        drop = !drop;
        console.log(drop);
    }
</script>

<nav class="flex bg-slate-100 justify-between items-center p-4">
    <img src="/Logo.webp" alt="logo" class="h-[3.5rem] w-[4rem]"/>
    <div class="hidden justify-center items-center lg:flex">
        <a href="/" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">Home</a>
        <a href="/about" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">About</a>
        <button on:click={toggle} class="flex flex-row pl-6 pr-4 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">
            <div class="text-maindark pr-4">hajj</div>
            {#if drop === false}
                <svg class="self-end" xmlns="http://www.w3.org/2000/svg" height="1rem" width="1rem" viewBox="0 0 1024 1024" version="1.1"><path d="M903.232 256l56.768 50.432L512 768 64 306.432 120.768 256 512 659.072z" fill="#000000"/></svg>    
            {:else}
                <svg class="self-end" xmlns="http://www.w3.org/2000/svg" width="1rem" height="1rem" viewBox="0 0 1024 1024" version="1.1"><path d="M903.232 768l56.768-50.432L512 256l-448 461.568 56.768 50.432L512 364.928z" fill="#000000"/></svg>
            {/if}
        </button>
        <ul class="p-2 absolute z-10 bottom-2/3 bg-slate-100 w-80 shadow bg-base-100 rounded-box" style:visibility={drop ? 'visible' : 'hidden'}>
			<li><a href="/" class="text-maindark">Packages</a></li>
			<li><a href="/hajj/facilities" class="text-maindark">Facilities</a></li>
            <li><a href="/hajj/tra" class="text-maindark">Training</a></li>
			<li><a href="/" class="text-maindark">FAQs</a></li>
		</ul>
        <a href="/umrah" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">Umrah</a>
        <a href="/" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 ml-1 mr-10 hover:ease-in hover:border-maindark hover:rounded-xl">Gallery</a>
        <a href="/contact" class="px-6 py-1 bg-yellow-600 rounded-full border-2 text-slate-100 border-slate-100 focus:text-maindark">Contact</a>
    </div>
    {#if showMenu === false}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <button on:click={toggleNavbar} class="lg:hidden cursor-pointer">
            <svg xmlns="http://www.w3.org/2000/svg"  fill="#000000" width="2rem" height="2rem" viewBox="0 0 1920 1920">
                <path d="M1920 1468.412v112.94H0v-112.94h1920Zm0-564.706v112.941H0V903.706h1920ZM1920 339v112.941H0V339h1920Z" fill-rule="evenodd"/>
            </svg>
        </button>
    {:else}
        <div class="flex flex-col lg:hidden justify-center">

            <button on:click={toggleNavbar} class="cursor-pointer self-end">
                <svg xmlns="http://www.w3.org/2000/svg" width="2rem" height="2rem" viewBox="0 0 24 24" fill="none">
                    <path d="M19 5L4.99998 19M5.00001 5L19 19" stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
               </svg>
            </button>
            <div class="items-center md:hidden flex flex-col self-start">
                <a href="/" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">Home</a>
                <a href="/about" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">About</a>
                <button on:click={toggle} class="flex flex-row pl-6 pr-4 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">
                    <div class="text-maindark pr-4">Hajj</div>
                    {#if drop === false}
                        <svg class="self-end" xmlns="http://www.w3.org/2000/svg" height="1rem" width="1rem" viewBox="0 0 1024 1024" version="1.1"><path d="M903.232 256l56.768 50.432L512 768 64 306.432 120.768 256 512 659.072z" fill="#000000"/></svg>    
                    {:else}
                        <svg class="self-end" xmlns="http://www.w3.org/2000/svg" width="1rem" height="1rem" viewBox="0 0 1024 1024" version="1.1"><path d="M903.232 768l56.768-50.432L512 256l-448 461.568 56.768 50.432L512 364.928z" fill="#000000"/></svg>
                        <div class="flex flex-col" style:visibility={drop ? 'visible' : 'hidden'}>
                            <a href="/about" class="text-maindark">Packages</a>
                            <a href="/hajj/facilities" class="text-maindark">Facilities</a>
                            <a href="/hajj/training" class="text-maindark">Training</a>
                            <a href="/hajj/FAQ" class="text-maindark">FAQs</a>
                        </div>
                    {/if}
                </button>
                <a href="/umrah" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">Umrah</a>
                <a href="/" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">Gallery</a>
                <a href="/" class="px-6 py-1 bg-yellow-600 rounded-full border-2 text-slate-100 border-slate-100 focus:text-maindark">Contact</a>
            </div>
        </div>
    {/if}
    
</nav>