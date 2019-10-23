<template>
    <div class="container">
      <app-header></app-header>
      <div class="row">
          <!-- <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3"> -->
          <div class="col-xs-12">
            <transition name="enlarge" mode="out-in">
              <router-view></router-view>
            </transition>
          </div>  
      </div>
    </div>
</template>

<script>
    import Header from "./Components/Header.vue";

    export default {   
      components: {
        'app-header': Header
      }      
    }
</script>

<style>

  body {
    padding: 30px;
  }

  .enlarge-enter-active {
    animation:enlarge-in 500ms forwards;
  }

  .enlarge-leave-active {
    animation: enlarge-out 200ms
  }

  @keyframes enlarge-in {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @keyframes enlarge-out {
    from {
      opacity: 1;
      position:absolute;
    }
    to {
      opacity: 0;
      width: 100%;
      height: 100%;
    }
  }
</style>
