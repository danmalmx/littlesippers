<template>
    <b-container fluid>
        <h3 v-show="error" :class="{'danger': error}" class="animated fadeInUp faster">{{error}}<i class="fas fa-times floatRight" @click="closeErrorMessage"></i></h3>
        <div id="map">Map shows here</div>
    </b-container fluid>
</template>

<script>
    import GoogleMapsApiLoader from 'google-maps-api-loader'

    export default {
        
        data() {
            return {
            apiKey: '',
            lat: 0,
            lng: 0,
            error: '',
            google: null,
            pos: null,
            map: null, 
            infoWindow: null,
        }
    },

    async mounted() {
        await this.initiatGoogleMaps();
        await this.initMap();
    },

    methods: {

        closeErrorMessage()  {
            this.error = '';
        },

        initMap() {
            this.map = new google.maps.Map(document.getElementById('map'), {
                center: { lat: 57.7200000, lng: 12.9400000, },
                zoom: 13,
            });

            this.infoWindow = new google.maps.InfoWindow;
            
            if(navigator.geolocation) {
                navigator.geolocation.getCurrentPosition( (position) => {
                    
                this.pos = {
                    lat: position.coords.latitude,
                    lng: position.coords.longitude,
                };
                    // this.infoWindow.setPosition(this.pos);
                    console.log(this.pos)
                    this.infoWindow.open(this.map);
                    this.map.setCenter(this.pos);

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

#map {
    height: 55vh;
    width: 100%;
    // border: .8rem solid #fff;
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

</style>
