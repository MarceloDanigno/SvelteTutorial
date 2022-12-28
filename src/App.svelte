<script>
  import svelteLogo from './assets/svelte.svg'
  import Counter from './lib/Counter.svelte'
</script>

<main>
  <h1>Props!</h1>

  <h2> Componente normal: </h2>
  <div class="card">
    <Counter />
  </div>

  <h2> Definindo posição inicial: </h2>
  <div class="card">
    <Counter count={100}/>
  </div>

  <h2> Definindo posição inicial e incremento: </h2>
  <div class="card">
    <Counter count={3} incrementValue={3}/>
  </div>

</main>

<style>
</style>
