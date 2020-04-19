<template>
  <div class="app-container">
    <el-row>
    <el-select v-model="editorValue" placeholder="请选择编辑器">
        <el-option
          v-for="item in editor"
          :key="item.value"
          :label="item.label"
          :value="item.value">
        </el-option>
      </el-select>
    <el-select v-model="editorTypeValue" placeholder="请选择版本">
        <el-option
          v-for="item in editortype"
          :key="item.value"
          :label="item.label"
          :value="item.value">
        </el-option>
      </el-select>
    <el-button type="primary">打包</el-button>
    </el-row>
    <br>
    <el-container>
      <el-header>svn更新日志</el-header>
      <el-main>
        <el-container>
          <el-header>上次打包后的更新</el-header>
          <el-main>
            <el-table :data="svnUpdateData">
              <el-table-column prop="version" label="版本" width="140"></el-table-column>
              <el-table-column prop="author" label="作者" width="120"></el-table-column>
              <el-table-column prop="date" label="日期" width="120"></el-table-column>
              <el-table-column prop="info" label="详情"></el-table-column>
            </el-table>
          </el-main>
        </el-container>
        <el-container>
          <el-header>最近更新日志</el-header>
          <el-main>
            
          </el-main>
        </el-container>
      </el-main>
    </el-container>
  </div>
</template>

<script>
export default {

  data() {
    return {
      editor: [{
          value: 'Mars',
          label: 'Mars'
        }, {
          value: 'BluePrint',
          label: '蓝图编辑器'
        }],
      editorValue: 'Mars',
      editortype: [{
          value: 'stable',
          label: '稳定版'
        }, {
          value: 'trunk',
          label: '开发版'
        }],
      editorTypeValue: 'stable',

      svnUpdateData: Array(2).fill({
        version: '12345',
        author: 'wsh',
        date: '2016-05-02',
        info: '测试',
      })
    }
  },

  methods: {
  }
}
</script>

<style>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    /* line-height: 160px; */
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>