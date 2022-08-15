<script>
import WeatherSearch from './WeatherSearch.vue';
export default {
    name: "Weather",
    components: { WeatherSearch },
    data() {
        return {
            result: "",
            responseAvailable: false,
            apiKey: '4bc8375613mshaa0ae80cf189616p1d566ejsnc0ff17993430'
        }
    },

    methods: {


        //////////////////////Fetch Data
        fetchAPIData() {
            this.responseAvailable = false

            const options = {
                method: 'GET',
                headers: {
                    'X-RapidAPI-Key': '4bc8375613mshaa0ae80cf189616p1d566ejsnc0ff17993430',
                    'X-RapidAPI-Host': 'weatherbit-v1-mashape.p.rapidapi.com'
                }
            };

            fetch('https://weatherbit-v1-mashape.p.rapidapi.com/forecast/minutely?lat=34.1&lon=-118.2&units=imperial', options)
                .then(response => {
                    if (response.ok) {
                        return response.json()
                    } else {
                        alert("Server returned " + response.status + " : " + response.statusText);
                    }
                })
                .then(response => {
                    this.result = response.data[0].temp;
                    this.responseAvailable = true;
                    console.log(response.data[0].temp)
                })
                .catch(err => {
                    console.log(err);
                });

               
        },

        

        


            ////// Display information


                    


            
            
    }

   
}
</script>


<template>

    <div class="border w-2/5 rounded  mx-4 shadow-lg">

        <div class="weather-header">

            <WeatherSearch />

            <div class="mx-2">
            <button class="text-white bg-orange-300 shadow-lg rounded-lg border-0 px-4 my-4 hover:bg-orange-500" type="button" id="get-weather" @click="fetchAPIData">Get Weather</button>
            </div>

            <div id='temp' v-if="responseAvailable == true">
               
        <hr >
                                <div class="text-bold h-24 text-white flex items-center text-center">
                                    <p  class="text-xl text-white text-bold ">
                                    The Temperature right now is {{ result }} in Los Angeles, CA
                                    </p>
                                </div>
                       

            </div>
        </div>
    </div>





</template>