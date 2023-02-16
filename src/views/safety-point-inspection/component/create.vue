<template>
    <div>
      <el-form label-width="180px" :model="form">
        <el-row>
          <el-col :span="7">
            <el-form-item label="巡检单编号" >
              <el-input v-model="form.safe_insp__audit">
              </el-input>
            </el-form-item>
          </el-col>
        </el-row>
        <el-col :span="7">
          <el-form-item label="巡检状态">
            <el-select v-model="value" placeholder="请选择">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value">
              </el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="7">
            <el-form-item ref="safe_insp__insp_name" label="巡检名称" prop="safe_insp__insp_name" hide-required-asterisk>
              <el-input v-model="form.safe_insp__insp_name" placeholder="请选择巡检名称" class="input-with-select" clearable>
                <el-button slot="append" icon="el-icon-search" maxlength="250" @click="inspNameVisible = !inspNameVisible" />
              </el-input>
            </el-form-item>
          </el-col>
          
          <!-- hide-required-asterisk -->
  
      </el-form>
        
      
      
      
</div>
</template>

<script>
export default {
    props: {

    },
    data() {
        return {
        
          input:'',
          form:{
            safe_insp__audit:'',
            safe_insp__insp_name:'',
            safe_insp__insp_date:'',
            safe_insp__insp_times:'',
            safe_insp__insp_memo:'',
            safe_insp__insp_ed:'',
            safe_insp__insp_ing:'',
            asafe_insp__insp_non:'',
            safe_insp_audit:'',
              },
              formLabelAlign:'',
              options:[{
                value: '选项1',
                label: '已巡查'
              },{
                value: '选项2',
                label: '巡查中'
              }]

        };
    },
    computed: {

    },
    created() {

    },
    mounted() {

    },
    watch: {

    },
    methods: {

    },
    components: {

    },
};
</script>

<style scoped lang="\">

</style>
