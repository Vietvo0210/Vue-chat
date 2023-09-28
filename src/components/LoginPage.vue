<template>
  <div>
    <h2>Đăng nhập</h2>
    <form @submit.prevent="login" v-if="!loggedIn">
      <div>
        <label for="username">Tài khoản:</label>
        <input type="text" id="username" v-model="username" required>
      </div>
      <div>
        <label for="password">Mật khẩu:</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <div>
        <button type="submit">Đăng nhập</button>
      </div>
    </form>
    <ChatPage v-else />
  </div>
</template>

<script setup>
import { ref } from "vue";
import ChatPage from "@/components/ChatPage.vue";

const username = ref("");
const password = ref("");
const loggedIn = ref(false);

const login = () => {
  if (username.value === "viet" && password.value === "123") {
    loggedIn.value = true;
  }
};
</script>
