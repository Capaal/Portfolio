<template>
    <div class="container-fluid">
        <app-test-mini-component v-for="(page, index) in activePages" :key=index @click.native="loadComponent(index)" style="cursor: pointer"
                :page="page" class="col-sm-6 col-md-4"></app-test-mini-component>
    </div>
</template>

<script>
import TestMiniComponent from "./testMiniComponent.vue";

export default {
    data() {
        return {
          activePages: [{miniTitle: 'Mini Test',
                miniBody: 'Some details about the component. Hopefully this will have a good way of indicating what this is about with maybe an image.',
                component: '/test'}, 
            {miniTitle: 'Second',
                miniBody: 'Some details about the component. 2nd and shorter',
                component: '/test'}, 
            {miniTitle: 'Just Another Title',
                miniBody: 'Some details about the component. 3rd',
                component: '/test'},
            {miniTitle: 'Help',
                miniBody: 'Text',
                component: '/test'}, 
            {miniTitle: 'And we are fine',
                miniBody: 'I really need to create another component to test switching to, rather than the test page.',
                component: '/test'},  ],
       
        }
    },
    components: {
        'app-test-mini-component': TestMiniComponent
    },
    methods: {
        loadComponent(index) {
            this.$router.push(this.activePages[index].component);
        }
    },
}
</script>