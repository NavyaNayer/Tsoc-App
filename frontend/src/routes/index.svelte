<script>
    import { onMount } from 'svelte';
    import axios from 'axios';
  
    let data = '';
  
    onMount(async () => {
      try {
        const response = await axios.get('http://[::1]:3000/api/data');
        console.log('Response:', response); // Debugging line
        data = response.data;
      } catch (error) {
        console.error('Error fetching data:', error); // Debugging line
      }
    });
  </script>
  
  <main>
    <h1>{data}</h1>
  </main>
  
  