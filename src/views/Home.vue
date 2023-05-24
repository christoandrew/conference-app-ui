<template>
    <div style="padding-top: 20px">
        <Carousel/>
        <a-page-header
                style="border: 1px solid rgb(235, 237, 240); margin-top: 10px"
                title="Upcoming Events"
        />
        <a-row style="padding-top: 10px;">
            <a-card :title="event.name" style="width: 240px; margin-right: 10px" v-for="event in events">
                <template #extra>
                    <a :href="event.url">More</a>
                </template>
                <p>{{ event.location }}</p>
                <p>{{ event.date }}</p>
            </a-card>
        </a-row>
    </div>
</template>

<script>
import {defineComponent} from 'vue';
import Carousel from "../components/Carousel.vue";
import axios from 'axios'
import moment from 'moment'

export default defineComponent({
    data() {
        return {
            events: []
        }
    },
    components: {
        Carousel,
    },
    setup(props) {

    },
    mounted() {
        axios.get("http://127.0.0.1:8000/api/conferences")
            .then(response => (this.events = response.data))
    },
    computed:{
        formatDate(){
            moment().format('MMMM Do YYYY')
        }
    }
});
</script>