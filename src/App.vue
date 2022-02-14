<template>
    <div id="app">
        <AppAuth v-if="!isAuthenticated" @authorize="authorize" />
        <AppProfile v-else />
    </div>
</template>

<script>
// Components
import AppAuth from "./components/AppAuth.vue";
import AppProfile from "./components/AppProfile.vue";

// Utils
import api from "./services/api";

export default {
    name: "App",
    components: {
        AppAuth,
        AppProfile,
    },
    data() {
        return {
            isAuthenticated: false,
        };
    },
    methods: {
        async authorize(bodyFormData) {
            try {
                const { data } = await api({
                    method: "post",
                    url: "/auth/login",
                    data: bodyFormData,
                    headers: { "Content-Type": "multipart/form-data" },
                });

                api.defaults.headers.common["Authorization"] = `Bearer ${data.data.access_token}`;
                this.isAuthenticated = true;
            } catch (error) {
                console.log("ERROR", error);
            }
        },
    },
};
</script>
