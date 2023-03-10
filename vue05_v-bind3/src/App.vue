<!-- ? We learn the shorthand of v-bind method here. It is the short way of using v-bind  because this method is oftenly be used. -->

<template>

  <span :style="paragraph">Span tag</span>

  <br>

  <div :class="class_name">Div tag</div>

  <br>

  <button :disabled="true">Button tag</button>

  <!-- todo That's it, this is the shorthening way of writing  v-bind method. So, instead of writing v-bind , we only write a colon (:) an use it-->

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  data (){
    return{

      paragraph :{
        fontSize: '36px',
        display : 'block',
        fontWeight: 'bolder',

      },

      class_name : "murat"
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
