<!-- <template>
    <div>
        <h2>Welcome, {{ username }}!</h2>
        <p>Email: {{ email }}</p>
    </div>
</template> -->
<template>
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-md-8">
          <div class="card text-center">
            <div class="card-header">Welcome, {{ username }}!</div>
            <img class="card-img-top mx-auto d-block" src="@/assets/profile.png" alt="Profile Photo" style="width: 40%; height: auto;">
            <div class="card-body">
              <div class="form-group">
                <label>Name:</label>
                <p class="form-control-static">{{ username }}</p>
              </div>
              <div class="form-group">
                <label>Email:</label>
                <p class="form-control-static">{{ email }}</p>
              </div>
              <router-link :to="'/register/return'" class="btn btn-primary">Logout</router-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
<script setup>
import { ref, onMounted } from 'vue';

const username = ref('');
const email = ref('');
onMounted(() => {

    const savedUsername = localStorage.getItem('username');
    const savedEmail = localStorage.getItem('email');
    username.value = savedUsername;
    email.value= savedEmail;
});

// export default {
//     props: {
//         username: String,
//         email: String
//     },
//   };
</script>