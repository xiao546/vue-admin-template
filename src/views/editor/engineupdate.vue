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
    </el-row>

    <el-row>
    <el-select v-model="engineTypeValue" placeholder="请选择引擎类型">
        <el-option
          v-for="item in engineType"
          :key="item.value"
          :label="item.label"
          :value="item.value">
        </el-option>
      </el-select>
    <el-select v-model="engineTypeVersionValue" placeholder="请选择引擎版本">
        <el-option
          v-for="item in engineTypeVersion"
          :key="item.value"
          :label="item.label"
          :value="item.value">
        </el-option>
      </el-select>
    </el-row>

    <el-row>
      <el-button type="primary">引擎更新</el-button>
    </el-row>
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

      engineType: [{
          value: '稳定版',
          label: '稳定版'
        }, {
          value: '开发版',
          label: '开发版'
        }],
      engineTypeValue: '稳定版',
      engineTypeVersion: [{
          value: '0.0.1',
          label: '0.0.1'
        }],
      engineTypeVersionValue: ''
    }
  },

  methods: {
  }
}
</script>
