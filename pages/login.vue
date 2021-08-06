<template>
<div>
   <CommonHeader/>



  <form @submit.prevent="login">
    <table class="login">
    <tr><th>ログイン</th></tr>
    <tr><td><input type="email" v-model="email" placeholder="メールアドレス" required /></td></tr>
    <tr><td><input type="password" v-model="password" placeholder="パスワード" required /></td></tr>
    <tr><td><button class="button" type="submit">ログイン</button></td></tr>
  </table>
  </form>
</div>

</template>

<script>
export default {
  data() {
    return {
      email: null,
      password: null,
    };
  },
  methods: {
    async login() {
      try {
        await this.$auth.loginWith("laravelJWT", {
          data: {
            email: this.email,
            password: this.password,
          },
        });
        this.$router.push("/");
      } catch {
        alert("メールアドレスまたはパスワードが間違っております");
      }
    },
  },
};
</script>

<style>

  .login {
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
