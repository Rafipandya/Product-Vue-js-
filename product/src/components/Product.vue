// Products.vue

<template>
  <div class="main">
    <h3 class="mb-4" style="font-size: 40px;">Products</h3>
    <!-- page -->
    <div class="row">
      <!-- Card 1 -->
      <div class="col-md-4" v-for="product in products" :key="product.id">
        <div class="card cards-top" style="width: 18rem;">
          <div class="card-body cards1">
            <div class="card Body" v-if="product.stock < 10" style="background: #FF5C5C; border: none; padding-bottom: 100px; border-radius: 25px;">
              <h5 class="card-title stock">{{product.stock}}</h5>
            </div>
            <div class="card Body" v-else style="background: #80ED99; border: none; padding-bottom: 100px; border-radius: 25px;">
              <h5 class="card-title stocks">{{product.stock}}</h5>
            </div>
            <p class="card-text values bold mt-4">{{product.name}}</p>
            <div class="row values2">
              <div class="card-body values2 col-md-6">
              <p class="card-text values2 bold mt-2" >Total Sold</p>
              </div>
              <div class="card-body ml-2 col-md-3" v-if="product.qty > 3">
                <p class="card-text mt-2 bold" style="background-color: transparent; color: green;" >{{product.qty}}</p>  
              </div>
              <div class="card-body ml-2 col-md-3" v-else>
                <p class="card-text bold" >{{product.qty}}</p>  
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.main {
  padding-left: 130px;
}

.cards-top {
   border-radius: 25px;
   margin-bottom: 160px;
   height: 380px;
}

.cards1 {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  background-color: white;
  border: 2px solid white;
  border-radius: 25px;
}

.stock {
  background-color: transparent;
  font-size: 70px;
  color: #750000;
  margin: auto;
  padding-top: 80px;
}

.stocks {
  background-color: transparent;
  font-size: 70px;
  color: green;
  margin: auto;
  padding-top: 80px;
}

.values {
  background-color: transparent;
  font-size: 24px;
}

.values2 {
  background-color: transparent;
}

.values3 {
  background-color: grey;
  width: 30px;
  height: 30px;
  border-radius: 25px;
  
}


</style>

<script>
export default {
  props : ['id','product_id'],
  data() {
    return {
      products: []
    }
  },
  mounted() {
    fetch(['http://localhost:3000/penjualan'])
    .then(res => {
      return res.json();
    })
    .then(data => this.products = data)
    .catch(err => console.log(err.message))
  }
};
</script>
