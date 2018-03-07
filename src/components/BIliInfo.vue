<template>
  <div>
    <el-table :data="data" stripe style="width: 100%">
      <el-table-column label="视频编号" width="140">
        <template slot-scope="scope">
          <a :href="scope.row.v_href">{{ scope.row.v_aid }}</a>
        </template>
      </el-table-column>
      <el-table-column prop="v_view" label="播放数" width="120">
      </el-table-column>
      <el-table-column prop="v_danmaku" label="弹幕数" width="120">
      </el-table-column>
      <el-table-column prop="v_reply" label="评论数" width="120">
      </el-table-column>
      <el-table-column prop="v_favorite" label="收藏数" width="120">
      </el-table-column>
      <el-table-column prop="v_coin" label="硬币数" width="120">
      </el-table-column>
      <el-table-column prop="v_share" label="分享数" width="120">
      </el-table-column>
      <el-table-column prop="v_name" label="视频名称">
      </el-table-column>
    </el-table>
  </div>

</template>

<script type="text/ecmascript-6">
export default {
  props: ['data']
};
</script>

<style scoped>
</style>
