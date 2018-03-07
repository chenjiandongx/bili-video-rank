<template>
  <div id="app">
    <v-header></v-header>
    <el-tabs type="border-card">
      <el-tab-pane label="播放数前 100">
        <bili-info :data="viewData"></bili-info>
      </el-tab-pane>
      <el-tab-pane label="弹幕数前 100">
        <bili-info :data="danmakuData"></bili-info>
      </el-tab-pane>
      <el-tab-pane label="评论数前 100">
        <bili-info :data="replyData"></bili-info>
      </el-tab-pane>
      <el-tab-pane label="收藏数前 100">
        <bili-info :data="favoriteData"></bili-info>
      </el-tab-pane>
      <el-tab-pane label="硬币数前 100">
        <bili-info :data="coinData"></bili-info>
      </el-tab-pane>
      <el-tab-pane label="分享数前 100">
        <bili-info :data="shareData"></bili-info>
      </el-tab-pane>
    </el-tabs>
    <div class="footer">
      <p align="center">
        Copyright &copy; 2018 chenjiandongx
      </p>
    </div>
  </div>
</template>

<script>
import BiliInfo from './components/BIliInfo';
import Header from './components/Header';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    'bili-info': BiliInfo,
    'v-header': Header
  },
  data() {
    return {
      cols: ['v_view', 'v_danmaku', 'v_reply', 'v_favorite', 'v_coin', 'v_share'],
      viewData: [],
      danmakuData: [],
      replyData: [],
      favoriteData: [],
      coinData: [],
      shareData: []
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      let i = 0;
      let url = 'https://raw.githubusercontent.com/chenjiandongx/bili-spider/master/json/';
      axios.get(url + this.cols[i++] + '.json').then(response => {
        this.viewData = response.data;
      });
      axios.get(url + this.cols[i++] + '.json').then(response => {
        this.danmakuData = response.data;
      });
      axios.get(url + this.cols[i++] + '.json').then(response => {
        this.replyData = response.data;
      });
      axios.get(url + this.cols[i++] + '.json').then(response => {
        this.favoriteData = response.data;
      });
      axios.get(url + this.cols[i++] + '.json').then(response => {
        this.coinData = response.data;
      });
      axios.get(url + this.cols[i++] + '.json').then(response => {
        this.shareData = response.data;
      });
    }
  }
};
</script>

<style scoped>
  .footer p {
    margin-top: 20px;
    color:#878B91;
  }
</style>
