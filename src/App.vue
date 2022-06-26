<template>
<div class="form">
  <h2>エントリーフォーム</h2>
  <div class="textForm">
    <label for="name">名前</label>
    <input type="text" id="name" v-model="eventData.name">
  </div>
  <div class="textForm">
    <label for="email">メールアドレス</label>
    <input type="text" id="email" v-model.lazy="eventData.email">
  </div>
  <div class="textForm">
    <label for="phon">お電話番号</label>
    <input type="text" id="phone" v-model.number="eventData.phone">
  </div>
  <!-- セレクトボックス -->
  <label>地域</label>
  <select v-model="eventData.location">
    <option v-for="location in locations" :key="location">{{location}}</option>
  </select>
  <!-- ラジオボタン -->
  <input type="radio" id="age" value="一般" v-model="eventData.age">
  <label for="age">一般</label>
  <input type="radio" id="age" value="高校生" v-model="eventData.age">
  <label for="age">高校生</label>
  <input type="radio" id="age" value="中学生" v-model="eventData.age">
  <label for="age">中学生</label>
  <input type="radio" id="age" value="小学生" v-model="eventData.age">
  <label for="age">小学生</label>
  <!-- 複数チェックボックス -->
  <div class="textForm">
     <input type="checkbox" id="isPrivate" value="HTML" v-model="eventData.isPrivate">
     <label for="isPrivate">100kmの部門</label>
     <input type="checkbox" id="isPrivate" value="CSS" v-model="eventData.isPrivate">
     <label for="isPrivate">フルマラソンの部門</label>
     <input type="checkbox" id="isPrivate" value="Vue.js" v-model="eventData.isPrivate">
     <label for="isPrivate">ハーフマラソンの部門</label>
  </div>
  <!-- ラジオボタン -->
  <input type="radio" id="free" value="無料" v-model="eventData.free">
  <label for="free">案内メール受け取る</label>
  <input type="radio" id="free" value="有料" v-model="eventData.free">
  <label for="free">案内メールを受け取らない</label>
  <label for="detail">ご相談・ご質問</label>
  <textarea id="detail" cols="30" rows="10" v-model="eventData.detail"></textarea>
  <button>送信する</button>
</div>
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
          checkbox: false, //単体チェックボックス 
          isPrivate: [], //複数チェックボックス配列
          free: "無料",
          location: "東京",//デフォルト設定
          detail: "detail",
        }
      }
    }
};
</script>

<style>
.form {
  background: #f3f3f3;
  widows: 60%;
  border-radius: 10px;
}
h2 {
  text-align: center;
  padding: 40px auto;
}

.textForm {
  display: flex;
  margin: 20px auto;
}

label {
  widows: 20%;
}

input {
  widows: 35%;
  margin-left: 5%;
}

</style>

