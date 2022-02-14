<template>
    <div class="card centered" v-if="profile">
        <h1>Профиль</h1>

        <p>ID пользователя: {{ profile.id }}</p>
        <p>Телефон: {{ profile.tellWithMask }}</p>
    </div>
</template>

<script>
import api from "../services/api";

export default {
    name: "AppProfile",
    data() {
        return {
            profile: null,
        };
    },
    mounted() {
        this.init();
    },
    methods: {
        async init() {
            const { data } = await api.get("/profile");
            this.profile = data.data;
        },
    },
};
</script>
