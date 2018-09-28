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
        <span slot="score" slot-scope="text, record">{{ record.homeScore }} - {{ record.guestScore }}</span>
        <span slot="halfScore" slot-scope="text, record">{{ record.homeHalfScore }} - {{ record.guestHalfScore }}</span>
      </a-table>
    </div>
  </div>
</template>

<script>

import reqwest from 'reqwest';

const columns = [{
    title: '賽事',
    dataIndex: 'league[1]',
}, {
    title: '時間',
    dataIndex: 'matchTime',
}, {
    title: '主隊',
    dataIndex: 'home[1]',
}, {
    title: '全場比分',
    dataIndex: 'score',
    scopedSlots: { customRender: 'score' },
}, {
    title: '客隊',
    dataIndex: 'guest[1]',
}, {
    title: '半場比分',
    dataIndex: 'halfScore',
    scopedSlots: { customRender: 'halfScore' },
}];

export default {
  name: 'HelloWorld',
  data() {
    return {
      data: [],
      columns,
    }
  },
  mounted() {
      this.fetch();
  },
  methods: {
    fetch () {
        this.loading = true
        reqwest({
            url: '/worldcup_2018.json',
            method: 'get',
            type: 'json',
        }).then((data) => {
            this.loading = false
            this.data = data.results;
        });
    },
  },
  props: {
    msg: String
  }
}


</script>