<template>
    <div>
        <h3 v-show="error" :class="{'danger': error}" class="animated fadeInUp faster">{{error}}<i class="fas fa-times floatRight" @click="closeErrorMessage"></i></h3>
        <div id="map">Map shows here</div>
    </div>
</template>

<script>
    import GoogleMapsApiLoader from 'google-maps-api-loader'

    export default {
        
        data() {
            return {
            apiKey: 'AIzaSyBIyBiGEuyhC5Cc-_W8k654CDOD6i2XndM',
            lat: 0,
            lng: 0,
            error: '',
            google: null,
        }
    },

    async mounted() {
        await this.initiatGoogleMaps();
        await this.initMap();
        // await this.getUsersLatLng();
    },

    methods: {
        getUsersLatLng() {
            if(navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    
                    position => {
                    this.lat = position.coords.latitude;
                    this.lng = position.coords.longitude;
                    console.log(position.coords.latitude);
                    console.log(position.coords.longitude);
                },
                error => {
                    this.error = error.message
                    console.log(error.message)
                }
                )

            } else {
                console.log('Your browser does not support golocation API');
            }
        },

        closeErrorMessage()  {
            this.error = '';
        },

        initMap() {
            
        if(navigator.geolocation) {
            navigator.geolocation.getCurrentPosition(
            
                position => {
                this.lat = position.coords.latitude;
                this.lng = position.coords.longitude;
                console.log(position.coords.latitude);
                console.log(position.coords.longitude);
            },
        error => {
            this.error = error.message
            console.log(error.message)
        }
        )

        } else {
            console.log('Your browser does not support golocation API');
        }
        
        let options = {
            center: {
                // lat: 57.7250,
                // lng: 12.9600,
                lat: this.lat,
                lng: this.lng,
            },
            zoom: 3,
        }

            console.log(this.lat, this.lng)

            let map = new google.maps.Map(document.getElementById('map'), options);

        },

        async initiatGoogleMaps() {
            const googleMapApi = await GoogleMapsApiLoader({
            apiKey: this.apiKey
        })
            this.google = googleMapApi;
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
    transition: all ease-in 1s;
    color: #fff;
}

.floatRight {
    margin-right: 20px;
    cursor: pointer;
    float: right;
    transition: color ease-in 0.25s;
}
.floatRight:hover {
    color:#aaa
}

#map {
    height: 500px;
    width: 100%;
}

</style>