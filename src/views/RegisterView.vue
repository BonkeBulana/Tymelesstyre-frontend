<template>
  <div class="register-container">
    <h2>Register your account</h2>

    <form @submit.prevent="handleRegister">
      <div class="form-group">
        <label>Name</label>
        <input v-model="fullName" type="text" placeholder="Enter your full name..." required />
      </div>

      <div class="form-group">
        <label>Surname</label>
        <input v-model="surname" type="text" placeholder="Enter your surname..." required />
      </div>

      <div class="form-group">
        <label>Username</label>
        <input v-model="username" type="text" placeholder="Enter a username..." required />
      </div>

      <div class="form-group">
        <label>Email address</label>
        <input v-model="email" type="email" placeholder="Enter your email address..." required />
      </div>

      <div class="form-group">
        <label>Password</label>
        <input v-model="password" type="password" placeholder="Enter your password..." required />
      </div>

      <div class="form-group">
        <label>Confirm Password</label>
        <input v-model="confirmPassword" type="password" placeholder="Enter your password again..." required />
      </div>

      <div class="form-group">
        <label>Role</label>
        <select v-model="role" required>
          <option value="">Select role</option>
          <option value="CUSTOMER">Customer</option>
          <option value="ADMIN">Admin</option>
        </select>
      </div>

      <button type="submit">
        Sign up
      </button>
    </form>

    <p class="login-link">
      Already have an account? <router-link to="/login">Sign in</router-link>
    </p>
  </div>
</template>

<script>
export default {
  name: "RegisterView",
  data() {
    return {
      fullName: "",
      username: "",
      email: "",
      password: "",
      confirmPassword: "",
      role: ""
    }
  },
  methods: {
    handleRegister() {
      console.log('Registering:', {
        fullName: this.fullName,
        username: this.username,
        email: this.email,
        password: this.password,
        role: this.role
      });
    }
  }
}
</script>

<style scoped>
.register-container {
  max-width: 400px;
  margin: 40px auto;
  padding: 30px;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

h2 {
  text-align: center;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 15px;
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 5px;
  font-weight: bold;
}

input, select {
  padding: 8px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

button {
  width: 100%;
  padding: 10px;
  background-color: #2f80ed;
  color: white;
  font-weight: bold;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.login-link {
  text-align: center;
  margin-top: 15px;
}
</style>
