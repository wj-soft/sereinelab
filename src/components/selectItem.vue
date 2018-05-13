<template>
  <div id="selectItem">
    <h1>관심항목 설정</h1>
      <div class="wrap">
        <h3>당신의 관심항목을 선택해주세요. (최대 4가지)</h3><hr>
        <ul @click="recheck">
          <li v-for="(type, index) in typeList" :key='index'>
            <input type="checkbox" v-bind:id="'type'+index" v-bind:value="type"  v-model="checkedNames" v-bind:disabled="maxValueCheck">
            <label v-bind:for="'type'+index">{{type}}</label>
          </li>
        </ul>
        <em v-if=maxValueCheck>최대 4개까지만 선택해주세요</em>
    </div>
  </div>
</template>

<script>
export default {
   data(){
    return {
      typeList: ["건조함", "각질", "문제성 지성", "블랙 헤드", "넓은 모공","복합성", "칙칙한 피부", "민감성 피부", "주름", "홍조"],
      checkedNames: [],
      maxValueCheck: false
    }
  },
  watch: {
    checkedNames : function(val){
      this.maxValueCheck = val.length >= 4 ? true : false
    }
  },
  computed: {
  },
  methods: {
    recheck : function(){
      if (this.checkedNames.length >= 4) {
        this.maxValueCheck = event.target.checked === false ? true : false 
      } 
    }
  }
}
</script>

<style lang="scss">
#selectItem{
  width: 550px;
  .wrap{
    background: #F5F5F5;
    height: 500px;
  }
  h3{
    text-align: center;
    margin: 30px 10px 30px 10px;
    padding: 40px 15px 15px 15px;
  }
  hr{
    margin-bottom: 40px;
  }
  li{
    width: 48%;
    float: left;
    font-size: 1.4rem;
    margin-bottom : 40px;
    margin-left: 2%;
  }
  em{
    color: red;
  }
  input[type="checkbox"] {
    display:none;
  }
  input[type='checkbox'] + label::before {
    content: '  '; 
    display: inline-block; 
    width: 1.8rem; 
    height: 1.6rem;
    background: url('../assets/unchecked.png') no-repeat;
  }
  input[type='checkbox']:checked + label::before {
    background: url('../assets/checked.png') no-repeat;
  }
// 모바일기기 대응을 위한 CSS
 @media screen and (max-width: 999px){
   width: 100%;
 }
}
</style>
