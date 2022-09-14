<template>
  <div class="container flex flex-col justify-center items-center mx-auto w-full min-h-screen">
    <h1 class="text-2xl font-bold">Dice Roll Challenge</h1>
    <div class="mx-auto text-center mt-4">
      <h2 class="text-xl font-medium">Number of Dice</h2>
      <input type="text" name="numberofdice" class="placeholder:italic placeholder:text-slate-400 block bg-white w-full border border-slate-300 rounded-md py-2 pl-2 pr-3 shadow-sm focus:outline-none focus:border-sky-500 focus:ring-sky-500 focus:ring-1 sm:text-sm" />
      <button @click="rollAll(3)" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 mb-4 rounded">
        ROLL
      </button>
    </div>
    <div class="mx-auto text-center">
      <!-- Dice Gallery -->
      <Die face-no="8" />
      <!-- Dice Gallery ends -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    rollDie() {
      let rand = Math.random();
      rand = Math.floor(rand * 6);
      rand = rand + 1;
      return rand;
    },
    rollAll(noOfRolls) {
      const rolls = [];
      for(let i; i <= noOfRolls; i++) {
          const roll = this.rollDie();
          rolls.push(roll);
      }
      console.log(rolls);
    },
  }
}
</script>
