<template>
  <div class="my-3">
    <div class="filter mb-3">
      <a-checkbox v-model="showRed">顯示紅牌</a-checkbox>
      <a-checkbox v-model="showYellow">顯示黃牌</a-checkbox>
      <a-radio-group defaultValue="0" v-model="lang">
        <a-radio-button value="0">繁體</a-radio-button>
        <a-radio-button value="1">简体</a-radio-button>
        <a-radio-button value="2">English</a-radio-button>
      </a-radio-group>
      <h1>{{ msg }}</h1>
    </div>
    <div>
      <a-table :columns="columns" :dataSource="data" :pagination="false" size="middle" :loading="loading">
        <span slot="matchTime" slot-scope="matchTime, record">{{ record.matchDate + " " + matchTime }}</span>
        <span slot="league" slot-scope="league">{{ league[lang] }}</span>
        <span slot="home" slot-scope="home, record">
          <a-badge v-show="showYellow" class="mr-1" :count="record.homeYellow" :numberStyle="{borderRadius:0, backgroundColor: 'yellow', color: '#999', boxShadow: '0 0 0 1px #d9d9d9 inset'}" />
          <a-badge v-show="showRed" :count="record.homeRed" :numberStyle="{borderRadius:0, backgroundColor: 'red', color: '#fff', boxShadow: '0 0 0 1px #d9d9d9 inset'}" />
          {{ home[lang] }}
        </span>
        <span slot="guest" slot-scope="guest, record"> 
          {{ guest[lang] }}
          <a-badge v-show="showRed" :count="record.guestRed" :numberStyle="{borderRadius:0, backgroundColor: 'red', color: '#fff', boxShadow: '0 0 0 1px #d9d9d9 inset'}" />
          <a-badge v-show="showYellow" class="ml-1" :count="record.guestYellow" :numberStyle="{borderRadius:0, backgroundColor: 'yellow', color: '#999', boxShadow: '0 0 0 1px #d9d9d9 inset'}" />
        </span>
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
    dataIndex: 'league',
    scopedSlots: { customRender: 'league' },
}, {
    title: '時間',
    dataIndex: 'matchTime',
    scopedSlots: { customRender: 'matchTime' },
    align: 'center',
}, {
    title: '主隊',
    dataIndex: 'home',
    scopedSlots: { customRender: 'home' },
    align: 'center',
}, {
    title: '全場比分',
    dataIndex: 'score',
    scopedSlots: { customRender: 'score' },
    align: 'center',
}, {
    title: '客隊',
    dataIndex: 'guest',
    scopedSlots: { customRender: 'guest' },
    align: 'center',
}, {
    title: '半場比分',
    dataIndex: 'halfScore',
    scopedSlots: { customRender: 'halfScore' },
    align: 'center',
}];

export default {
  name: 'HelloWorld',
  data() {
    return {
      data: [],
      columns,
      lang: 0,
      showRed: true,
      showYellow: true,
      loading: false,
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