<script>
  export let count = 0
  export let incrementValue = 1
  const increment = () => {
    count += incrementValue
  }
</script>

<button on:click={increment}>
  count is {count}
</button>
