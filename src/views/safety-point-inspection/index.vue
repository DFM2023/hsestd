<template>

  <div>
    <el-card>
    <div>
      <el-button type="primary" @click:="create">新增</el-button>
      <el-button type="primary" @click:="del">删除</el-button>
      <el-button type="primary" @click:="audit">提交</el-button>
      <el-button type="primary" @click:="upload">图文附件</el-button>
    </div>
    <el-input v-model="input" placeholder="请输入内容"></el-input>

    <el-table
      :data="tableData"
      style="width: 100%"
    >
      <template v-for="(item ,i) in tableHeader">
        <el-table-column
          v-if="item.type === 'selection'"
          type="selection"
          width="55"
        />
        <el-table-column
          :prop="item.prop"
          :label="item.label"
          :width="item.width"
        />
      </template>
    </el-table>
    </el-card>
    <!-- <div v-for="(item,index) in tableHeader"></div> -->
  </div>
</template>

<script>
import api from './api' // 引入api文件，里面含了接口
export default {
  components: {

  },
  props: {

  },
  data() {
    return {
      tableHeader: [
        {
          type: 'selection'
        },
        {
          prop: 'safe_insp__audit',
          label: '巡检编号',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_code',
          label: '巡检名称',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_name',
          label: '巡检状态',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_date',
          label: '巡检日期',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_man',
          label: '巡检人员',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_times',
          label: '巡检频率',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_memo',
          label: '备注',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_ed',
          label: '已巡检数量',
          width: '200px'
        },
        {
          prop: 'safe_insp__insp_ing',
          label: '待巡检数量',
          width: '200px'
        },
        {
          prop: 'asafe_insp__insp_non',
          label: '不合格数量',
          width: '200px'
        },
        {
          prop: 'safe_insp_audit',
          label: '单据状态',
          width: '200px'
        }
      ],
      tableData: [],
      pager: {
        pageNo: 0,
        pageSize: 10,
        total: 0
      },
      whereSql: ''
    }
  },
  computed: {

  },
  watch: {

  },
  created() {
    this.getList()
  },
  mounted() {

  },
  methods: {
    create() {},
    del() {},
    audit() {},
    upload() {},
    miss() {},
    getList() {  
      api.getData1(
      ).then(data => {
        this.tableData = data.data.root
      })
    }
  }
}

</script>

<style scoped lang="scss">

</style>
