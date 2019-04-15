<template>
    <div class="container">
        <div class="card card-default">
            <div class="card-header">Teacher Dashboard</div>

            <div class="card-body">
                Welcome to Teacher dashboard
            </div>
           
        </div>
        <div class="card card-default">
            <div class="card-header">Students list</div>

            <div class="card-body">
                <userList></userList>
            </div>
        </div>
    </div>
</template>

<script>
  import userList from '../../components/user-list.vue'
  export default {
    mounted() {
      //
    },
    components: {
      userList
    }
  }
</script>