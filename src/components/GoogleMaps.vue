<template>
    <div>
        <h1 v-show="error" :class="{'danger': error}">{{error}}<i class="fas fa-times floatRight" @click="closeErrorMessage"></i></h1>
        <div id="map"></div>

    </div>
</template>

<script>
    export default {

    data() {
        return {
            apiKey: 'AIzaSyDz5U-vkiXLyBmHyHyIqj0XOweq7EkmoZ0',
            lat: 0,
            lng: 0,
            error: '',
        }
    },

    mounted() {
        this.getUsersLatLng();

    },

    methods: {
        getUsersLatLng() {
            if(navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                
                position => {
                    this.lat = position.coords.latitude;
                    this.lng = position.coords.longitude
                    console.log(position.coords.latitude)
                    console.log(position.coords.longitude)
                },
                error => {
                    this.error = error.message
                    console.log(error.message)
                }
                )

            } else {
                let cfs = confirm('Allow browser to know your current location')
                console.log('Your browser does not support golocation API');
            }
        },

        closeErrorMessage()  {
            this.error = '';
        }
    }
        
    }
</script>

<style lang="scss" scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.danger {
    font-size: 1.5rem;
    padding: 1rem;
    text-align: center;
    background: red;
}

.floatRight {
    margin-right: 20px;
    cursor: pointer;
    float: right;
    transition: color ease-in 0.25s;
}
.floatRight:hover {
    color:#fff
}

</style>