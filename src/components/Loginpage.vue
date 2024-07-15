<template>
  <div :class="{ container: true, active: isActive }" id="container">
    <div class="form-container sign-up">
      <form>
        <h1 class="header" style="color: #89388d;">Καλωσορίσατε στο Iolife </h1>
        <div class="social-icons">
          <p class="sub-header" style="color: #c2c2c7;">Παρακαλώ εισάγετε τα στοιχεία σας</p>
        </div>
        <input type="email" placeholder="Διεύθυνση ηλεκτρονικού ταχυδρομείου" />
        <input type="password" placeholder="Κωδικός Πρόσβασης" />
        <input type="password" placeholder="Επιβεβαίωση Κωδικού Πρόσβασης" />
        <button class="formButton" style="background-color: #89388d;" type="submit" @click.prevent="register()">
          Sign Up
        </button>
        <p>
          Already have an account?
          <a href="#" @click.prevent="changeForm" style="color: #89388d;text-decoration: underline;">Sign In</a>
        </p>
      </form>
    </div>
    <div class="form-container sign-in">
      <form>
        <h1 class="header" style="color: #89388d;">Καλωσορίσατε στο Iolife </h1>
        <div class="social-icons">
          <p class="sub-header" style="color: #c2c2c7;">Παρακαλώ εισάγετε τα στοιχεία σας</p>
        </div>
        <input v-model="input.email" type="email" placeholder="Διεύθυνση ηλεκτρονικού ταχυδρομείου" />
        <input v-model="input.password" type="password" placeholder="Κωδικός Πρόσβασης" />
        <div class="flex-container">
          <input type="checkbox" style="border: solid 2px #89388d;margin-right: 7px;">
          <p style="text-wrap: nowrap;margin-right: 12px;margin-top: 20px;">Να με θυμάσαι</p>
          <a href="#" class="underline" style="">Forgot Your Password?</a>
        </div>
        <button class="formButton" style="background-color: #89388d;" type="submit" @click.prevent="login()">
          Sign In
        </button>
        <p>
          Don't have an account?
          <a href="#" @click.prevent="changeForm" style="color: #89388d;text-decoration: underline;">Sign Up</a>
        </p>
      </form>
    </div>
    <div class="toggle-container">
      <div class="toggle">
        <div class="toggle-panel toggle-left welcome-back">
          <!-- <h1>Welcome Back!</h1>
          <p>Enter your personal details to use all of site features</p> -->
          <!-- <button class="btn" id="login" @click="changeForm">Sign In</button> -->
        </div>
        <div class="toggle-panel toggle-right">
          <!-- <h1>Hello, Friend!</h1>
          <p>Register with your personal details to use all of site features</p> -->
          <!-- <button class="btn" style="background-color: #89388d;" id="register" @click="changeForm">Sign Up</button> -->
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

.header {
  font-size: 24px;
  font-weight: 600;
  line-height: normal;
  letter-spacing: -0.72px;
}
.sub-header {
  font-weight: 400;
  font-size: 17px;
  line-height: 20px;
  color: rgba(45, 45, 61, 0.45);
}
.flex-container {
            display: flex;
            align-items: center;
            font-family: Arial, sans-serif;
            font-size: 14px;
            color: #89388d;
        }

.flex-container p {
            margin-right: 15px;
            color: #89388d;
        }
.flex-container a {
            margin-left: 20px;
            color: #89388d;
            text-decoration: underline;
            white-space: nowrap;
        }
body {
  background-color: #e1bee7; /* Light purple background */
  background: linear-gradient(to right, #ce93d8, #e1bee7); /* Gradient with purple tones */
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
}

.underline:hover {
  text-decoration: underline;
}
.container form p {
  font-size: 14px;
  color: #89388d;
  margin-top: 10px;
}

.container form a {
  color: #89388d;
  text-decoration: none;
  margin-left: 5px;
}

.container form a:hover {
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
  background-color: #7b1fa2; /* Purple background for buttons */
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
  background-color: #89388d; /* Darker purple background for buttons */
  border-color: transparent;
  color: #fff;
  position: absolute;
  bottom: 30px; /* Position buttons lower */
}

#login {
  left: 30%;
}

#register {
  right: 25%;
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
  color: #7b1fa2; /* Purple for hover color */
  font-size: 15px;
  border-color: #7b1fa2; /* Purple for hover border */
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
  background-color: #7b1fa2; /* Purple background */
  height: 100%;
  background: linear-gradient(to right, #8e24aa, #7b1fa2); /* Gradient with purple tones */
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
  background-image: url("/src/assets/background.jpg");
  background-size: cover;
  background-position: center;
}

.container.active .toggle-left {
  transform: translateX(0);
}

.toggle-right {
  right: 0;
  transform: translateX(0);
  background-image: url("/src/assets/background.jpg");
  background-size: cover;
  background-position: center;
}

.container.active .toggle-right {
  transform: translateX(200%);
}

.formButton {
  position: relative;
  background-color: #89388d; /* Purple background for form buttons */
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
  transition-duration: 0.4s;
  -webkit-transition-duration: 0.4s; /* Safari */
}

.formButton:hover {
  transform: scale(1.01);
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
  box-shadow: 0 0 10px 30px #7b1fa2; /* Purple shadow */
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
