<template>
  <div class="body">
    <Alex :basees="basees" @toggle="toggle = $event" @name="name = $event"/>
    <Eva :basees="basees" @toggle="toggle = $event" @name="name = $event"/>
    <Modal :basees="basees" :toggle="toggle" @toggle="toggle = $event" :name="name"/>
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

      toggle: false,
      name: '',
    }
  },

  methods: {

  },

}
</script>

<style lang="scss" scoped></style>