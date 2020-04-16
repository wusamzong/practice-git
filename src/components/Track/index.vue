<template src='./template.html'>

</template>

<script>
export default {
  data(){
    return{
      mute: false,
      solo: true,
      test: 'test'
    }
  },
  
  methods:{
    muteHandler(){
      this.mute= !this.mute
    },
    soloHandler(){
      this.solo= !this.solo
    }
  }
}
</script>

<style scope>
.Track{
  display: inline-block;
  margin: 5px;
  border-radius: 5px;
  width: 95%;
  height: 180px;
  background: #464646;
  display: grid;
  grid-template-columns: 90px auto;
  grid-template-rows: 90px 90px;
  grid-template-areas: 
    "leftButton rightMessenge"
    "leftButton rightMessenge";
}
.leftButton{
  grid-area: leftButton;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: space-around;
}
.leftButton button{
  width: 98%;
  height: 48%;
  background: #5c5c5c;
  border: none;
  font-size: 30px;
}
.rightMessenge{
  grid-area: rightMessenge;
}
</style>