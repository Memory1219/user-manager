<template>
  <h3 class="form-title">{{ isEdit ? '编辑用户' : '创建用户' }}</h3>
  <el-container class="form-container">
    <el-main>
      <el-form :model="user" label-width="80px" @submit.prevent="submit" class="form-content">
        <el-form-item label="姓名">
          <el-input v-model="user.name" required></el-input>
        </el-form-item>
        <el-form-item label="邮箱">
          <el-input v-model="user.email" required></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submit">保存</el-button>
          <router-link to="/">
            <el-button>取消</el-button>
          </router-link>
        </el-form-item>
      </el-form>
    </el-main>
  </el-container>
</template>

<script>
import { fetchUser, createUser, updateUser } from '../api/user';

export default {
  name: 'UserForm',
  props: ['id'],
  data() {
    return { user: { name: '', email: '' } };
  },
  computed: {
    isEdit() {
      return !!this.$route.params.id;
    },
  },
  mounted() {
    const id = this.$route.params.id;
    if (id) {
      fetchUser(id)
        .then((r) => {
          this.user = r.data;
        })
        .catch(() => alert('加载用户失败'));
    }
  },
  methods: {
    submit() {
      const id = this.$route.params.id;
      if (id) {
        updateUser(id, this.user)
          .then(() => this.$router.push('/'))
          .catch(() => alert('更新失败'));
      } else {
        createUser(this.user)
          .then(() => this.$router.push('/'))
          .catch(() => alert('创建失败'));
      }
    },
  },
};
</script>

<style>
.form-container {
  padding: 20px;
  text-align: center;
  margin-left: 25%;
}

.form-title {
  text-align: center;
  font-size: 24px; 
  font-weight: bold; 
  color: #409eff; 
  margin-bottom: 30px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
}

.form-content {
  width: 100%;
  max-width: 500px; /* 限制表单宽度 */
  background: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
}
</style>
