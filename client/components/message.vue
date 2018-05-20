<template>
    <div class="container">
        <h1>{{x}} + {{y}} = ?</h1>
        <hr>
        <button v-for="number in answers" 
                @click="onAnswer(number)"
                class="btn btn-primary answers"
        >{{number}}</button>
    </div>
</template>

<script>
    export default {
  name: 'message',
  data(){
    return {
        x: GetNumber(100,200),
        y: GetNumber(100,200)
        
    }
  },
  methods: {
    onAnswer(num){
        if(num == this.good){
            this.$emit('success');
            
        }
        else {
            this.$emit('error',`${this.x} + ${this.y} = ${this.good}`);
            
        }
    }
  },
  computed: {
    good () {
        return this.x + this.y
        },
      answers(){
      let numbers = [this.good];
      
      while(numbers.length < 4){
      let num = GetNumber(this.good + 20, this.good - 20);
      if(numbers.indexOf(num) === -1)
        numbers.push(num);
      }
      numbers.sort(()=>{return Math.random() - Math.random()});
      return numbers;
      }
  }
}
function GetNumber(min, max){
    return Math.floor((Math.random()*(max - min) + min))
}
</script>

<style>
    .answers{
        margin: 10px;
    }
</style>