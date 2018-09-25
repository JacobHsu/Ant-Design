<template>
  <div class="my-3">
    <a-checkbox>顯示紅牌</a-checkbox>
    <a-checkbox>顯示黃牌</a-checkbox>
    <a-radio-group defaultValue="0">
      <a-radio-button value="0">繁體</a-radio-button>
      <a-radio-button value="1">简体</a-radio-button>
      <a-radio-button value="2">English</a-radio-button>
    </a-radio-group>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>