<template>
    <nav id="nav">
      <div class=" navbar-collapse " id="bs-example-navbar-collapse-1">
        <ul class=" nav navbar-nav navbar-right mt20">
            <!--UNLOGGED-->
            <li v-if="!$auth.check()" v-for="(route, key) in routes.unlogged" v-bind:key="route.path">
                <router-link  :to="{ name : route.path }" :key="key">
                    {{route.name}}
                </router-link>
            </li>
            <!--LOGGED USER-->
            <li v-if="$auth.check(1)" v-for="(route, key) in routes.student" v-bind:key="route.path">
                <router-link  :to="{ name : route.path }" :key="key">
                    {{route.name}}
                </router-link>
            </li>
            <!--LOGGED ADMIN-->
            <li v-if="$auth.check(2)" v-for="(route, key) in routes.teacher" v-bind:key="route.path">
                <router-link  :to="{ name : route.path }" :key="key">
                    {{route.name}}
                </router-link>
            </li>
            <!--LOGOUT-->
            <li v-if="$auth.check()">
                <a href="#" @click.prevent="$auth.logout()">Logout</a>
            </li>
        </ul>
      </div>
    </nav>
</template>

<style type="text/css">
  .navbar-nav {flex-direction: row; }
  .navbar-right {
    float: right!important;
    margin-right: -15px;
}
</style>

<script>
  export default {
    data() {
      return {
        routes: {
          // UNLOGGED
          unlogged: [
            {
              name: 'Register',
              path: 'register'
            },
            {
              name: 'Login',
              path: 'login'
            }
          ],

          // LOGGED USER
          student: [
            {
              name: 'Dashboard',
              path: 'dashboard'
            }
          ],
          // LOGGED ADMIN
          teacher: [
            {
              name: 'Dashboard',
              path: 'admin.dashboard'
            },
            {
              name: 'Room',
              path: 'admin.room'
            },
            {
              name: 'Add Student',
              path: 'admin.register_student'
            },
          ]
        }
      }
    },
    mounted() {
      //
    }
  }
</script>
