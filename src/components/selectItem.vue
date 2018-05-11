<template>
  <div id="selectItem">
    <h1>관심항목 설정</h1>
      <div class="wrap">
        <h3>당신의 관심항목을 선택해주세요. (최대 4가지)</h3><hr>
        <ul>
          <li>
            <input type="checkbox" id="type1" value="건조함" v-model="checkedNames">
            <label for="type1">건조함</label>
          </li>
          <li>
            <input type="checkbox" id="type2" value="각질" v-model="checkedNames">
            <label for="type2">각질</label>
          </li>
          <li>
            <input type="checkbox" id="type3" value="문제성 지성" v-model="checkedNames">
            <label for="type3">문제성 지성</label>
          </li>
          <li>
            <input type="checkbox" id="type4" value="블랙 헤드" v-model="checkedNames">
            <label for="type4">블랙 헤드</label>
          </li>
          <li>
            <input type="checkbox" id="type5" value="넓은 모공" v-model="checkedNames">
            <label for="type5">넓은 모공</label>
          </li>
          <li>
            <input type="checkbox" id="type6" value="복합성" v-model="checkedNames">
            <label for="type6">복합성</label>
          </li>
          <li>
            <input type="checkbox" id="type7" value="칙칙한 피부" v-model="checkedNames">
            <label for="type7">칙칙한 피부</label>
          </li>
          <li>
            <input type="checkbox" id="type8" value="민감성 피부" v-model="checkedNames">
            <label for="type8">민감성 피부</label>
          </li>
          <li>
            <input type="checkbox" id="type9" value="주름" v-model="checkedNames">
            <label for="type9">주름</label>
          </li>
          <li>
            <input type="checkbox" id="type10" value="홍조" v-model="checkedNames">
            <label for="type10">홍조</label>
          </li>
        </ul>
    </div>
  </div>
</template>

<script>
export default {
   data(){
    return {
      checkedNames: []
    }
  }
}
</script>

<style lang="scss">
#selectItem{
  width: 550px;
  .wrap{
    background: #F5F5F5;
    height: 450px;
  }
  h3{
    text-align: center;
    margin: 10px;
    padding: 15px;
  }
  hr{
    margin-bottom: 40px;
  }
  li{
    width: 50%;
    float: left;
    font-size: 1.4rem;
    margin-bottom : 40px;
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
}


</style>
