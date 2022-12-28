<script>
	import { count } from './stores.js';
  export let multiplyValue = 2
  const multiply = () => {
    count.update(n => n * multiplyValue);
  }
</script>

<button on:click={multiply}>
  x
</button>
