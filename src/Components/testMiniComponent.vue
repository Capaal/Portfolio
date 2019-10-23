<template>    
    <div @mouseover="isHover = true" @mouseleave="isHover = false">
        <transition name="flip" mode="out-in">
            <div class="panel panel-success" v-if="!isHover"> 
                <div class="panel-heading">
                    <h3 class="panel-title">{{ page.miniTitle }}</h3>
                </div>
                <div class="panel-body">
                    <p>{{ page.miniBody }}</p>
                </div>            
            </div>   
            <app-test-component v-else class="panel"></app-test-component>
            <!-- <component :is="app-test-component" v-else class="panel"></component>         -->
        </transition>
    </div>
</template>

<script>
import TestComponent from "./testComponent.vue";

export default {
    props: ['page'],
    data() {
        return {
            isHover: false
        }
    },
    components: {
        'app-test-component': TestComponent,
    }
    
}
</script>

<style scoped>
    .panel {
        height: 25rem;
    }
    .flip-enter {
        transform: scale(.4);
    }

    .flip-enter-active {
        animation: flip-in 200ms ease-out forwards;
    }

    .flip-leave-active {
        animation: flip-out 200ms ease-out forwards;
    }

    @keyframes flip-in {
        from {
            transform: rotateY(90deg);
        }
        to {
            transform: rotateY(0deg);
        }
    }

    @keyframes flip-out {
        from {
            transform: rotateY(0deg);
        }
        to {
            transform: rotateY(90deg);
        }
    }
</style>