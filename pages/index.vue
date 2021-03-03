<template>
  <div>
    <div class="container">
      <div class="card">
        <div class="border">
          <h1 class="title">
            Lista para Tudo
          </h1>
          <form class="add">
            <label>
              <input type="text" placeholder="Adicionar um item">
            </label>
            <button>+</button>
          </form>
          <Logo />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// export default {}
</script>

<style>
button {
  border: 2px solid #2ECC71;
  border-radius: 100%;
  padding-right: 10px;
  padding-left: 10px;
}

input {
  border: 2px solid #2ECC71;
  border-radius: 10px;
  padding-left: 15px;
}

.add {
  padding-top: 10px;
  padding-bottom: 15px;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.title {
  display: block;
  font-weight: 300;
  font-size: 25px;
  letter-spacing: 1px;
}

.card {
  padding-left: 15%;
  padding-right: 15%;
}

.border {
  border: 5px solid #2ECC71;
  padding: 1rem;
  border-radius: 10px;
}
</style>
