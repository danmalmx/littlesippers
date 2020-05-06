<template>

  <div class="search">
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
  </div>
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
    height: 40vh;
    background: black;
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
}

.searchInput {
    position: absolute;
    top: 45%;
    left: 35%;
    height: 4rem;
    font-size: 1rem;
    width: 30%;
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