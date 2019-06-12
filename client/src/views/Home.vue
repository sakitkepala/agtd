<template>
  <el-container>
    <el-header></el-header>

    <el-main>
      <div class="container-center">
        <h2>Welcome!</h2>
        <div>Enter your email address to start free trial</div>

        <div v-if="error" class="error">
          {{ error }}
        </div>

        <el-form ref="form" :model="form">
          <el-form-item>
            <label>Email</label>
            <el-input v-model="form.email" placeholder="Email"></el-input>
          </el-form-item>

          <el-form-item>
            <el-button type="primary">Create my AGTD account</el-button>
          </el-form-item>
        </el-form>

        <div>
          <span>Already have an AGTD account?</span>
          <router-link :to="{name: 'login'}" class="link">Log in</router-link>
        </div>

        <div v-if="submitted">
          <div>Thank you!</div>
          <div>Please check your email.</div>
        </div>
      </div>
    </el-main>
  </el-container>
</template>

<script>
export default {
  data() {
    return {
      submitted: false,
      error: false,
      form: {
        email: '',
      }
    }
  }
}
</script>

<style scoped lang="scss">
.el-button {
  width: 100%;
}

.error {
  padding-top: 10px;
}
</style>
