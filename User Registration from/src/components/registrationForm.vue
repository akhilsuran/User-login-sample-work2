
<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-6">
                <div class="card">
                    <div class="card-header" style="text-align: center;">LOGIN</div>
                    <div class="card-body">
                        <form @submit.prevent="registerUser">
                            <div class="form-group">
                                <label for="email">Username:</label>
                                <input class="form-control" type="text" id="username" v-model="username" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Email address:</label>
                                <input type="email" class="form-control" id="email" v-model="email" required>
                            </div>
                            <div class="form-group">
                                <label for="password">Password:</label>
                                <input type="password" class="form-control" id="password" v-model="password" required>
                            </div>
                            <br>
                            <button type="submit" class="btn btn-primary">Submit</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script >

export default {
    data() {
        return {
            id: this.$route.params.id,
            username: '',
            email: '',
            password: ''
        };
    },
    created() {
        if (this.id) {
            localStorage.clear();
            console.log("storage cleared")
        }
    },
    methods: {
        registerUser() {
            localStorage.setItem('username', this.username);
            localStorage.setItem('email', this.email);
            this.$router.push('/profile', {
                username: this.username,
                email: this.email
            });
        }
    }
};
</script>
    