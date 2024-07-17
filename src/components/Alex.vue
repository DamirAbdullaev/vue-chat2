<template>
    <div class="phone">
      <div class="phone__header">
        <img src="@/assets/img/alex.svg" alt="alex">
        <div class="phone__header_info">
          <p class="phone__header_info-name">Александр</p>
          <span class="phone__header_info-status">Онлайн</span>
        </div>
      </div>
  
      <div class="phone__main">
        <div class="phone__main_sms">
          <p class="phone__main_sms-text">
            <img src="@/assets/img/test_img.jpg" alt="test_img">
            Привет. Как дела? Где ты изучаешь программирование?</p>
          <span class="phone__main_sms-time">12:21</span>
        </div>
        <div class="phone__main_sms active">
          <p class="phone__main_sms-text">
            <img src="@/assets/img/test_img.jpg" alt="test_img">
            Привет. Нормально. Как у тебя дела? Я учусь в учебном центре PROWEB</p>
          <span class="phone__main_sms-time">12:21</span>
        </div>
      </div>
  
      <div class="phone__footer">
        <form class="phone__footer_form">
          <textarea ref="messageTextarea" v-model="message" placeholder="Написать сообщение..." :style="{ height: textareaHeight }"></textarea>
          <button v-if="message"><img src="@/assets/img/send.svg" alt="send"></button>
          <button v-else><img src="@/assets/img/photoaparat.svg" alt="photoaparat"></button>
        </form>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        message: '',
        textareaHeight: '56px', 
        maxTextareaHeight: 150,
      };
    },
    
    methods: {
        updateTextareaHeight() {
            const textarea = this.$refs.messageTextarea;
            textarea.style.height = '56px';
            textarea.style.height = Math.min(textarea.scrollHeight, this.maxTextareaHeight) + 'px';
            this.textareaHeight = textarea.style.height;
        }
    },

    watch: {
      message() {
        this.$nextTick(this.updateTextareaHeight);
      }
    }
  };

  </script>
  
  <style scoped>
  </style>
  