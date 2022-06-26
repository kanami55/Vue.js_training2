<template>
<form>
    <h2>エントリーフォーム</h2>
    <dl>
      <dt>名前</dt>
      <dd><input type="text" id="name" v-model="eventData.name"></dd>
      <dt>メールアドレス</dt>
      <dd><input type="text" id="email" v-model.lazy="eventData.email"></dd>
      <dt>お電話番号</dt>
      <dd><input type="text" id="phone" v-model.number="eventData.phone"></dd>
    <!-- セレクトボックス -->
      <dt>地域</dt>
    <select v-model="eventData.location">
      <option v-for="location in locations" :key="location">{{location}}</option>
    </select>
    <!-- ラジオボタン -->
      <dt>エントリー区分</dt>
      <dd><input type="radio" id="age" value="一般" v-model="eventData.age">一般
          <input type="radio" id="age" value="高校生" v-model="eventData.age">高校生
          <input type="radio" id="age" value="中学生" v-model="eventData.age">中学生
          <input type="radio" id="age" value="小学生" v-model="eventData.age">小学生
      </dd>
    <!-- 複数チェックボックス -->
      <dt>エントリー部門</dt>
      <dd>
        <input type="checkbox" id="isPrivate" value="HTML" v-model="eventData.isPrivate">100kmの部門
        <input type="checkbox" id="isPrivate" value="CSS" v-model="eventData.isPrivate">フルマラソンの部門
        <input type="checkbox" id="isPrivate" value="Vue.js" v-model="eventData.isPrivate">ハーフマラソンの部門
      </dd>
    <!-- ラジオボタン -->
      <dt>関連メールについて</dt>
      <dd><input type="radio" id="free" value="有効" v-model="eventData.free">案内メール受け取る
          <input type="radio" id="free" value="無効" v-model="eventData.free">案内メールを受け取らな
      </dd>
      <dt>ご相談・ご質問</dt>
      <dd><textarea id="detail" cols="30" rows="10" v-model="eventData.detail"></textarea></dd>
  </dl>
  <button>送信する</button>
</form>
</template>

<script>
export default {
    data() {
      return {
        locations: ["北海道","東北","関東","中部","近畿","中国","四国","九州","沖縄"],
        eventData: {
          name: "名前",
          email: "email",
          phone: "お電話番号",
          age: "一般",
          isPrivate: [], //複数チェックボックス配列
          free: "有効",
          location: "東京",//デフォルト設定
          detail: "detail",
        }
      }
    }
};
</script>

<style>
form {
  margin: 0 auto;
  width: 70%;
  background: #f3f3f3;
  padding: 30px 50px;
  border-radius: 10px;
}
h2 {
  text-align: center;
  padding: 40px auto;
}
dl {
  margin: 0 auto;
}
form dl dt {
  float: left;
  padding: 10px 0;
  width: 300px;
  clear: both;
}
form dl dd {
 padding: 10px 0;
}
</style>

