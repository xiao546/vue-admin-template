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
         <el-button type="primary">提交</el-button>
    </el-row>
    <el-table
      :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
      style="width: 100%">
      <el-table-column
        label="标题"
        prop="title">
      </el-table-column>
      <el-table-column
        label="详情"
        prop="info">
      </el-table-column>
      <el-table-column
        label="wiki"
        prop="wiki">
      </el-table-column>
      <el-table-column
        label="图片"
        prop="picture">
      </el-table-column>
      <el-table-column
        align="right">
        <template slot="header" slot-scope="scope">
          <el-input
            v-model="search"
            size="mini"
            placeholder="输入关键字搜索"/>
          <el-button size="mini" type="primary">添加</el-button>
        </template>
        <template slot-scope="scope">
          <el-button
            size="mini"
            @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
          <el-button
            size="mini"
            type="danger"
            @click="handleDelete(scope.$index, scope.row)">删除</el-button>
        </template>
      </el-table-column>
    </el-table>
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

        tableData: [{
          title: '2016-05-02',
          info: 'test',
          wiki: 'test',
          picture: 'test'
        }, {
          title: '2016-05-04',
          info: 'test1',
          wiki: 'test2',
          picture: 'test3'
        }],
        search: ''
      }
    },
    methods: {
      handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      }
    },
  }
</script>