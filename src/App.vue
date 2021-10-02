<template>
  <div class="character-builder">
    <CharacterAttributeChanger 
      v-for="( value, key) in characterParams"
      :key="key"
      :value="characterParams[key].val"
      :additio="characterParams[key].addition"
      :maxCoun="characterParams[key].maxCount"
      @change="(v) => { handleChangeCharacter(key, v) }" 
    />    
  </div>
</template>

<script>
import CharacterAttributeChanger from '@/components/character_attribute_changer.vue'

export default {
  components: {
    CharacterAttributeChanger
  },
  data: () => ({
    characterParams: [
    {id: 0, val: 0, maxCount: 45, addition: 1},
    {id: 2, val: 0, maxCount: 45, addition: 1 },
    {id: 3, val: 0, maxCount: 45, addition: 1},
    {id: 4, val: 0, maxCount: 45, addition: 1},
    {id: 5, val: 0, maxCount: 1.0, addition: 0.1},
    {id: 6, val: 0, maxCount: 1.0, addition: 0.1}]
    
  }),
   methods: {
    handleChangeCharacter(key, v) {
      if (v > this.characterParams[key].maxCount || v < 0) {return}
      this.characterParams[key].val = v
      alt.emit('Red', this.characterParams)
    }
  }
}
</script>

<style scoped>
.character-builder {
    max-width: 100%;
    height: 600px;
    width: 350px;
    background: linear-gradient(0deg, rgb(0, 0, 0) 0%, rgb(61, 61, 61) 100%);    
    border-radius: 7%;
    opacity: 0.95; 
}
</style>
