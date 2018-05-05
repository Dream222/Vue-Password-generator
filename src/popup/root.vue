<template>
    <div class="app-content">
      <el-row>
        <el-col :span="20" :offset="2">
          <div class="grid-content bg-purple">
            <el-row :span="24">
              <el-col :span="8" class="label-text">
                <span class="demo-input-label">length</span>
              </el-col>
              <el-col :span="16">
                <el-input type="number" placeholder="Please input" v-model="length"></el-input>
              </el-col>
            </el-row>
            <el-row :span="24">
              <el-col :span="8" class="label-text">
                <span class="demo-input-label">Special</span>
              </el-col>
              <el-col :span="16">
                <el-input type="text" placeholder="Please input" v-model="special"></el-input>
              </el-col>
            </el-row>
            <el-row :span="24">
              <el-col :span="16" :offset="8" >
                <el-button class="generate" type="success" @click="Generate" plain>Generate</el-button>
              </el-col>
            </el-row>
             <el-row :span="24">
              <el-col :span="8" class="label-text">
                <span class="demo-input-label">Result</span>
              </el-col>
              <el-col :span="16">
                <el-input id="myPassword" type="text" placeholder="Please input" v-model="result"></el-input>
                <el-button type="primary" @click="Copy" plain>copy</el-button>
              </el-col>
            </el-row>
          </div>
        </el-col>
      </el-row>
    </div>
</template>
<script>
  export default {
    data: function () {
      return {
        input: '',
        length: 8,
        special: '~!@#$%^&*',
        result: ''
      }
    },
    computed: { },
    created () { },
    mounted () { },
    methods: {
      Generate: function () {
        var possible = this.special
        var passwordText = ''
        var chars = 'abcdefghiklmnopqrstuvwxyz~!@#$%^&*'
        for (var i = 0; i < 4; i++) {
          passwordText += possible.charAt(Math.floor(Math.random() * possible.length))
        }
        for (var j = 0; j < this.length - 4; j++) {
          passwordText += chars.charAt(Math.floor(Math.random() * possible.length))
        }
        this.result = passwordText
      },
      Copy: function () {
        var copyText = document.getElementById('myPassword')
        copyText.select()
        document.execCommand('Copy')
      }
    }
  }
</script>
<style lang="scss">
  div {
    color: blue
  }
  .app-content {
    width: 600px;
  }
  .el-input {
    margin-top: 20px;
  }
  .generate, .el-button {
    margin-top: 20px; 
    width: 100%;
  }
  .label-text {
    margin-top: 20px;
    font-size: 20px;
  }
  
</style>