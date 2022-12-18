<script>
  let emailLogin, passwordLogin;
  // Define uma função de POST


  
  async function postData(url = '', data = {}) {
      //  Função simulando funcionamento
      return new Promise((resolve) => {resolve("Usuário Cadastrado com Sucesso.")})
      //  Exemplo de função real:
      //  const response = await fetch(url, {
      //    method: 'POST',
      //    headers: {
      //      'Content-Type': 'application/json'
      //    },
      //    body: JSON.stringify(data)
      //  });
      //  return response.json();
  }

  // Define uma função que será ativada no click
  async function doLogin() {
    console.log(emailLogin, passwordLogin);
    postData('HTTP://localhost:3001/login', { email: emailLogin, password: passwordLogin })
      .then((data) => {
        console.log(data);
      });
  }
</script>

<main>
  <!-- Form de login-->
  <h1>Register</h1>
  <form class="form-group">
      <input bind:value={emailLogin} type="email" placeholder="Email">
      <input bind:value={passwordLogin} type="password" placeholder="Password">
      <button type="submit" class="btn btn-primary" on:click={doLogin}> Submit </button>
  </form>
</main>

<style>
</style>
