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
            <option value="whole-grain">Integral</option>
          </select>          
        </div>
        <div class="input-container">
          <label for="meat">Choose the Meat</label>
          <select name="meat" id="meat" v-model="meat">
            <option value="">Choose a Meat:</option>
            <option value="meat">Picanha</option>
          </select>          
        </div>

        <div id="optional-container" class="input-container">
          <label id="optional-title" for="optional">Choose Optional</label>
          <div class="checkbox-container">
            <input type="checkbox" name="optional" v-model="optional" value="Bacon">
            <span>Bacon</span>
          </div>            
          <div class="checkbox-container">
            <input type="checkbox" name="optional" v-model="optional" value="Salame">
            <span>Salame</span>
          </div>            
          <div class="checkbox-container">
            <input type="checkbox" name="optional" v-model="optional" value="Picles">
            <span>Picles</span>
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
  name: 'BurgerForm'
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