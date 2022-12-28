<script>
let contentKey = true;

function toggle() {
  contentKey = !contentKey;
}

let content = `<h2> Esse conteudo foi adicionado!</h2>
               <div class="inserted"><p>E esse</p><p>também!</p></div>`;

let content2 = `<h1 class="inserted"> Sou um componente diferente!</h1>`;

</script>

<main>
  <!-- Form de login-->
  {#if contentKey}
    <div class="container">{@html content}</div>
  {:else}
    <div>{@html content2}</div>
  {/if}
  <button on:click={toggle}>
    Trocar Elemento
  </button>
</main>

<style>
.container :global(.inserted) {
  color: red;
  font-weight: 600;
}
</style>
