<script lang="ts">
     import { Button } from 'flowbite-svelte'
   </script>
   
   <div class="container mx-auto text-center py-16 px-4">
     <section class="space-y-8">
       <div class="animate-fade-in">
         <img 
           src="assets/profile.jpg" 
           alt="Profile" 
           class="w-40 h-40 rounded-full mx-auto object-cover border-4 border-gray-300 shadow-lg transition-transform duration-300 hover:scale-105"
         />
       </div>
   
       <header class="space-y-6 animate-fade-in-down">
         <p class="text-lg text-gray-600">
           Hello! I'm <span class="text-primary font-semibold">Viñas, Jim Dale V.</span>, a student developer passionate about creating innovative solutions. 
           Over the past three years, I've honed my skills in software development, web applications, and algorithm design. This portfolio is a reflection of my 
           journey, growth, and projects that showcase my dedication to learning and innovation.
         </p>
         <p class="text-lg text-gray-600">
           Each project represents a step in my learning curve—from small apps to complex systems—highlighting my diverse skill set in problem-solving and coding.
         </p>
         <p class="text-lg text-gray-600">
           Feel free to explore my work and learn more about me. If you have any questions or want to collaborate, don't hesitate to reach out!
         </p>
       </header>
     </section>
   </div>
   
   <style lang="postcss">
     @keyframes fade-in {
       from { opacity: 0; }
       to { opacity: 1; }
     }
   
     @keyframes fade-in-down {
       from { opacity: 0; transform: translateY(-20px); }
       to { opacity: 1; transform: translateY(0); }
     }
   
     .animate-fade-in {
       animation: fade-in 1s ease-out;
     }
   
     .animate-fade-in-down {
       animation: fade-in-down 1s ease-out;
     }
   </style>