<template>
<div>
    <Navbar />
    <GoogleMap />
    <Search />
    <Footer />
</div>
</template>

<script>
import Navbar from '@/components/NavBar';
import GoogleMap from '@/components/GoogleMaps';
import Search from '@/components/Search';
import Footer from '@/components/Footer';

    export default {
        components:{ 
            Navbar,
            Search,
            GoogleMap,
            Footer,
        },
        
    };

</script>

<style lang="scss" scoped>

</style>