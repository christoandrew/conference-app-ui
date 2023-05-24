<template>
    <div class="container">
        <NavBar/>
        <router-view></router-view>
    </div>
</template>
<script>
import {defineComponent, ref} from 'vue';

import NavBar from "./components/NavBar.vue";

export default defineComponent({
    components: {
        NavBar,
    },
    setup() {
    },
});
</script>