<template>

  <div class="search">
    <b-form>
    <b-form-input class="input" placeholder="Search for a location"></b-form-input>
    <b-button class="SearchButton" variant="success">Find</b-button>
        
    </b-form>
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
    height: 50vh;
    background: black;
}

.input {
    position: absolute;
    top: 50%;
    left: 10%;
    width: 30%;
.searhButton {
    position: absolute;
    top: 50%;
    margin-left: 1rem;
    display: inline;
}
}


</style>