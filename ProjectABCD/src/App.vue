<template>
    <div id="app">
        <Navbar></Navbar>
        <div class="container">
            <div v-if="fetchingData">
                <p>Loading data</p>
            </div>
            <div v-else-if="data.length === 0">
                <p>No data to show</p>
            </div>
            <div v-else>
                <market-view :data="data" />
            </div>
        </div>
        <Footer></Footer>
    </div>
</template>

<script>
import MarketView from './components/MarketView.vue';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';

export default {
    name: 'App',
    components: {
        MarketView,
        Navbar,
        Footer
    },
    data() {
        return {
            data: [],
            fetchingData: false
        }
    },
    computed: {
    },
    methods: {
        /**
         * Fetch data from instruments.json
         */
        fetchData() {
            return new Promise((resolve) => {
                const xmlHttp = new XMLHttpRequest();

                xmlHttp.onreadystatechange = function() { 
                    if (xmlHttp.readyState == 4 && xmlHttp.status == 200)
                        resolve(xmlHttp.responseText);
                }

                xmlHttp.open("GET", 'http://localhost:8080/instruments.json', true); // true for asynchronous 
                xmlHttp.send(null);
            })
        }
    },
    async mounted() {
        this.fetchingData = true;
        
        const response = await this.fetchData();

        this.data = JSON.parse(response);

        this.fetchingData = false;
    },
}
</script>

<style>
/* #app {

} */
</style>