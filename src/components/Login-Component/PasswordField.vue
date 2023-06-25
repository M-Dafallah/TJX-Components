<template>
  <div class="passwordComp">
    <div class="pass">
      <label for="password">Password</label>
      <span class="password-icon">
        <input
          id="password"
          type="password"
          name="password"
          placeholder="Enter Password here"
        />

        <img
          tabindex="0"
          role="button"
          aria-label="Show / Hide password Icon "
          :aria-roledescription="
            showPassword
              ? 'Press enter to hide password '
              : 'Press enter to show password '
          "
          @keydown.enter="togglePasswordView"
          @click="togglePasswordView"
          class="show-icon"
          :src="
            showPassword
              ? 'https://cdn.icon-icons.com/icons2/2406/PNG/512/eye_slash_visible_hide_hidden_show_icon_145987.png'
              : 'https://cdn.icon-icons.com/icons2/2406/PNG/512/eye_visible_hide_hidden_show_icon_145988.png'
          "
        />
      </span>
    </div>

    <div class="confirmPass">
      <label for="confirmPass">Confirm Password</label>
      <span class="password-icon">
        <input
          id="confirmPassword"
          type="password"
          name="confirmPass"
          placeholder="Confirm Password here"
        />

        <img
          tabindex="0"
          role="button"
          aria-label="Show / Hide confirm password Icon "
          :aria-roledescription="
            showPasswordConfirm
              ? 'Press enter to hide password '
              : 'Press enter to show password '
          "
          @keydown.enter="togglePasswordConfirmView"
          @click="togglePasswordConfirmView"
          class="show-icon"
          :src="
            showPasswordConfirm
              ? 'https://cdn.icon-icons.com/icons2/2406/PNG/512/eye_slash_visible_hide_hidden_show_icon_145987.png'
              : 'https://cdn.icon-icons.com/icons2/2406/PNG/512/eye_visible_hide_hidden_show_icon_145988.png'
          "
        />
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "PasswordField",
  data() {
    let showPassword = false;
    let showPasswordConfirm = false;

    return {
      showPassword,
      showPasswordConfirm,
    };
  },
  methods: {
    togglePasswordView() {
      console.log(this.showPassword);
      this.showPassword = !this.showPassword;

      let passwordInput = document.getElementById("password");

      if (this.showPassword) {
        passwordInput.type = "text";
      } else {
        passwordInput.type = "password";
      }
    },
    togglePasswordConfirmView() {
      this.showPasswordConfirm = !this.showPasswordConfirm;

      let passwordInput = document.getElementById("confirmPassword");

      if (this.showPasswordConfirm) {
        passwordInput.type = "text";
      } else {
        passwordInput.type = "password";
      }
    },
  },
};
</script>

<style>
.passwordComp {
  margin-top: 17px;
}

.pass,
.confirmPass {
  display: flex;
  flex-direction: column;
}

.pass label,
.confirmPass label {
  align-self: flex-start;
  margin-bottom: 10px;
}

.pass input,
.confirmPass input {
  padding: 3px;
}

.confirmPass label {
  margin-top: 15px;
}

.show-icon {
  /*background: url("https://cdn.icon-icons.com/icons2/2406/PNG/512/eye_visible_hide_hidden_show_icon_145988.png");*/
  height: 20px;
  width: 20px;
  padding-top: 1px;
  margin-top: 2px;
  display: block;
  border: 1px solid lightgray;

  /* Other styles here */
}

.show-icon:hover {
  cursor: pointer;
}

.password-icon {
  display: flex;
}

.password-icon input {
  float: left;
}

.password-icon img {
  float: right;
}
</style>
