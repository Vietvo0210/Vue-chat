<template>
  <div>
    <h2>Chat</h2>
    <!-- Hiển thị danh sách tin nhắn -->
    <div class="message-list">
      <div v-for="(message, index) in messages" :key="index">
        {{ message.sender }}: {{ message.text }}
      </div>
    </div>

    <!-- Hộp nhập tin nhắn -->
    <div class="message-input">
      <input type="text" v-model="newMessage" @keyup.enter="sendMessage" placeholder="Nhập tin nhắn...">
      <button @click="sendMessage">Gửi</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatPage',
  data() {
    return {
      newMessage: '',
      messages: [], // Danh sách tin nhắn
    };
  },
  methods: {
    sendMessage() {
      // Gửi tin nhắn và thêm tin nhắn mới vào danh sách
      if (this.newMessage.trim() === '') return;

      this.messages.push({
        text: this.newMessage,
        sender: 'Bạn', // Tên của người gửi
      });

      this.newMessage = ''; // Xóa nội dung hộp nhập tin nhắn
    },
  },
};
</script>
