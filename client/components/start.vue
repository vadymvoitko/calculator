<template>
  <div class='alert alert-secondary'>
  <h3>Are you ready?</h3>
  <button @click="ClickStart" class="btn btn-success">Start</button>
    
  </div>
</template>

<script>
export default {
  name: 'start',
  data(){
    return {
        
    }
  },
  methods: {
    ClickStart: function(ev){
        this.$emit('StartEmit');
    }
  }
}
</script>

<style scoped>
    .alert {
    text-align: center;
    }
</style>