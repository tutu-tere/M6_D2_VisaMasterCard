<script>
export default {
  name: 'CardVisa',
  data() {
    return {
      user: {
        tituloTarjeta: '',
        chipSrc: './img/chip.png',
        numero: '',
        fechaExpiracion: '',
        propietario: '',
        visaSrc: './img/visa.png'
      }
    }
  }
}
</script>

<template>
  <div id="app">
    <form>
      <div>
        <label for="user-titulotarjeta">Título de la tarjeta: </label>
        <input
          id="user-titulotarjeta"
          class="form-control"
          type="text"
          v-model="user.tituloTarjeta"
        />
      </div>

      <div>
        <label for="user-chipSrc">Chip SRC: </label>
        <input id="user-chipSrc" class="form-control" type="text" v-model="user.chipSrc" />
      </div>

      <div>
        <label for="user-numero">Número: </label>
        <input id="user-numero" class="form-control" type="number" v-model="user.numero" />
      </div>

      <div>
        <label for="user-fechaExpiracion">Fecha de expiración: </label>
        <input
          id="user-fechaExpiracion"
          class="form-control"
          type="date"
          v-model="user.fechaExpiracion"
        />
      </div>

      <div>
        <label for="user-propietario">Propietario: </label>
        <input id="user-propietario" class="form-control" type="text" v-model="user.propietario" />
      </div>

      <div>
        <label for="user-tipoTarjeta">Tipo de tarjeta SRC: </label>
        <input id="user-tipoTarjeta" class="form-control" type="text" v-model="user.visaSrc" />
      </div>
    </form>

    <div class="carnet">
      <h3>{{ user.tituloTarjeta }}</h3>
      <img width="40" :src="user.chipSrc" alt="Chip" />
      <div>
        <h2>{{ user.numero }}</h2>
        <span
          >Fecha Exp: <b>{{ user.fechaExpiracion }}</b></span
        >
      </div>
      <footer>
        <span>{{ user.propietario }}</span>
        <img :src="user.visaSrc" width="60" alt="Visa" />
      </footer>
    </div>
  </div>
</template>

<style scoped>
#app {
  display: flex;
  gap: 40px;
}
form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}
form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.carnet {
  width: 400px;
  height: 230px;
  background: #1c1a1e;
  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>
