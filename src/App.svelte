<script>
  import { count } from './lib/stores.js';
  import Counter from './lib/Counter.svelte'
  import Multiply from './lib/Multiply.svelte'

  let countValue;

  count.subscribe(value => {
    countValue = value;
  });
</script>

<main>
  <h1>Valor atual: {countValue}!</h1>

  <div class="card">
    <Counter incrementValue={3}/>
  </div>
  <div class="card">
    <Multiply multiplyValue={3}/>
  </div>
</main>

<style>
</style>
