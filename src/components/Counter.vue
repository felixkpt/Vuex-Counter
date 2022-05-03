<template>
  <div>
    <h1>Vuex Counter</h1>
    <h1 class="counter">{{ counter }}</h1>
    <button @click="subFromCounter(parseInt(value))">-</button>
    <input type="number" v-model="value">
    <button @click="addToCounter(parseInt(value))">+</button>
    <div>
    <button @click="addRandomNumber" class="btn">Add Random Number</button>
    </div>
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions } from 'vuex'
export default {
    data() {
        return {
            value: 1
        }
    },
    computed: {
        ...mapState(['counter', 'counter2'])

    },
    methods: {
        ...mapMutations(['addToCounter', 'subFromCounter']),
        ...mapActions(['addRandomNumber'])
    }
}
</script>

<style>
.counter{
    font-size: 3rem;
}
button {
    border-radius: 100%;
    width: 2rem;
    height: 2rem;
    font-weight: 700;
    border: 3px solid green;
}
input {
    padding: 0.2rem 0;
    margin: 0.2rem 0;

}
.btn {
    /* display: block; */
    border-radius: .5rem;
    width: auto;
    background: green;
    backdrop-filter:gray;
    color:white;
    cursor:pointer
}
</style>
