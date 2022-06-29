<template>
  <el-form
    :rules="loginFormRules"
    :model="loginForm"
    ref="loginForm"
    class="form"
    dir="rtl"
  >
    <h3 class="form__title">تسجيل الدخول</h3>
    <p class="form__description">قم بأدخال البيانات للدخول</p>

    <el-form-item prop="username" label=" ">
      <el-input
        v-model="loginForm.username"
        placeholder="اسم المستخدم"
        type="text"
      />
    </el-form-item>

    <el-form-item prop="password" label=" ">
      <el-input
        v-model="loginForm.password"
        placeholder="كلمة المرور"
        type="password"
        show-password
      />
    </el-form-item>

    <nuxt-link to="/auth/forget_password">هل نسيت كلمه السر؟</nuxt-link>

    <button type="submit" class="btn btn--pink" @click.prevent="login">
      تسجيل الدخول
    </button>
  </el-form>
</template>

<script>
export default {
  layout: "auth",
  // middleware: "loggedIn",
  data() {
    return {
      loginForm: {
        username: "",
        password: "",
      },
      loginFormRules: {
        username: [{ required: true, message: "يجب ادخال اسم المستخدم" }],
        password: [{ required: true, message: "يجب ادخال الرقم السري" }],
      },
    };
  },
  methods: {
    login() {
      this.$refs.loginForm.validate(async (valid) => {
        if (valid) {
          const loading = this.$loading({
            lock: true,
            text: "Loading",
            spinner: "el-icon-loading",
            background: "rgba(0, 0, 0, 0.7)",
          });
          console.log(this.loginForm);
          try {
            await this.$auth.loginWith("local", { data: this.loginForm });
            this.$router.push("/");
            this.$message.success("تم تسجيل الدخول بنجاح");
          } catch (error) {
            this.$message.error("خطأ في تسجيل الدخول");
          } finally {
            loading.close();
          }
        }
      });
    },
  },
};
</script>

<style></style>
