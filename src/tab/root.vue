<template>
    <div class="app-content">
      <el-row>
        <el-col :span="6" :offset="9">
          <div class="grid-content bg-purple">
            <el-row :span="24">
              <el-col :span="8">
                <span class="demo-input-label">length</span>
              </el-col>
              <el-col :span="16">
                <el-input type="number" placeholder="Please input" v-model="input"></el-input>
              </el-col>
            </el-row>
            <el-row :span="24">
              <el-col :span="8">
                <span class="demo-input-label">Special</span>
              </el-col>
              <el-col :span="16">
                <el-input type="text" placeholder="Please input" v-model="input"></el-input>
              </el-col>
            </el-row>
            <el-row :span="24">
              <el-col :span="24">
                <el-button class="generate" type="success" plain>Generate</el-button>
              </el-col>
            </el-row>
             <el-row :span="24">
              <el-col :span="8">
                <span class="demo-input-label">Result</span>
              </el-col>
              <el-col :span="16">
                <el-input type="password" placeholder="Please input" v-model="input"></el-input>
                <el-button type="primary" plain>copy</el-button>
              </el-col>
            </el-row>
          </div>
        </el-col>
      </el-row>
    </div>
</template>
<script>
  export default {
    data: () => ({
      input: ''
    }),
    computed: { },
    created () { },
    mounted () { },
    methods: { }
  }
</script>
<style lang="scss">
  div {
    color: blue
  }
  .app-content {
    margin-top: 200px;
  }
  .el-input {
    margin-top: 20px;
  }
  .generate, .el-button {
    margin-top: 20px; 
    width: 100%;
  }
  span {
    margin-top: 20px;
    font-size: 20px;
  }
  
</style>