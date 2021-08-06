<template>
  <div class="home">
    <table>
    <tr><th><img src="img/logo.png" width="200px"></th></tr>
      <tr>
       <td><img src="img/home.png" width="30px"></td>
        <td>ホーム</td>
      </tr>
      <tr>
        <td><img src="img/logout.png" width="30px"></td>
        <td>ログアウト</td>
      </tr>
      <tr>
        <td>シェア</td>
      </tr>
      <tr>
      <td><textarea name="" ></textarea></td>
      </tr>
      <tr>
        <td><button class="button" type="submit">シェアする</button></td>
      </tr>
    </table>

    <table>
      <tr><th>コメント</th></tr>
    </table>
  </div>
</template>

<script>
export default {}
</script>


<style>
body{
  background-color: #000033;
  color: white;
}

.home {
  display: flex;
}
</style>
