<template>
  <div class="character-attribute-changer">
    <button @click="$emit('change', +(value - additio).toFixed(1))">←</button>
    <div> {{value}} | {{maxCoun}} | {{ additio }} </div>
    <button @click="$emit('change',+(value + additio).toFixed(1))">→</button>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: Number,
      required: true
    },
    maxCoun: {
      type: Number,
      required: true
    },
    additio: {
      type: Number,
      required: true
    }
  }
}
</script> 

<style scoped>
:root {
  --background-color: #000000;
  --color: #000000;
  --light-theme: #ffffff;
}
.character-attribute-changer {
  display: flex;
  justify-content: space-around;
  padding-top: 20px;
  color: white;
}
button {
  color: white;
  border-radius: 50%;
}
button {
  display: flex;
  justify-content: center;
  align-items: center;
  
  background-color: var(--light-theme);
  cursor: pointer;
  font-size: 24px;
  color: var(--color);
  transition: all 0.3s;
  position: relative;

  text-align: center;
  overflow: hidden;

  border-radius: 45%;
  box-shadow: 0 6px 30px -10px rgba(#CCCCCC, 1);
}
button:hover {
  transform: translateX(5px) translateY(-7px);
}

</style>