<template>
  <el-form
    :rules="forgetPasswordFormRules"
    :model="forgetPasswordForm"
    ref="forgetPasswordForm"
    class="form"
    dir="rtl"
  >
    <h3 class="form__title">استعادة كلمة السر</h3>
    <p class="form__description">
      قم بأدخال البريد الالكتروني أو رقم الجوال الخاص بك
    </p>

    <el-form-item prop="email" label=" ">
      <el-input
        v-model="forgetPasswordForm.email"
        placeholder="البريد الالكتروني / رقم الجوال"
        required
      />
    </el-form-item>

    <button
      type="submit"
      class="mt-4 btn btn--pink"
      @click.prevent="forgetPassword"
    >
      ارسال
    </button>
    <button
      type="submit"
      class="mt-3 btn btn--white"
      @click.prevent="goToLogin"
    >
      رجوع
    </button>
  </el-form>
</template>

<script>
export default {
  layout: "auth",
  data() {
    return {
      forgetPasswordForm: {
        email: "",
      },
      forgetPasswordFormRules: {
        email: [{ required: true, message: "يجب ادخال البريد الالكتروني" }],
      },
    };
  },
  methods: {
    forgetPassword() {
      this.$refs.forgetPasswordForm.validate((valid) => {
        if (valid) {
          const loading = this.$loading({
            lock: true,
            text: "Loading",
            spinner: "el-icon-loading",
            background: "rgba(0, 0, 0, 0.7)",
          });
          console.log(this.forgetPasswordForm);
          try {
            this.$message.success("تم الارسال بنجاح");
          } catch (error) {
            this.$message.error("حدث خطأ ما");
          } finally {
            loading.close();
          }
        }
      });
    },
    goToLogin() {
      this.$router.push("/auth/login");
    },
  },
};
</script>

<style></style>
