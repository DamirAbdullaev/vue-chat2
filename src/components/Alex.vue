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
        <div :class="{active: base.name == 'Александр'}" v-for="(base, i) in basees" :key="i" class="phone__main_sms">
          <p class="phone__main_sms-text">
            <img v-if="base.url" :src="base.url" alt="test_img">{{ base.text }}</p>
          <span class="phone__main_sms-time">{{ base.time }}</span>
        </div>
      </div>
  
      <div class="phone__footer">
        <form @submit.prevent="" class="phone__footer_form">
          <textarea ref="messageTextarea" v-model="message" placeholder="Написать сообщение..." :style="{ height: textareaHeight }"></textarea>
          <button @click="sendDataToParent" v-if="message"><img src="@/assets/img/send.svg" alt="send"></button>
          <button @click="$emit('toggle', true), $emit('name', 'Александр')" v-else><img src="@/assets/img/photoaparat.svg" alt="photoaparat"></button>
        </form>
      </div>
    </div>
  </template>
   
  <script>
  export default {
    data() {
      return {
        name: 'Александр',
        url: '',
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
        },

        sendDataToParent() {
            this.basees.push({ name: this.name, url: this.url, time: new Date().getHours() + ':' + new Date().getMinutes(), text: this.message });
            this.message = ''
        },
    },

    watch: {
      message() {
        this.$nextTick(this.updateTextareaHeight);
      }
    },

    props: {
        basees: {
            typeof: Array
        },
    }
  };

  </script>
  
  <style scoped>
  </style>
  