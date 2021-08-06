<template>
<div>
   <CommonHeader/>

  <form @submit.prevent="register">
    <table class="register">
    <tr><th>新規登録</th></tr>
    <tr><td><input type="text" v-model="name" placeholder="ユーザーネーム" required /></td></tr>
    <tr><td><input type="email" v-model="email" placeholder="メールアドレス" required /></td></tr>
    <tr><td><input type="password" v-model="password" placeholder="パスワード" required /></td></tr>
    <tr><td><button class="button" type="submit">新規登録</button></td></tr>
  </table>
  </form>
</div>

</template>

<script>
import CommonHeader from '~/components/CommonHeader.vue';
export default {
  components: { CommonHeader },
  auth: false,
  data() {
    return {
      name: null,
      email: null,
      password: null,
    };
  },
  methods: {
    async register() {
      try {
        await this.$axios.post("http://localhost:8000/api/auth/register", {
          name: this.name,
          email: this.email,
          password: this.password,
        });
        this.$router.push("/login");
      } catch {
        alert("メールアドレスがすでに登録されています");
      }
    },
  },
};
</script>

<style>
  .register {
    background-color: white;
    border-radius: 20px;
    padding: 50px 50px;
    margin: 0 auto;
  }


  input {
    width: 400px;
    height: 50px;
    margin-top: 20px;
    border-radius: 15px;
    border: 2px solid #ccc;
  }

  .button {
    display: block;
    margin: auto;
    margin-top: 20px;
  }


</style>
