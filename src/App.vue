<template>
  <div class="body">
    <Alex :basees="basees" />
    <Eva :basees="basees" />
    <Modal />
  </div>
</template>

<script>
import Alex from './components/Alex.vue';
import Eva from './components/Eva.vue';
import Modal from './components/Modal.vue';
export default {
  components: { Alex, Eva, Modal },


  data() {
    return {
      basees: [
        { name: 'Ева', url: '', text: 'Привет. Как дела? Где ты изучаешь программирование?', time: '13:23' },
        { name: 'Александр', url: '', text: 'Привет. Нормально. Как у тебя дела? Я учусь в учебном центре PROWEB', time: '13:23' },
      ],
    }
  },

  methods: {

  },

}
</script>

<style lang="scss" scoped></style>