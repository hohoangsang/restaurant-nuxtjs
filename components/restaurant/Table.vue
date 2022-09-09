<script lang="ts" setup>
import restaurant from "@/data.json";

const restaurantOrganized = {
  first: [...restaurant].splice(0, 25),
  second: [...restaurant].splice(25, 50),
};
</script>

<template>
  <div class="table">
    <h1>TOP 50: THE RANKING</h1>
    <div class="table-container">
      <div class="table-col">
        <RestaurantRow 
            v-for="restaurant in restaurantOrganized.first" 
            :key="restaurant.id" 
            :restaurant="restaurant"
        />
      </div>
      <div class="table-col">
        <RestaurantRow 
            v-for="restaurant in restaurantOrganized.second" 
            :key="restaurant.id" 
            :restaurant="restaurant
        />
      </div>
    </div>
  </div>
</template>

<style scoped>
.table {
  margin: 3rem 0;
}
.table h1 {
  margin-bottom: 2rem;
}
.table-container {
  display: flex;
  justify-content: space-between;
}
.table-col {
  width: 48%;
}
</style>
