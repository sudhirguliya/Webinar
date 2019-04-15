<template>
    <div id="main">
        <header id="header" class="container-fluid" style="min-height:auto; background:#333">
            <!-- <h1>
                <router-link :to="{name: 'home'}">
                    Laravel Vue SPA
                </router-link>
            </h1> -->
          <div class="row">
              <div class="col-xs-12">
                <nav class=" navbar navbar-bootsnipp animate " role="navigation">
                  <div class=" container ">
                    <!-- Brand and toggle get grouped for better mobile display -->
                    <div class=" navbar-header ">
                        <button type="button" class=" navbar-toggle " data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
                            <span class=" sr-only ">Toggle navigation</span>
                            <span class=" icon-bar "></span>
                            <span class=" icon-bar "></span>
                            <span class=" icon-bar "></span>
                        </button>
                        <div class=" animbrand ">
                            <a class=" navbar-brand  animate" v-bind:href="'/'" >
                            <img src="https://www.goconsult.in/img/gc-logo.png" > </a>
                        </div>
                    </div>

                    <navigationMenu></navigationMenu>

                  </div>
                </nav>
              </div>
          </div>
        </header>
        <div id="content">
            <router-view></router-view>
        </div>
    </div>
</template>

<script>
  import navigationMenu from './components/Menu.vue'
  export default {
    data() {
      return {
        //
      }
    },
    components: {
      navigationMenu
    }
  }
</script>