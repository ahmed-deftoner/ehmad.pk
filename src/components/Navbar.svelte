<script>
    let drop = false;

    function toggle() {
        drop = !drop;
        console.log(drop);
    }
</script>

<nav class="flex bg-slate-100 justify-between items-center p-4">
    <img src="/logo.webp" alt="logo" class="h-[3rem] w-[3.5rem]"/>
    <div class="hidden justify-center items-center lg:flex">
        <a href="/" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">Home</a>
        <a href="/about" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">About</a>
        <button on:click={toggle} class="flex flex-row pl-6 pr-4 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">
            <div class="text-maindark pr-4">Hajj</div>
            {#if drop === false}
                <svg class="self-end" xmlns="http://www.w3.org/2000/svg" height="1rem" width="1rem" viewBox="0 0 1024 1024" version="1.1"><path d="M903.232 256l56.768 50.432L512 768 64 306.432 120.768 256 512 659.072z" fill="#000000"/></svg>    
            {:else}
                <svg class="self-end" xmlns="http://www.w3.org/2000/svg" width="1rem" height="1rem" viewBox="0 0 1024 1024" version="1.1"><path d="M903.232 768l56.768-50.432L512 256l-448 461.568 56.768 50.432L512 364.928z" fill="#000000"/></svg>
            {/if}
        </button>
        <ul class="p-2 absolute z-10 bottom-2/3 bg-slate-100 w-80 shadow bg-base-100 rounded-box" style:visibility={drop ? 'visible' : 'hidden'}>
			<li><a href="/" class="text-maindark">Item 1</a></li>
			<li><a href="/" class="text-maindark">Item 2</a></li>
            <li><a href="/" class="text-maindark">Item 1</a></li>
			<li><a href="/" class="text-maindark">Item 2</a></li>
		</ul>
        <a href="/" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 mx-1 hover:ease-in hover:border-maindark hover:rounded-xl">Umrah</a>
        <a href="/" class="text-maindark px-6 py-2 border-2 border-transparent transition duration-150 ml-1 mr-10 hover:ease-in hover:border-maindark hover:rounded-xl">Gallery</a>
        <a href="/" class="px-6 py-1 bg-yellow-600 rounded-full border-2 text-slate-100 border-slate-100 focus:text-maindark">Contact</a>
    </div>
    <div class="flex lg:hidden">
        <div class="space-y-2">
            <span class="block w-8 h-0.5 bg-maindark animate-pulse"></span>
            <span class="block w-8 h-0.5 bg-maindark animate-pulse"></span>
            <span class="block w-8 h-0.5 bg-maindark animate-pulse"></span>
        </div>
    </div>
</nav>