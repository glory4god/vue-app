<template>
  <h2>Gugudan</h2>
  <button @click="reset">시작하기</button>
  <form v-on:submit.prevent="addList">
    <h3>{{ first }} * {{ second }} = {{ temp }}</h3>
    <input
      v-model="temp"
      @keydown.enter.prevent="addList"
      type="number"
      id="gugudan-input"
    />
    <button>Add</button>
  </form>
  <div>score : {{ score }}</div>
  <!-- props 는 v-bind로 넘겨야 넘어감! -->
  <RecordList
    v-for="(list, idx) in recordList"
    v-bind:key="idx"
    v-bind:stage="list.stage"
    v-bind:result="list.result"
    @remove="remove(idx)"
  />
  <!-- @remove 를 통해 remove라는 메소드가 어떤걸 의미하는지 전달!!!! 아래 함수로 바꿔도 된다 -->
  <!-- @remove="recordList.splice(index, 1)" -->
</template>

<script>
import RecordList from './ReportList.vue';
export default {
  name: 'Gugudan',
  components: {
    RecordList,
  },
  data: () => ({
    first: 0,
    second: 0,
    temp: null,
    score: 0,
    recordList: [],
  }),
  methods: {
    reset: function () {
      this.first = Math.ceil(Math.random() * 9);
      this.second = Math.ceil(Math.random() * 9);
      this.temp = null;
    },
    addList: function () {
      if (this.temp === null || this.temp === '') {
        alert('입력하세요');
      } else {
        if (this.first * this.second === +this.temp) {
          this.score += 1;
          this.recordList.push({
            stage: this.first + ' X ' + this.second + ' = ' + this.temp,
            result: '정답',
          });
        } else {
          this.recordList.push({
            stage: this.first + ' X ' + this.second + ' = ' + this.temp,
            result: '땡',
          });
        }
        console.log(this.first * this.second, +this.temp);
        this.reset();
      }
    },
    remove(idx) {
      this.recordList.splice(idx, 1);
    },
  },
};
</script>
