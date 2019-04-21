<template>
  <h2 class="text-success">
    {{translatedText}}
  </h2>
</template>

<script>

export default {
  name: 'TranslateOutput',
  props:['translatedText']
}
</script>

<style scoped>
    #translateoutput{
        
    }
</style>
