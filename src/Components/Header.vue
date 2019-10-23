<template>
    <nav class="navbar navbar-light" style="background-color: #e3f2fd;">
        <div class="container-fluid">
            <div class="navbar-header">
                <router-link to="/" class="navbar-brand">Jason Reed</router-link>
            </div>            
            <div class="collapse navbar-collapse" >
                <ul class="navbar-nav nav">
                    <router-link to="/test" active-class="active" tag="li"><a>Test</a></router-link>
                </ul>
            </div>
        </div>
    </nav>    
</template>

<script>
export default {
    
}
</script>

<style scoped>

</style>

