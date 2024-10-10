<script>
    import { fade, fly } from 'svelte/transition';
  
    const projects = [
      {
        title: 'Image Gallery',
        description: 'Image Gallery with uploads and user management',
        image: 'assets/image.png',
        technologies: ['Angular',],
        repo: 'https://github.com/Jmdlvns/Gmage'
      },
      {
        title: 'Weather-App',
        description: 'Weather app with location detection and user preference',
        image: 'assets/bg.png',
        technologies: ['Angular'],
        repo: 'https://github.com/Jmdlvns/weather-app'
      },
    ];
  </script>
  
  <div class="container mx-auto px-4 py-12">
    <h1 class="text-4xl font-bold mb-8 text-center" in:fade>My Projects</h1>
  
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each projects as project, i}
        <div in:fly={{ y: 50, delay: i * 150 }} class="bg-white rounded-lg shadow-md overflow-hidden">
          <img src={project.image} alt={project.title} class="w-full h-48 object-cover" />
          <div class="p-6">
            <h2 class="text-2xl font-semibold mb-2">{project.title}</h2>
            <p class="text-gray-600 mb-4">{project.description}</p>
            <div class="mb-4">
              <h3 class="font-semibold mb-2">Technologies:</h3>
              <div class="flex flex-wrap gap-2">
                {#each project.technologies as tech}
                  <span class="bg-teal text-gray px-2 py-1 rounded-full text-sm">{tech}</span>
                {/each}
              </div>
            </div>
            <div class="flex justify-between">
              <a href={project.repo} target="_blank" rel="noopener noreferrer" class="text-teal hover:underline">GitHub Repo</a>
            </div>
          </div>
        </div>
      {/each}
    </div>
  
    <div class="mt-16 text-center" in:fade={{ delay: 500 }}>
      <h2 class="text-2xl font-semibold mb-4">Let's Work Together</h2>
      <p class="mb-6">Interested in collaborating or have a project in mind? Get in touch!</p>
      <a href="/Contact-page" class="bg-coral text-black px-6 py-3 rounded-full text-lg font-semibold hover:bg-opacity-90 transition-all duration-300">
        Contact Me
      </a>
    </div>
  </div>