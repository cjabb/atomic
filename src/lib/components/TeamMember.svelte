<script lang="ts">
    export let member: {
      name: string;
      role: string;
      image: string;
      github: string;
      linkedin: string;
      email: string;
      skills: string[];
    };
  </script>
  
  <div class="bg-gray-800 rounded-lg shadow-lg p-6 hover-illuminate">
    <img src={member.image} alt={member.name} class="w-32 h-32 rounded-full mx-auto mb-4 object-cover" />
    <h3 class="text-2xl font-semibold text-center">{member.name}</h3>
    <p class="text-center text-gray-400 mb-4">{member.role}</p>
    <div class="flex justify-center space-x-4 mb-4">
      <a href={member.github} class="text-gray-300 hover:text-white transition-colors">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-github"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
      </a>
      <a href={member.linkedin} class="text-gray-300 hover:text-white transition-colors">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-linkedin"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
      </a>
      <a href={`mailto:${member.email}`} class="text-gray-300 hover:text-white transition-colors">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-mail"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
      </a>
    </div>
    <div class="flex flex-wrap justify-center gap-2">
      {#each member.skills as skill}
        <span class="bg-blue-600 text-white text-sm px-3 py-1 rounded-full">
          {skill}
        </span>
      {/each}
    </div>
  </div>