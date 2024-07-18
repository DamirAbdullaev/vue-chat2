<template>
    <div v-if="toggle" class="modal" @click="$emit('toggle', false);">
      <div class="modal__block" @click.stop>
        <h2 class="modal__block-title">Отправить картинку</h2>
        
        <div class="modal__block_inputs">
          <label>
            <span>URL</span>
            <input v-model="url" placeholder="URL" type="text">
          </label>
          <label>
            <span>Комментарий</span>
            <input v-model="text" placeholder="Комментарий" type="text">
          </label>
        </div>
  
        <div class="modal__block_btn">
          <button @click="$emit('toggle', false)" class="cancel">Отмена</button>
          <button @click="sendDataToParent" class="send">ОТПРАВИТЬ</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
        return {
            url: '',
            text: '',
        }
    },

    methods: {
        sendDataToParent() {
            if (this.url) {
                this.basees.push({ name: this.name, url: this.url, time: new Date().getHours() + ':' + new Date().getMinutes(), text: this.text });
                this.url = '';
                this.text = '';

                this.$emit('toggle', false)
            }
        }
    },

    props: {
        basees: {
            typeof: Array
        },

      toggle: {
        typeof: Boolean
      },

      name: {
        typeof: String
      }
    },
  }
  </script>
  
  <style scoped>
  </style>
  