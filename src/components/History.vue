<template>
  <div class="container">
      <div style="width: auto;">

      <h4>History</h4>
      <div class="flex">
          <p v-for="(hist, i) in history" :key="i"
          :class="activeIndexes(parseInt(value)).includes(i) && 'bold'">{{ hist }}</p>
      </div>
      <input type="number" v-model="value">
      </div>
      
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
data() {
    return {
        value: 0
        }
},
computed: {
    ...mapState(['history']),
    ...mapGetters(['activeIndexes'])
}

}
</script>

<style>
.container {
    margin-top: 10px;
}
.flex {
    display: flex;
    text-align: center;
    width: 25rem;
    margin: 0 auto;
    justify-content: center;
    flex-wrap: wrap;
}
p{ padding: 3px; border:gray 1px solid;margin:1px}
.bold {
    font-weight: 900;
}
</style>