<template>
  <div id="burger-table">
    <div>
      <div id="burger-table-header">
        <div class="order-id">#:</div>
        <div>Customer:</div>
        <div>Bread:</div>
        <div>Meat:</div>
        <div>Optionals:</div>
        <div>Actions:</div>
      </div>
    </div>
    <div id="burger-table-rows">
      <div class="burger-table-row">
        <div class="order-number">1</div>
        <div>name</div>
        <div>integral</div>
        <div>picanha</div>
        <div>
          <ul>
            <li>Bacon</li>
            <li>Bacon</li>
          </ul>
        </div>
        <div>
          <select name="status" class="status">
            <option value="">Order Status</option>
          </select>
          <button class="delete-btn">Cancel</button>
        </div>
      </div>
    </div>    
  </div>
</template>

<script>
export default {
  name: 'Dashboard'
}
</script>

<style scoped>
  #burger-table {
    max-width: 1200px;
    margin: 0 auto;
  }

  #burger-table-header,
  #burger-table-rows,
  .burger-table-row {
    display: flex;
    flex-wrap: wrap;
  }

  #burger-table-header {
    font-weight: bold;
    padding: 12px;
    border-bottom: 3px solid #333;
  }

  #burger-table-header div,
  .burger-table-row div {
    width: 19%;
  }

  .burger-table-row {
    width: 100%;
    padding: 12px;
    border-bottom: 1px solid #CCC;
  }

  #burger-table-header .order-id,
  .burger-table-row .order-number {
    width: 5%;
  }

  select {
    padding: 12px 6px;
    margin-right: 12px;
  }

  .delete-btn {
    background-color: #222;
    color: #fcba03;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
  }

  .delete-btn:hover {
    background-color: #FCBA03;
    color: #222;
  }
</style>