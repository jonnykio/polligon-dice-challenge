<template>
  <div class="w-10 h-10">
    <img class="w-full h-full" src="/die/die-01.jpg" />
  </div>
</template>

<script>
export default {
  name: "Die",
  props: {
    faceNo: {
        type: Number,
        default: 1,
        required: true,
        validator: value => {
            return value > 0 && value < 7;
        }
    },
  },
}
</script>

<style>

</style>