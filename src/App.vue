<template>
  <!-- <div id="app">
    <Navbar />
    <router-view /> 
   </div> -->
   <div>
      <h1>Gitについて</h1>
       <Counter></Counter>
  </div>
 
</template>

<script>
// import Navbar from "@/components/Navbar.vue"

// export npmdefault {
//   components: {
//     Navbar,
//   },
// }
import Counter from "@/components/Counter.vue"

export default{
  components:{
    Counter,
  },
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.body {
  margin: 0px, 0px;
} */
</style>
