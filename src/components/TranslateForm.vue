<template>
  <div class="row" id="translateform">
      <div class="col-md-6 col-md-offset-3">
        <form id="transForm" class="form-inline well" @submit="formSubmit">
            <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter Text to translate" />
            
            <select class="form-control" v-model="language">
                <option value="ru">Russian</option>
                <option value="es">Spanish</option>
                <option value="fr">French</option>
                <option value="zh">Chinese</option>
                <option value="hi">Hindi</option>
                <option value="ar">Arabic</option>
                <option value="mr">Marathi</option>
                <option value="pa">Punjabi</option>
                <option value="ur">Urdu</option>
            </select>
            <br>
            <input class="btn btn-primary" type="submit" value="Translate" >
        </form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'TranslateForm',
  data(){
      return {
          textToTranslate: 'what is your name', language:''
      }
  },
  created(){
      this.language = 'ru';
  },
  methods:{
      formSubmit: function(e) {
          this.$emit('formSubmit', this.textToTranslate, this.language);
          e.preventDefault();
      }
  }
}
</script>

<style>
    #_translateform{
        width:70%;
        margin-left: 20px;
    }
    #transForm{
        border-radius:10px;
        border:1px #ccc solid;
        padding:10px;
    }
</style>
