<template>
  <div class="login">
    <h2 tabindex="0">Accessible Login Component</h2>
    <div class="email">
      <label for="emailField">Email</label>
      <input name="emailField" type="email" placeholder="Enter email here" />
    </div>

    <div class="pass" tabindex="0">
      <PasswordField id="passwordField" />
    </div>
    <section class="btn-wrapper" tabindex="0">
      <button class="reg-btn">Register</button>
    </section>
  </div>
</template>

<script>
import PasswordField from "./PasswordField";
export default {
  name: "LoginMain",
  components: { PasswordField },
};
</script>

<style scoped>
.login {
  display: flex;
  flex-direction: column;
  border: 1px solid black;
  margin: 20px 10vh 20px 10vh;
  padding: 20px 30px 20px 30px;
}
.login h2 {
  font-weight: lighter;
}

.email {
  display: flex;
  flex-direction: column;
}

.email label {
  align-self: flex-start;
  margin-bottom: 10px;
}

.email input {
  margin-right: 15vw;
  padding: 5px;
}

.reg-btn {
  padding: 5px 30px 5px 30px;
  background: black;
  color: white;
  font-size: 20px;
  align-self: flex-start;
}

.btn-wrapper {
  margin-top: 25px;
  max-width: fit-content;
  max-height: fit-content;
}
</style>
