<script>
  import { onMount } from 'svelte';
  import axios from 'axios'; // Assuming you're using axios for HTTP requests
  
  let repos = [];

  onMount(async () => {
    try {
      const response = await axios.get('https://api.github.com/orgs/larsylab-org/repos');
      repos = response.data;
    } catch (error) {
      console.error('Error fetching repositories:', error);
    }
  });
</script>

{#if repos.length > 0}
  <div class="flex flex-col xl:items-start items-center xl:px-40 px-3 md:pb-20 pb-4">
    <h1 in:fly={{ duration: 850, y: 80 }}>Projects</h1>
    <div class="flex gap-5 flex-wrap" in:fly={{ duration: 850, y: 80, delay: 200 }}>
      {#each repos as repo}
        <div class="max-w-xs rounded overflow-hidden shadow-lg">
          <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">{repo.name}</div>
            <p class="text-gray-700 text-base">
              {repo.description ? repo.description : 'No description available'}
            </p>
          </div>
          <div class="px-6 pt-4 pb-2">
            <a href={repo.html_url} target="_blank" rel="noopener noreferrer" class="text-blue-500 hover:text-blue-700">View on GitHub</a>
          </div>
        </div>
      {/each}
    </div>
    <div class="relative mt-5" in:fly={{ duration: 850, y: 80, delay: 300 }}>
      <Button text="Return" link="/" delay={150}/>
    </div>
  </div>
{:else}
  <p>Loading...</p>
{/if}
