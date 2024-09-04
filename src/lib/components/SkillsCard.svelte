<script lang="ts">
    export let skills: string[];
  </script>
  
  <div class="bg-gray-800 rounded-lg shadow-lg p-6 hover-illuminate">
    <p class="text-lg mb-4 text-gray-300">
      Together, we bring a comprehensive skill set to tackle any project:
    </p>
    <div class="flex flex-wrap gap-2">
      {#each skills as skill}
        <span class="bg-blue-600 text-white px-3 py-1 rounded-full text-sm">
          {skill}
        </span>
      {/each}
    </div>
  </div>