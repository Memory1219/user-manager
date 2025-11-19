<template>
  <el-container class="app-container">

    <el-header class="app-header">
      <el-row>
      <el-col :span="9">
        <div class="grid-content ep-bg-purple" />
      </el-col>
      <el-col :span="6">
        <h1>用户管理系统</h1>
      </el-col>
      <el-col :span="9">
        <div class="grid-content ep-bg-purple-light" />
      </el-col>
    </el-row>
     
    </el-header>
    <el-main class="app-main">
      <el-row>
        <el-col :span="7">
          <div class="grid-content ep-bg-purple" />
        </el-col>
        <el-col :span="10">
        <router-view />
        </el-col>
        <el-col :span="7">
          <div class="grid-content ep-bg-purple" />
        </el-col>
      </el-row>
      
    </el-main>
    <el-footer>
    <el-row>
      <el-col :span="8">
        <div class="grid-content ep-bg-purple" />
      </el-col>
      <el-col :span="8">
      <p>&copy; 2025 用户管理系统. All rights reserved.</p>
      </el-col>
      <el-col :span="8">
        <div class="grid-content ep-bg-purple" />
      </el-col>
    </el-row>
  </el-footer>
  </el-container>
</template>

<style>
.app-container {
  min-height: 100vh;
  background: linear-gradient(to bottom, #e3f2fd, #f5f5f5); /* 添加渐变背景 */
  color: #333;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
}

.app-header {
  width: 100%;
  background: #409eff;
  color: #fff;
  padding: 20px 0;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* 增加阴影效果 */
  border-bottom: 2px solid #e3f2fd; /* 添加底部边框 */
}

.app-header h1 {
  margin: 0;
  font-size: 28px; /* 增大字体 */
  font-weight: bold; /* 加粗字体 */
}

</style>