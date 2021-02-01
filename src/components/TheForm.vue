<template>
  <div class="the-form">
    <a-form-model
      ref="ruleForm"
      :model="formInput"
      :rules="rules"
      class="login-form"
    >
      <a-form-model-item label="Email" ref="email" prop="email">
        <a-input
          v-model="formInput.email"
          @blur="
            () => {
              $refs.email.onFieldBlur();
            }
          "
          type="email"
        >
        </a-input>
      </a-form-model-item>
      <a-form-model-item label="Password" ref="password" prop="password">
        <a-input
          v-model="formInput.password"
          @blur="
            () => {
              $refs.password.onFieldBlur();
            }
          "
          type="password"
          autocomplete="off"
        >
        </a-input>
        <a class="the-form__link" href="#">Forgot your password?</a>
      </a-form-model-item>
      <a-form-model-item>
        <a-button
          type="primary"
          html-type="submit"
          class="login-form-button"
          :disabled="formInput.email === '' || formInput.password === ''"
          @click="onSubmit"
        >
          Sign in
        </a-button>
      </a-form-model-item>
    </a-form-model>
  </div>
</template>
<script>
export default {
  name: "TheForm",
  data() {
    return {
      formInput: {
        email: "",
        password: "",
      },
      rules: {
        email: [
          {
            required: true,
            message: "Invalid email",
            trigger: "blur",
          },
        ],
        password: [
          {
            required: true,
            min: 3,
            max: 10,
            message: "Invalid format too short",
            trigger: "blur",
          },
        ],
      },
    };
  },

  methods: {
    onSubmit() {
      this.$refs.ruleForm.validate((valid) => {
        if (valid) {
          alert("Form sent!");
          this.$refs.ruleForm.resetFields();
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
  },
};
</script>
<style lang="scss">
.the-form {
  min-width: 420px;
  .ant-form-item:not(:last-child) {
    margin-bottom: 30px;
  }
  .ant-col input {
    height: 54px;
  }
  .login-form-button {
    width: 100%;
    height: 56px;
    &:hover {
      background-color: $button-blue;
    }
  }
  &__link {
    position: absolute;
    right: 20px;
    bottom: -10px;
    color: $button-grey;
  }
  .has-success input {
    border-color: #008000;
  }
}
.ant-input {
  border-color: inherit;
  &:visited,
  &:active,
  &:focus {
    border-color: $button-blue;
  }
}
.ant-form-item-label > label::after,
label::before {
  display: none !important;
}
.ant-form-explain {
  font-size: 12px !important;
  transform: translateY(-72px);
  text-align: right;
  transition: none !important;
}
</style>