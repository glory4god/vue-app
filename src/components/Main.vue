<template>
  <h2>msg : {{ msg }}</h2>
  <div>computed : {{ shortMessage }}</div>
  <div>{{ now }}</div>
  <div id="example-1" v-if="awesome">Vue is awesome!</div>
  <div v-else>no, bbbb</div>
</template>

<script>
export default {
  // vue 파일의 컴포넌트화는 이런식으로 하는듯?!!?!?!
  name: 'Main',
  props: {
    msg: String,
  },

  // computed 를 통해 복잡한 로직을 함수로 리턴해주기!
  computed: {
    shortMessage: function () {
      return this.msg.substring(10);
    },
    now: function () {
      return new Date().toString().substring(0, 15);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
