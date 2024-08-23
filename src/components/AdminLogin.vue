<script setup>
import { reactive, ref } from 'vue';
import { ElMessage } from 'element-plus';

const loginForm = reactive({
  username: '',
  password: '',
});

const loginRules = {
  username: [
    { required: true, message: 'Please enter your username', trigger: 'blur' },
  ],
  password: [
    { required: true, message: 'Please enter your password', trigger: 'blur' },
  ],
};

const loginFormRef = ref(null);

const handleLogin = () => {
  loginFormRef.value.validate((valid) => {
    if (valid) {
      // 处理登录逻辑，例如调用API
      ElMessage.success('Login successful!');
    } else {
      ElMessage.error('Please complete the form correctly');
      return false;
    }
  });
};
</script>

<template>
  <div class="login-container">
    <el-card class="login-card">
      <h3 class="login-title">Admin Login</h3>
      <el-form :model="loginForm" :rules="loginRules" ref="loginForm" label-width="100px">
        <el-form-item label="Username" prop="username">
          <el-input v-model="loginForm.username" placeholder="Enter your username"></el-input>
        </el-form-item>
        <el-form-item label="Password" prop="password">
          <el-input type="password" v-model="loginForm.password" placeholder="Enter your password"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="handleLogin">Login</el-button>
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>

<style scoped>
.login-container {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f5f5f5;
}

.login-card {
  padding: 20px;
  width: 400px;
  border-radius: 8px;
}

.login-title {
  text-align: center;
  margin-bottom: 20px;
}
</style>