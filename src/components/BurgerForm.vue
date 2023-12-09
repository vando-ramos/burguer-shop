<template>
  <div>
    <div>
      <form id="burger-form">
        <div class="input-container">
          <label for="name">Customer Name</label>
          <input type="text" id="name" name="name" v-model="name" placeholder="Enter Your Name">
        </div>
        <div class="input-container">
          <label for="bread">Choose the Bread</label>
          <select name="bread" id="bread" v-model="bread">
            <option value="">Choose a Bread:</option>
            <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">{{ pao.tipo }}</option>
          </select>          
        </div>
        <div class="input-container">
          <label for="meat">Choose the Meat</label>
          <select name="meat" id="meat" v-model="meat">
            <option value="">Choose a Meat:</option>
            <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">{{ carne.tipo }}</option>
          </select>          
        </div>

        <div id="optional-container" class="input-container">
          <label id="optional-title" for="optional">Choose Optional</label>
          <div class="checkbox-container" v-for="opcional in opcionaisData" :key="opcional.id">
            <input type="checkbox" name="optional" v-model="optional" :value="opcional.tipo">
            <span>{{ opcional.tipo }}</span>
          </div>
        </div>

        <div class="input-container">
          <input type="submit" class="submit-btn" value="Create Burger">
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BurgerForm',
  data() {
    return {
      paes: null,
      carnes: null,
      opcionaisData: null,
      nome: null,
      pao: null,
      carne: null,
      opcionais: [],
      status: 'Solicitado',
      msg: null
    }
  },
  methods: {
    async getIngredients() {

      const req = await fetch('http://localhost:3000/ingredientes');
      const data = await req.json();

      this.paes = data.paes;
      this.carnes = data.carnes;
      this.opcionaisData = data.opcionais;

    }
  },
  mounted() {
    this.getIngredients()
  }
}
</script>

<style scoped>
  #burger-form {
    max-width: 400px;
    margin: 0 auto;
  }

  .input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
  }

  label {
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #FCBA03;
  }

  input, select {
    padding: 5px 10px;
    width: 300px;
  }

  #optional-container {
    flex-direction: row;
    flex-wrap: wrap;
  }

  #optional-title {
    width: 100%;
  }

  .checkbox-container {
    display: flex;
    align-items: flex-start;
    width: 50%;
    margin-bottom: 20px;
  }

  .checkbox-container span,
  .checkbox-container input {
    width: auto;
  }

  .checkbox-container span {
    margin-left: 6px;
    font-weight: bold;
  }

  .submit-btn {
    background-color: #222;
    color: #FCBA03;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
  }

  .submit-btn:hover {
    background-color: #FCBA03;
    color: #222;
  }
</style>