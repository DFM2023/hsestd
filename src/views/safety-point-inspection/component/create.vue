<template>
    <div>
      <el-card class="box-card">
        <div class="buttons">
        <div class="buttons">
          <!-- <el-button type="primary" @click="create">新增</el-button>
          <el-button type="primary" @click="del">删除</el-button> -->
          <el-button type="primary" @click="save">保存</el-button>
          <!-- <el-button type="primary" @click="audit">提交</el-button>
          <el-button type="primary" @click="unaudit">反提交</el-button>
          <el-button type="primary" @click="upload">图文附件</el-button> -->
          <!-- <el-button type="primary" @click="back">返回列表</el-button> -->
        </div>
        <!-- <el-button type="primary" @click="back">返回列表</el-button> -->
      </div>

      <el-form label-width="180px" :model="form">
        <el-row>
          <el-col :span="7">
            <el-form-item label="巡检单编号" >
              <el-input v-model="form.safe_insp__insp_code">
              </el-input>
            </el-form-item>
          </el-col>
        </el-row>
        <el-col :span="7">
          <el-form-item label="巡检状态">
            <el-select v-model="form.safe_insp__insp_state" placeholder="请选择">
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
          <el-col :span="7">
            <el-form-item label="巡检日期">
              <el-input placeholder="请选择日期" suffix-icon="el-icon-date" v-model="form.afe_insp__insp_date">
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="7">
            <el-form-item ref="safe_insp__insp_man" label="巡检人员" prop="safe_insp__insp_man">
              <el-input v-model="form.safe_insp__insp_man" placeholder="请选择巡检人员" class="input-with-select" clearable>
                <el-button slot="append" icon="el-icon-search" @click="selUserVisible = !selUserVisible" />
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="7">
            <el-form-item label="备注">
              <el-input v-model="form.safe_insp__insp_memo" maxlength="500" />
            </el-form-item>
          </el-col>
          <el-col :span="7">
            <el-form-item label="巡检频率">
              <el-select v-model="form.safe_insp__insp_times" placeholder="请选择  ">
                  <el-option label="日检" value="shanghai">
                  </el-option>
                  <el-option label="周检" value="beijing">
                  </el-option>
                  <el-option label="月检" value="beijing">
                  </el-option>
                  <el-option label="季检" value="beijing">
                  </el-option>
                  <el-option label="年检" value="beijing">
                  </el-option>
                  </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="7">
            <el-form-item label="已巡检数量" >
              <el-input
                placeholder=""
                v-model="form.safe_insp__insp_ed"
                :disabled="true">
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="7">
             <el-form-item label="待巡检数量" >
              <el-input
                placeholder=""
                v-model="form.safe_insp__insp_ing"
                :disabled="true">
              </el-input>
             </el-form-item>
          </el-col>
          <el-col :span="7">
            <el-form-item label="待巡检数量" >
                <el-input
                  placeholder=""
                  v-model="form.safe_insp__insp_non"
                  :disabled="true">
               </el-input>
             </el-form-item>
            
            
          </el-col>
          <!-- hide-required-asterisk -->
  
      </el-form>
    </el-card>
        
      
      
      
</div>
</template>

<script>
import api from '../api'

export default {
    props: {

    },
    data() {
        return {
        
          input:'',
          form:{
            safe_insp__audit:'',
            safe_insp__insp_code:'',
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
      save(){
        console.log(this.form, '????');
        api.Crerte(this.form).then(data => {
          console.log(data, '返回的信息');
        })
      }
    },
    components: {

    },
};
</script>

<style scoped lang="\">

</style>
