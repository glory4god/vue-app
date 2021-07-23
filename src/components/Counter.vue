<template>
  <h2>COUNTER</h2>
  <h4>count = {{ count }}</h4>
  <h4 v-if="count > 5">count = {{ count }} ( if count>5 show! )</h4>
  <h4>counter is odd? {{ oddCheck }}</h4>
  <h4>
    <span>{{ isShow ? 'show!!' : 'notShow!!' }}</span
    ><span> : boolean state TEST</span>
  </h4>
  <button @click="increase">up</button>
  <button @click="twiceCount">*2</button>
  <button @click="decrease">down</button>
  <button @click="isShowHandler">show?</button>
  <button @click="reset">reset</button>
</template>
<script>
export default {
  name: 'Counter',
  // components 에선 data 선언할 때, 함수 선언 해야함
  data: () => ({
    count: 0,
    isShow: true,
  }),
  methods: {
    increase: function () {
      return (this.count += 1);
    },
    decrease: function () {
      return (this.count -= 1);
    },
    isShowHandler: function () {
      return (this.isShow = !this.isShow);
    },
    reset: function () {
      this.count = 0;
      this.isShow = true;
    },
    twiceCount: function () {
      return (this.count *= 2);
    },
  },
  computed: {
    oddCheck: function () {
      if (this.count % 2 === 0) {
        return true;
      }
      return false;
    },
  },
};
</script>
