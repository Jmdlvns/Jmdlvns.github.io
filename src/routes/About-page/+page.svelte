<script>
    import { fade, fly } from 'svelte/transition';
  
    const skills = [
      { name: 'Svelte'},
      { name: 'Python'},
      { name: 'Algorithms'},
      { name: 'Web Development'},
      { name: 'Angular'},
    ];
  
    const education = [
      { year: '2022 - Present', degree: 'Bachelor of Science in Computer Science', school: 'Gordon College' },
      { year: '2020 - 2022', degree: 'TVL-ICT', school: 'Columban College' },
    ];
  </script>
  
  <div class="container mx-auto px-4 py-12">
    <h1 class="text-4xl font-bold mb-8 text-center" in:fade>About Me</h1>
  
    <div class="max-w-3xl mx-auto space-y-12">
      <section in:fade>
        <h2 class="text-2xl font-semibold mb-4">Who I Am</h2>
        <p class="text-lg">
          I'm Jim Dale Viñas, a passionate student developer. I love creating innovative web solutions and deriving insights from complex datasets. My journey in tech is driven by curiosity and a desire to make a positive impact through code.
        </p>
      </section>
  
      <section>
        <h2 class="text-2xl font-semibold mb-4">Skills</h2>
        <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
          {#each skills as skill, i}
            <div in:fly={{ y: 50, delay: i * 100 }} class="bg-white p-4 rounded-lg shadow-md text-center">
              <p>{skill.name}</p>
            </div>
          {/each}
        </div>
      </section>
  
      <section in:fade>
        <h2 class="text-2xl font-semibold mb-4">Education</h2>
        <div class="space-y-4">
          {#each education as edu}
            <div class="bg-white p-4 rounded-lg shadow-md">
              <p class="font-semibold">{edu.year}</p>
              <p class="text-lg">{edu.degree}</p>
              <p class="text-gray-600">{edu.school}</p>
            </div>
          {/each}
        </div>
      </section>
  
      <section in:fade>
        <h2 class="text-2xl font-semibold mb-4">Interests</h2>
        <p class="text-lg">
          Beyond coding, I'm passionate about hiking, games, reading sci-fi novels. I believe in continuous learning and staying updated with the latest tech trends.
        </p>
      </section>
    </div>
  </div>