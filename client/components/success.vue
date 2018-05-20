<template>
  <div class="alert" >
        <h2> {{ text }} </h2>
        <hr>
        <button class="btn btn-primary" @click="$emit('next')">
            continue
        </button>  
    <div class="container">3</div>
  </div>
</template>

<script>
    export default {
        props: ['type', 'text']
    }
</script>

<style>

</style>