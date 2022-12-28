<script>
	import { count } from './stores.js';
  export let incrementValue = 1
  const increment = () => {
    count.update(n => n + incrementValue);
  }
</script>

<button on:click={increment}>
  +
</button>
