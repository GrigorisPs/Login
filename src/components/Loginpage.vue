<template>
  <div :class="{ container: true, active: isActive }" id="container">
    <div class="form-container sign-up">
      <form>
        <h1>Create Account</h1>
        <div class="social-icons">
          <a href="#" class="icon"
            ><i class="fa-brands fa-google-plus-g"></i
          ></a>
          <a href="#" class="icon"><i class="fa-brands fa-facebook-f"></i></a>
          <a href="#" class="icon"><i class="fa-brands fa-github"></i></a>
          <a href="#" class="icon"><i class="fa-brands fa-linkedin-in"></i></a>
        </div>
        <span>or use your email for registeration</span>
        <input type="text" placeholder="Name" />
        <input type="email" placeholder="Email" />
        <input type="password" placeholder="Password" />
        <button class="formButton" type="submit" @click.prevent="register()">
          Sign Up
        </button>
      </form>
    </div>
    <div class="form-container sign-in">
      <form>
        <h1>Sign In</h1>
        <div class="social-icons">
          <a href="#" class="icon"
            ><i class="fa-brands fa-google-plus-g"></i
          ></a>
          <a href="#" class="icon"><i class="fa-brands fa-facebook-f"></i></a>
          <a href="#" class="icon"><i class="fa-brands fa-github"></i></a>
          <a href="#" class="icon"><i class="fa-brands fa-linkedin-in"></i></a>
        </div>
        <span>or use your email password</span>
        <input v-model="input.email" type="email" placeholder="Email" />
        <input
          v-model="input.password"
          type="password"
          placeholder="Password"
        />
        <a href="#" class="underline">Forgot Your Password?</a>
        <button class="formButton" type="submit" @click.prevent="login()">
          Sign In
        </button>
      </form>
    </div>
    <div class="toggle-container">
      <div class="toggle">
        <div class="toggle-panel toggle-left">
          <h1>Welcome Back!</h1>
          <p>Enter your personal details to use all of site features</p>
          <button class="btn" id="login" @click="changeForm">Sign In</button>
        </div>
        <div class="toggle-panel toggle-right">
          <h1>Hello, Friend!</h1>
          <p>Register with your personal details to use all of site features</p>
          <button class="btn" id="register" @click="changeForm">Sign Up</button>
        </div>
      </div>
    </div>
  </div>
  <div class="login-info"></div>
</template>

<script>
export default {
  name: "Loginpage",
  data() {
    return {
      isActive: false,
      input: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    changeForm() {
      this.isActive = !this.isActive;
    },
    login() {
      if (this.input.email !== "" || this.input.password !== "") {
        console.log("authenticated");
      } else {
        console.log("Username and Password can not be empty!");
      }
    },
    register() {},
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
}

body {
  background-color: #c9d6ff;
  background: linear-gradient(to right, #e2e2e2, #c9d6ff);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
}
.underline:hover {
  text-decoration: underline;
}

.container {
  background-color: #fff;
  border-radius: 30px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.35);
  position: relative;
  overflow: hidden;
  width: 768px;
  max-width: 100%;
  min-height: 480px;
}

.container p {
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.3px;
  margin: 20px 0;
}

.container span {
  font-size: 13px;
  margin-bottom: 1em;
}

.container a {
  color: #333;
  font-size: 14px;
  text-decoration: none;
  margin: 15px 0 15px;
}

.container button {
  background-color: #512da8;
  color: #fff;
  font-size: 12px;
  padding: 10px 45px;
  border: 1px solid transparent;
  border-radius: 4em;
  font-weight: 600;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  margin-top: 10px;
  cursor: pointer;
}

.container button.btn {
  background-color: transparent;
  border-color: white;
  color: #fff;
}

.container form {
  background-color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 0 40px;
  height: 100%;
}

.container input {
  background-color: #eee;
  border: none;
  margin: 8px 0;
  padding: 10px 15px;
  font-size: 13px;
  border-radius: 8px;
  width: 100%;
  outline: none;
}

.form-container {
  position: absolute;
  top: 0;
  height: 100%;
  transition: all 0.6s ease-in-out;
}

.sign-in {
  left: 0;
  width: 50%;
  z-index: 2;
}

.container.active .sign-in {
  transform: translateX(100%);
}

.sign-up {
  left: 0;
  width: 50%;
  opacity: 0;
  z-index: 1;
}

.container.active .sign-up {
  transform: translateX(100%);
  opacity: 1;
  z-index: 5;
  animation: move 0.6s;
}

@keyframes move {
  0%,
  49.99% {
    opacity: 0;
    z-index: 1;
  }
  50%,
  100% {
    opacity: 1;
    z-index: 5;
  }
}

.social-icons {
  margin: 20px 0;
}

.social-icons a {
  border: 1px solid #ccc;
  border-radius: 20%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  margin: 0 3px;
  width: 40px;
  height: 40px;
}
.social-icons a:hover {
  transform: scale(1.2);
  color: #512da8;
  font-size: 15px;
  border-color: #512da8;
  color: #512da8;
}

.toggle-container {
  position: absolute;
  top: 0;
  left: 50%;
  width: 50%;
  height: 100%;
  overflow: hidden;
  transition: all 0.6s ease-in-out;
  border-radius: 150px 0 0 100px;
  z-index: 1000;
}

.container.active .toggle-container {
  transform: translateX(-100%);
  border-radius: 0 150px 100px 0;
}

.toggle {
  background-color: #512da8;
  height: 100%;
  background: linear-gradient(to right, #5c6bc0, #512da8);
  color: #fff;
  position: relative;
  left: -100%;
  height: 100%;
  width: 200%;
  transform: translateX(0);
  transition: all 0.6s ease-in-out;
}

.container.active .toggle {
  transform: translateX(50%);
}

.toggle-panel {
  position: absolute;
  width: 50%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 0 30px;
  text-align: center;
  top: 0;
  transform: translateX(0);
  transition: all 0.6s ease-in-out;
}

.toggle-left {
  transform: translateX(-200%);
}

.container.active .toggle-left {
  transform: translateX(0);
}

.toggle-right {
  right: 0;
  transform: translateX(0);
}

.container.active .toggle-right {
  transform: translateX(200%);
}
.formButton {
  position: relative;
  background-color: #512da8;
  border-radius: 4em;

  font-size: 14px;
  color: white;
  padding: 10px 45px;
  margin-top: 10px;
  cursor: pointer;
  user-select: none;
  text-align: center;
  letter-spacing: 0.5px;
  text-decoration: none;
  cursor: pointer;
  transition-duration: 0.4s;
  -webkit-transition-duration: 0.4s; /* Safari */
}
.formButton:hover {
    
 transform:scale(1.01) ;

}


.formButton:after {
  content: "";
  display: block;
  position: absolute;
  border-radius: 4em;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: all 0.5s;
  box-shadow: 0 0 10px 30px #512da8;
}

.formButton:active:after {
  box-shadow: 0 0 0 0 white;
  position: absolute;
  border-radius: 4em;
  left: 0;
  top: 0;
  opacity: 1;
  transition: 0s;
}

.formButton:active {
  top: 1px;
}
</style>
