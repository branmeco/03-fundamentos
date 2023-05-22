<template>
  <h2>{{customTitle}}</h2>
  <p>{{ counter }} <sup>2</sup> = {{ squareCounter }}</p>
  <div>
    <button v-on:click="increase">+1</button>
    <button v-on:click="decrease">-1</button>
  </div>
</template>

<script>
export default {
  props: ["title"],
  // name: 'Patito'
  data() {
    return {
      counter: 5,
    };
  },
  methods: {
    getSquareValue() {
      console.log("getSquareValue");
      return (this.counter = this.counter);
    },
    //increase
    increase() {
      this.counter++;
    },
    //decrease
    decrease() {
      this.counter--;
    },
  },
  computed: {
    squareCounter() {
      console.log("computed squareCounter");
      return this.counter * this.counter;
    },
    //Customtitle
    costumTitle(){
        return this.title || 'Counter';
    }
  },
};
</script>

<style>
button {
  margin: 0 5px;
  background-color: #64bbb7;
  color: white;
  border: 1px solid white;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}

button:hover {
  background-color: #5aa67b;
  transition: 0.3s ease-in-out;
}
</style>