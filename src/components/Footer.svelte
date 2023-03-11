<script lang="ts">
    let Name: string = '';
    let Email: string = '';
    let Message: string = '';
    let result = null;

    async function submitForm() {
      console.log("jsks");
        const Msg = {
            name: Name,
            email: Email,
            message: Message
        };
        const res = await fetch('https://idxmkziy70.execute-api.ap-south-1.amazonaws.com/Stage/msg', 
        { 
         method: 'POST',
          body: JSON.stringify(Msg)        
        });
        const json = await res.json()
        result = JSON.stringify(json)
        console.log(result);
        console.log(JSON.stringify(Msg));
    }
</script>

<footer class="bg-gray-800">
    <!-- Flex Container -->
    <div
      class="container flex flex-col-reverse justify-between px-6 py-10 mx-auto space-y-8 md:flex-row md:space-y-0"
    >
      <!-- Logo and social links container -->
      <div
        class="flex flex-col-reverse items-center justify-between space-y-12 md:flex-col md:space-y-0 md:items-start"
      >
        <div class="mx-auto my-6 text-center text-white md:hidden">
          Copyright &copy; 2022, All Rights Reserved
        </div>
        <!-- Logo -->
        <div class="flex flex-row">
          <img src="/logo.png" class="h-[3rem] w-[3.5rem]" alt="" />
          <div class="flex flex-col">
            <h2 class="text-white font-extrabold text-3xl">
                EMAD
              </h2>
              <p class="text-white text-xs">TRAVEL AND TOURS</p>
          </div>
        </div>
        <!-- Social Links Container -->
        <div class="flex justify-center space-x-4">
          <!-- Link 1 -->
          <a href="/">
            <img src="/icon-facebook.svg" alt="" class="h-8" />
          </a>
          <!-- Link 2 -->
          <a href="/">
            <img src="/icon-youtube.svg" alt="" class="h-8" />
          </a>
          <!-- Link 3 -->
          <a href="/">
            <img src="/icon-twitter.svg" alt="" class="h-8" />
          </a>
          <!-- Link 4 -->
          <a href="/">
            <img src="/icon-pinterest.svg" alt="" class="h-8" />
          </a>
          <!-- Link 5 -->
          <a href="/">
            <img src="/icon-instagram.svg" alt="" class="h-8" />
          </a>
        </div>
      </div>
      <!-- List Container -->
      <div class="flex justify-around space-x-24">
        <div class="flex flex-col space-y-3 text-white">
          <a href="/" class="hover:text-brightRed">Home</a>
          <a href="/" class="hover:text-brightRed">Pricing</a>
          <a href="/" class="hover:text-brightRed">Products</a>
          <a href="/" class="hover:text-brightRed">About</a>
        </div>
        <div class="flex flex-col space-y-3 text-white">
          <a href="/" class="hover:text-brightRed">Careers</a>
          <a href="/" class="hover:text-brightRed">Community</a>
          <a href="/" class="hover:text-brightRed">Privacy Policy</a>
        </div>
      </div>

      <!-- Input Container -->
      <div class="flex flex-col justify-between mx-4">
        <div class="relative">
          <div class="absolute -inset-1 bg-gradient-to-r from-pink-600 to-purple-500 rounded-lg blur opacity-75 hover:opacity-100 
          transition duration-600 hover:duration-200 animate-tilt">
          </div>
          <form on:submit|preventDefault={submitForm} class="relative backdrop-blur-md bg-gray-900 rounded-lg p-5">
            <h1 class="text-slate-200 font-extrabold text-5xl pb-8">Send a message</h1>
            <div class="form-group mb-6">
              <input id="name" bind:value={Name} type="text" required class="form-control block
              w-full
              px-3
              py-1.5
              text-base
              font-normal
              text-gray-700
              bg-white bg-clip-padding
              border border-solid border-gray-300
              rounded
              transition
              ease-in-out
              m-0
              focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none" 
                placeholder="Name">
            </div>
            <div class="form-group mb-6">
              <input id="email" bind:value={Email} type="email" required class="form-control block
              w-full
              px-3
              py-1.5
              text-base
              font-normal
              text-gray-700
              bg-white bg-clip-padding
              border border-solid border-gray-300
              rounded
              transition
              ease-in-out
              m-0
              focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none" 
                placeholder="Email address">
            </div>
            <div class="form-group mb-6">
              <textarea id="message" bind:value={Message} class="
              form-control
              block
              w-full
              px-3
              py-1.5
              text-base
              font-normal
              text-gray-700
              bg-white bg-clip-padding
              border border-solid border-gray-300
              rounded
              transition
              ease-in-out
              m-0
              focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none
            " required rows="3" placeholder="Message"></textarea>
            </div>
            <button type="submit" class="
            w-full
            px-6
            py-2.5
            bg-blue-600
            text-white
            font-medium
            text-xs
            leading-tight
            uppercase
            rounded
            shadow-md
            hover:bg-blue-700 hover:shadow-lg
            focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0
            active:bg-blue-800 active:shadow-lg
            transition
            duration-150
            ease-in-out">Send</button>
          </form>
        </div>
       
        <div class="hidden mt-5 text-white md:block">
          Copyright &copy; 2022, All Rights Reserved
        </div>
      </div>
    </div>
  </footer>
  
  <style>  
 
  </style>