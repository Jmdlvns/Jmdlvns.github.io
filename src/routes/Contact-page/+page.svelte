<script>
    import { fade, fly, scale } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';
  
    let name = '';
    let email = '';
    let message = '';
    let formSubmitted = false;
  
    const contactInfo = [
      { type: 'Email', value: '202210413@gordoncollege.edu.ph', icon: 'fas fa-envelope', link: 'https://mail.google.com/' },
      { type: 'Facebook', value: 'Jim Dale', icon: 'fab fa-facebook', link: 'https://facebook.com/eladmij' },
      { type: 'Instagram', value: '@itsszdale', icon: 'fab fa-instagram', link: 'https://www.instagram.com/itsszdale/' }
    ];
  
    function handleSubmit() {
      // In a real application, you would send the form data to a server here
      console.log('Form submitted', { name, email, message });
      formSubmitted = true;
      setTimeout(() => {
        formSubmitted = false;
        name = '';
        email = '';
        message = '';
      }, 5000);
    }
  </script>
  
  <div class="container mx-auto px-4 py-12">
    <h1 class="text-4xl font-bold mb-8 text-center" in:fade>Contact Me</h1>
  
    <div class="max-w-4xl mx-auto bg-white rounded-lg shadow-md p-8" in:fly={{ y: 50, duration: 500 }}>
      <div class="grid md:grid-cols-2 gap-8">
        <div>
          <h2 class="text-2xl font-semibold mb-4">Get in Touch</h2>
          <p class="mb-6">
            I'd love to hear from you! Feel free to reach out through any of the following channels:
          </p>
  
          <div class="space-y-4">
            {#each contactInfo as info, i}
              <div class="flex items-center p-3 bg-light-gray rounded-lg" in:fly={{ x: -50, delay: i * 100 }}>
                <i class="{info.icon} text-2xl text-teal mr-4"></i>
                <div>
                  <h3 class="font-semibold">{info.type}</h3>
                  <a 
                    href={info.link} 
                    target="_blank" 
                    rel="noopener noreferrer" 
                    class="text-teal hover:underline"
                  >
                    {info.value}
                  </a>
                </div>
              </div>
            {/each}
          </div>
        </div>
  
        <div>
          <h2 class="text-2xl font-semibold mb-4">Send a Message</h2>
          <form on:submit|preventDefault={handleSubmit} class="space-y-4">
            <div>
              <label for="name" class="block mb-1 font-medium">Name</label>
              <input 
                type="text" 
                id="name" 
                bind:value={name} 
                required 
                class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-teal"
              />
            </div>
            <div>
              <label for="email" class="block mb-1 font-medium">Email</label>
              <input 
                type="email" 
                id="email" 
                bind:value={email} 
                required 
                class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-teal"
              />
            </div>
            <div>
              <label for="message" class="block mb-1 font-medium">Message</label>
              <textarea 
                id="message" 
                bind:value={message} 
                required 
                rows="4" 
                class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-teal"
              ></textarea>
            </div>
            <button 
              type="submit" 
              class="bg-teal text-black px-6 py-2 rounded-full font-semibold hover:bg-opacity-90 transition-all duration-300"
            >
              Send Message
            </button>
          </form>
        </div>
      </div>
  
      {#if formSubmitted}
        <div 
          class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50 z-50"
          in:fade={{ duration: 200 }}
          out:fade={{ duration: 200 }}
        >
          <div 
            class="bg-white p-8 rounded-lg shadow-lg text-center"
            in:scale={{ duration: 200, easing: quintOut }}
          >
            <i class="fas fa-check-circle text-5xl text-teal mb-4"></i>
            <h3 class="text-2xl font-semibold mb-2">Thank You!</h3>
            <p>Your message has been sent successfully.</p>
          </div>
        </div>
      {/if}
    </div>
  </div>
  
  <style>
    /* Any additional component-specific styles can be added here */
  </style>