<template>
  <div id="selectItem">
    <h1>관심항목 설정</h1>
      <div class="wrap">
        <h3>당신의 관심항목을 선택해주세요. (최대 4가지)</h3><hr>
        <ul>
          <li v-for="(type, index) in typeList" :key='index' v-bind:class="{unChecking : checkedNames.indexOf(type) == -1}">
            <input type="checkbox" 
              v-model="checkedNames" 
              v-bind:id="'type'+index" 
              v-bind:value="type"  
              v-bind:disabled="checkboxStatus[index]">
            <label v-bind:for="'type'+index">{{type}}</label>
          </li>
        </ul>
    </div>
  </div>
</template>

<script>
export default {
   data(){
    return {
      typeList: ["건조함", "각질", "문제성 지성", "블랙 헤드", "넓은 모공","복합성", "칙칙한 피부", "민감성 피부", "주름", "홍조"],
      checkboxStatus: [false,false,false,false,false,false,false,false,false,false],
      checkedNames: []
    }
  },
  
  watch: {
    checkedNames : function(val){
    	if ( val.length == 4 ) {
      	for ( var i=0; this.typeList.length > i; i++ ) {
        	if ( this.checkedNames.indexOf(this.typeList[i]) == -1 ) {
          	this.checkboxStatus[i] = true;
          } 
        }
      } else {
      	for ( var j=0; this.typeList.length > j; j++ ) {
        		this.checkboxStatus[j] = false;
        }
      }
		}
  },
  computed: {
  },
  methods: {
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
  ul{
    padding: 0 10px 0 10px;
  }
  li{
    width: 48%;
    float: left;
    font-size: 1.4rem;
    margin-bottom : 40px;
    margin-left: 2%;
  }
  input[type="checkbox"] {
    display:none;
  }
  input[type='checkbox'] + label::before {
    content: ''; 
    display: inline-block; 
    margin-right: 10px;
    width: 1.8rem; 
    height: 1.6rem;
    background: url('../assets/unchecked.png') no-repeat;
  }
  input[type='checkbox']:checked + label::before {
    background: url('../assets/checked.png') no-repeat;
  }
  .unChecking{
    color: #999999;
  }
// 모바일기기 대응을 위한 CSS
 @media screen and (max-width: 768px){
   width: 100%;
   li{
     font-size: 1.2rem;
   }
 }
}
</style>
