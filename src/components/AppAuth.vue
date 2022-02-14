<template>
    <div class="card centered">
        <h1>Авторизация</h1>
        <input type="text" name="tell" v-model="username" />
        <input type="password" name="password" v-model="password" />
        <button @click="handleAuth">Авторизация</button>
    </div>
</template>

<script>
export default {
    name: "AppAuth",
    data() {
        return {
            username: "+77052279866",
            password: 1111,
        };
    },
    methods: {
        async handleAuth() {
            const bodyFormData = new FormData();
            bodyFormData.append("tell", this.username);
            bodyFormData.append("password", this.password);

            // Send data to parent
            this.$emit("authorize", bodyFormData);
        },
    },
};
</script>
