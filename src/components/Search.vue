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
    height: 50vh;
    background: black;
}

.input {
    align-self: center;
    width: 75%;
    display: inline-block;
    margin: auto;
}

.searhButton {
    align-self: center;
    margin-left: 1rem;
    display: inline;
}

</style>