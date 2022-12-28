<script>
  import { count } from './lib/stores.js';
  import Counter from './lib/Counter.svelte'
  import Multiply from './lib/Multiply.svelte'

  let countValue;

  count.subscribe(value => {
    countValue = value;
  });

  $: countExp = countValue.toExponential(2);

  let rockets = null;
  let space = null;
  function enableRockets() {
    rockets = `<h3> Dar força aos fogetes. </h3>`;
    document.getElementById('rockets').style.display = 'block';
  }

  function enableSpace() {
    space = `<h3> Dar força ao módulo espacial. </h3>`;
    document.getElementById('space').style.display = 'block';
  }
</script>

<main>
  <h1>Velocidade da nave: {countExp} m/s!</h1>
  {#if countValue < 100}
    <h3> A nave está aquecendo...</h3>
  {:else if countValue < 340}
    <h3> Estamos subindo!</h3>
  {:else if countValue < 3800}
    <h3> <button on:click={enableRockets}>Adicione força aos fogetes!</button> Estamos na velocidade do som!</h3>
  {:else if countValue < 3.33564e9}
    <h3> <button on:click={enableSpace}>Adicione força ao módulo espacial!</button> Estamos saindo da terra.</h3>
  {:else}
    <h3> Passamos a velocidade da luz!</h3>
  {/if}

  <div class="card">
    <h3> Adicionar gasolina. </h3>
    <Counter incrementValue={10}/>
  </div>
  <div class="card">
    <h3> Dar força ao reator. </h3>
    <Multiply multiplyValue={1.2}/>
  </div>
  <div class="card" id="rockets" style="display: none;">
    {@html rockets}
    <Multiply multiplyValue={1.5}/>
  </div>
  <div class="card" id="space" style="display: none;">
    {@html space}
    <Multiply multiplyValue={2.5}/>
  </div>
</main>

<style>
</style>
