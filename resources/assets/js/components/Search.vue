<template>
    <div>
        <h1>Search compoment here</h1>
        <vue-google-autocomplete
                ref="address"
                id="map"
                classname="form-control"
                placeholder="Please type your address"
                v-on:placechanged="getAddressData"
                country="['us','ng']"
        >
        </vue-google-autocomplete>
    </div>
</template>
<script>
    import VueGoogleAutocomplete from 'vue-google-autocomplete'
    export default {
       components: { VueGoogleAutocomplete },
        data(){
            return {
                address: ''
            }
        },
        methods: {
            /**
             * When the location found
             * @param {Object} addressData Data of the found location
             * @param {Object} placeResultData PlaceResult object
             * @param {String} id Input container ID
             */
            getAddressData: function (addressData, placeResultData, id) {
                this.address = addressData;
                console.log(placeResultData)
            },
        },
        created(){

        },
        mounted(){
            // To demonstrate functionality of exposed component functions
            // Here we make focus on the user input
            this.$refs.address.focus();
        },
        computed: {

        }
    }
</script>
<style scoped>

</style>