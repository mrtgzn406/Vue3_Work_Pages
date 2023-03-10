<!-- ? We try to describe the binding styles matter by using v-bind="" method here. We can give inline css to an html tag by using v-bind:style="" method -->

<template>

  <h1 v-bind:style="'color: red; background-color: black; padding: 20px'">First Method</h1>

  <!-- todo This is the first method of giving css by using v-bind method. If we directly we want to  give some css we can do that. And we separate the expressions with ; like normal css-->

  <!-- ----------------------------------------------------------------------------------- -->
  <h1 v-bind:style="{
    'color' : 'white',
    'background-color' : 'darkgreen',
    'font-weight' : 'bolder'
  }">Second Method</h1>

  <!-- todo This is the second method, we are giving css properties in a curly braces. So, we are giving css properties like an object property. Because as you know, writing css properties almost same as writing object properties. Therefore, we are writing css properties in curly braces and we enclose our css expression with '' for both css property name ('color') and css property  ('red'). -->

  <!-- ----------------------------------------------------------------------------------- -->
  
  <h1 v-bind:style="{
    color: 'aqua',
    backgroundColor : 'purple',
    fontSize: '3rem'
  }">Third Method</h1>

<!-- todo This is the third method, we are giving css properties with javascript syntax. So, we are writing the css property name with javascript syntax plainly and writing property with css syntax in '' symbols. And if we write this css property name with javascript syntax then we must apply this rule: if property name including only one word (like 'color', 'width', 'height') then we can write that property name same as css syntax, but if the property name that we will write, including two or moreover words (like 'font-size', 'background-color', 'font-variant') then we must write that property name with javascript syntax, meaning writing property names with "lower camel case" by writing without '' symbols (like fontSize, backgroundColor, fontVariant).  -->
<!-- ! Note that, every language has a naming convention. For instance, Css has "kebab case" naming convention and Javascript has "camel case" naming convention. Because while declaring multi word identifiers (a name that identifies a variable, class, arrays, numbers, strings, etc). They sometimes cannot be separated by space, because the space character can be a reserved key word and might result in an error. 

  ? So, "kebab case" means if there is a variable that has two or more words (for example background-color, margin-top), this variable's words will be separated from each other with a dash (-), like margin-left, font-variant etc. 

  ? And "lower camel case" means is there is a variable that has two or more words, they must be separated by writing the first letter of word capital except first word.   -->

<!-- ----------------------------------------------------------------------------------- -->

<h1 v-bind:style="{
  display : displaying,
  'border': bordering,
  borderRadius : '15px',
  paddingRight: '30px',
  'padding-left': '30px',
  paddingBottom: '30' + pixel_unit,
  'padding-top': '30' + pixel_unit
}">Fourth Method</h1>

<!-- todo This is the fourth method, we giving css properties by using javascript object properties. Here, we write  css property name both with javascript syntax and css syntax . Addition that, we give css properties with javascript object properties. So, to do this , we firstly create an key-value pair in return object which exist in <script> tags and give it a css property in ''. Secondly we write an css property name in v-bind method and give that javascript property key as property .  So that whatever javascript properties includes itself , it will be applied to relevant html tag.   -->

  <!-- ----------------------------------------------------------------------------------- -->

  <h1 v-bind:style="h1_text_properties">Fifth Method example 1</h1>

  <h1 v-bind:style="[h1_text_properties, h1_other_properties]">Fifth method example 2 </h1>

  <!-- todo This is the fifth method, we are giving css properties directly as a javascript object. Therefore, we firstly create a javascript object in return object as a property. Secondly, we should write css properties in that object. Thirdly, we write this object's name in v-bind:style="" method and we don't write curly braces here. If we want to write two or more javascript objects in v-bind:style="" method we must create an index operator ([]) in v-bind:style="" method and write javascript objects' names inside index operator by separating each one of them with a comma (,).     -->
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  data (){
    return{
      displaying : 'inline-block', 
      bordering: '10px groove yellow',
      radius : '10px',
      pixel_unit : 'px',

      h1_text_properties: {
        'text-decoration': 'underline',
        color : 'orangered',
      },
      h1_other_properties: {
        width : '400px',
        height : '200px',
        padding : '20px',
        'margin' : 'auto',
        border : '5px dashed purple'
      }


   
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
