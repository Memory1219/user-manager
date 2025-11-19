<template>
  <div class="app-container">
    <header class="app-header">
      <h1>用户管理系统</h1>
    </header>
    <main class="app-main">
      <router-view />
    </main>
  </div>
</template>

<style>
.app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  background: #f5f5f5;
  color: #333;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
}

.app-header {
  width: 100%;
  background: #409eff;
  color: #fff;
  padding: 20px 0;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.app-header h1 {
  margin: 0;
  font-size: 24px;
}

.app-main {
  flex: 1;
  width: 100%;
  max-width: 1200px;
  padding: 20px;
  box-sizing: border-box;
}
</style>