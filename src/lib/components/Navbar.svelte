<script lang="ts">
    import Logo from './Logo.svelte';
  </script>
  
  <nav class="bg-gray-800 p-4 sticky top-0 z-10">
    <div class="container mx-auto flex justify-between items-center">
      <Logo />
      <ul class="flex space-x-6">
        <li><a href="#hero" class="hover:text-blue-400 transition-colors">Home</a></li>
        <li><a href="#team" class="hover:text-blue-400 transition-colors">Team</a></li>
        <li><a href="#projects" class="hover:text-blue-400 transition-colors">Projects</a></li>
        <li><a href="#skills" class="hover:text-blue-400 transition-colors">Skills</a></li>
      </ul>
    </div>
  </nav>