<template>
  <div class="my-3">
    <div class="filter mb-3">
      <a-checkbox>顯示紅牌</a-checkbox>
      <a-checkbox>顯示黃牌</a-checkbox>
      <a-radio-group defaultValue="0">
        <a-radio-button value="0">繁體</a-radio-button>
        <a-radio-button value="1">简体</a-radio-button>
        <a-radio-button value="2">English</a-radio-button>
      </a-radio-group>
      <h1>{{ msg }}</h1>
    </div>
    <div>
      <a-table :columns="columns" :dataSource="data" :pagination="false" size="middle">
      </a-table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      data,
      columns,
    }
  },
  props: {
    msg: String
  }
}

const data = [{
  key: '1',
  name: '胡彦斌',
  age: 32,
  address: '西湖区湖底公园1号'
}, {
  key: '2',
  name: '胡彦祖',
  age: 42,
  address: '西湖区湖底公园1号'
}];

const columns = [{
  title: '姓名',
  dataIndex: 'name',
  key: 'name',
}, {
  title: '年龄',
  dataIndex: 'age',
  key: 'age',
}, {
  title: '住址',
  dataIndex: 'address',
  key: 'address',
}];
</script>