<template>
  <li>
    {{ stage }}, {{ result }} <button @click="$emit('remove')">remove</button>
    <!--  emit함수를 통해서 자식이 부모에게 변화시키는 데이터 보내는 느낌 -->
  </li>
</template>

<script>
export default {
  props: { stage: String, result: String },
};
</script>
