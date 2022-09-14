<template>
  <div class="container flex flex-col justify-center items-center mx-auto w-full min-h-screen">
    <h1 class="text-2xl font-bold">Dice Roll Challenge</h1>
    <div class="mx-auto text-center mt-4">
      <h2 class="text-xl font-medium">Number of Dice</h2>
      <input type="number" name="numberofdice" v-model=noOfRolls class="placeholder:italic placeholder:text-slate-400 block bg-white w-full border border-slate-300 rounded-md py-2 pl-2 pr-3 mb-2 shadow-sm focus:outline-none focus:border-sky-500 focus:ring-sky-500 focus:ring-1 sm:text-sm" />
      <button @click="rollAll(noOfRolls)" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 mb-4 rounded">
        ROLL
      </button>
    </div>
    <div class="flex flex-row mx-auto text-center">
      <!-- Dice Gallery -->
      <Die v-bind:key="index" v-for="die, index in rollsResult" :face-no=die />
      <!-- Dice Gallery ends -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      noOfRolls: null,
      rollsResult: {
        type: Array,
        default: [],
      }
    }
  },
  methods: {
    rollDie: function() {
      const minSideVal = 1;
      const maxSideVal = 6;
      let rand = Math.random();
      rand = Math.floor(rand * maxSideVal) + minSideVal;
      return rand;
    },
    rollAll: function(noOfRolls) {
      this.rollsResult = [];
      const rolls = [];
      for(let i = 0; i <= noOfRolls - 1; i++) {
          const roll = this.rollDie();
          rolls.push(roll);
      }
      this.rollsResult = rolls;
    },
  }
}
</script>
