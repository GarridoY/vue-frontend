<script lang="ts">
export default {
    data() {
        return { res: null }
    },
    methods: {
        async click() {
            this.res = await fetch('http://localhost:8080/employees').then(response => {
                // The API call was successful!
                return response.json();
            }).catch(function (err) {
                // There was an error
                console.warn('Something went wrong.', err);
                return null;
            });
        }
    }
}
</script>

<template>
    <button type="button" @click="click()">Click me</button>
    <p>{{ res }}</p>
</template>