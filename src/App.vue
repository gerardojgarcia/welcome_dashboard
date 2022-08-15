<script>
import Hello from './components/Hello.vue';
import Weather from './components/Weather.vue';
import WeatherSearch from './components/WeatherSearch.vue'
import News from './components/News.vue';
export default {
    name: "App",
    components: {
    Hello,
    Weather,
    WeatherSearch,
    News
},

      props: {
        name: String
      }

     
};


</script>

<template>
  <div class=" dashboard-container flex flex-col  px-16 w-full bg-cover bg-center">



      <div class= " dashboard w-full   backdrop-blur-sm py-16 my-16  self-center rounded-lg shadow-lg flex flex-col">
        <Hello name="Gerardo"/>


        <div class="w-auto flex flex-row mx-8 items-center  ">


          <News/>

          <Weather />



        </div>
      </div>




  </div>
</template>


<style scoped>



</style>