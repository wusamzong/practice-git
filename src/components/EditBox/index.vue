<template src='./template.html'>
  
</template>

<script>
export default {
  data(){
    return {
      isMidi:false
    }
  },
  props:{
    EditWindows:{
      type: Number,
      required: true
    },
    isEdit:{
      type: Boolean,
      required: true
    }
  },
}
</script>
<style scope>
.EditBox{
  height: 100%;
  display: grid;
  grid-template-columns: 350px auto;
  grid-template-rows: 50px auto;
  grid-template-areas: 
  "frame frame"
  "adjust content";
}
.MidiEditor{
  height: 100%;
  display: grid;
  grid-template-columns: 350px auto;
  grid-template-rows: 50px auto;
  grid-template-areas: 
  "frame content"
  "adjust content";
}
.frame{
  grid-area: frame;
  margin: 0px 20px;
  border-bottom:#a8a8a8 0.5px solid;
  display: flex;
  align-items: center;

}
.frame button{
  display: inline-block;
  width: 50px;
  height: 50px;
  background: #858585;
  border: 1px solid #858585;
}
.frame p{
  color: white;
  margin: 0 20px;
  font-size: 25px;
}
.content{
  grid-area: content;
  background: #4b4b4b;
}
.adjust{
  grid-area: adjust;
  background: #353535;
}

</style>