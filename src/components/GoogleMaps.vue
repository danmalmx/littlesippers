<template>
    <div>
        <h1>Map Goes Here</h1>
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
                navigator.geolocation.getCurrentPosition(position => {
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
                throw 'Your browser does not support golocation API';
            }
        }
    }
        
    }
</script>

<style lang="scss" scoped>

</style>