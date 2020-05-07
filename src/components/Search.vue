<template>

  <b-container fluid class="search">
    <b-form-group class="searchSet">
        <div class="searchBox">
            <b-form-input class="searchInput" placeholder="Search for a location"></b-form-input>
        </div>
        <!-- <div class="searchButton">
            <b-button variant="success">Find</b-button>
        </div>        
        <div class="searchHereButton">
            <b-button class="shbSize"variant="primary">Find Close By</b-button>
        </div>         -->
    </b-form-group>
  </b-container fluid>
</template>

<script>

    export default {
        data() {
            return {
                text: '',
            }
        }
    }
</script>

<style lang="scss" scoped>

.search  {
    position: relative;
    height: 25vh;
    background: darkgrey;
    // (1, 5, 243); 
    background-color: transparent(0.6);
}

.searchSet {
    vertical-align: middle;
    // display: flex;
    // justify-content: space-between;
}

.searchBox {
    // position: absolute;
    // top: 45%;
    // left: 30%;
    // right: 30%;
    vertical-align: middle;
    margin: auto;
    background: url('/src/assets/search-solid.svg');
    padding-left: 20px;
}

.searchInput {
    background-color: #fff;
    position: absolute;
    top: 35%;
    left: 30%;
    height: 5rem;
    font-size: 1.5rem;
    width: 45%;
    border-radius: 50px;
    color: #ccc;
    background-position: 20px;
    border: 3px solid #999;
}

.searchInput:focus {
    padding-left: 20px;
}

::placeholder {
    padding: 20px;
    color: #ccc;
}


// .searchButton {
//     position: absolute;
//     top: 45%;
//     left: 30.3%
// }

// .searchHereButton {
//     width: 300px;
//     position: absolute;
//     top: 45%;
//     right: 41%;
// }

</style>