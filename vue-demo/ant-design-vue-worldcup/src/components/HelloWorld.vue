<template>
  <div class="my-3">
    <a-button type="primary">Primary</a-button>
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