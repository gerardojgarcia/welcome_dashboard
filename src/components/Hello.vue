<script>


export default {
    name: 'Hello',





    props: {
        name: String,
    },
    data() {

        return {

        
               timestamp: ""
            }

            },
            created() {
                setInterval(this.getNow, 1000);
            },
            methods: {
                getNow() {
                    const today = new Date();
                    const date = today.getFullYear()+'-'+(today.getMonth()+1)+'-'+today.getDate();
                    const time = today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds();
                    const dateTime = date +' '+ time;
                    this.timestamp = dateTime;
                }
           
    }
 }



</script>

<template>
    <div class="text-white">
        <h1 class="text-8xl pt-44">Welcome {{name}}, </h1>
        <p class="text-5xl py-16">today is {{ timestamp }}</p>
    </div>
</template>