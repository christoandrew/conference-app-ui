<template>
    <a-menu v-model:selectedKeys="current" mode="horizontal">
        <a-menu-item key="home">
            <router-link to="/">Home</router-link>
        </a-menu-item>
        <a-menu-item key="mail">
            <router-link to="/about">About</router-link>
        </a-menu-item>
    </a-menu>
</template>

<script>
import {defineComponent, ref} from 'vue';
import {MailOutlined, AppstoreOutlined, SettingOutlined} from '@ant-design/icons-vue';

export default defineComponent({
    components: {
        MailOutlined,
        AppstoreOutlined,
        SettingOutlined,
    },
    setup() {
        const current = ref(['home']);
        return {
            current,
        };
    },
});
</script>