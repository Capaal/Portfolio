<template>
    <div>
        <p>Test Component</p>
        <button class="btn btn-primary" @click="backPressed">Back</button>
    </div>
</template>

<script>
export default {
    methods: {
        backPressed() {
            this.$router.push('/');
        }
    }
}
</script>