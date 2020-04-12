<template>
  <div id="app">
    <div class="layout">
      <div class="head-1">
        <ul>
          <li>Exit</li>
          <li>File</li>
          <li>Edit</li>
          <li>View</li>
          <li>Settings</li>
          <li>Help</li>
        </ul>
        <p>Title {{hi}}</p>
      </div>

      <div class="head-2">
        <div class="step">
          <button class="previousStep">▲</button>
          <button class="nextStep">▲</button>
        </div>
        <div class="play">
          <button class="before">▲</button>
          <button class="play">▲</button>
          <button class="after">▲</button>
          <p class="length">{{time}}</p>
        </div>
        <div class="BPM">
          <p>{{BPM}}bpm</p>
          <button class="speedUp">▲</button>
          <button class="slowDown" style="border-bottom-right-radius: 5px; border-top-right-radius: 5px;">▼</button>
        </div>
        <div class="volume">
          <input type="range" min="0" max="100" />
        </div>
      </div>

      <div class="side-box">side-box</div>
      <div class="edit-box">edit-box</div>
    </div>

    <div class="bottom">bottom</div>
  </div>
</template>
<script rel='stylesheet' href='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css'/>
<script>
export default {
  name: "App",
  data() {
    return {
      hi: "hello",
      BPM: 120,
      time: "00:00.0"
    };
  }
};
</script>

<style>
body {
  margin: 0;
  font-family: sans-serif;
}
#app {
  margin: 0 auto;
  padding: 0;
}
.layout {
  height: 95vh;
  width: 100%;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 250px auto;
  grid-template-rows: 50px 50px auto;
  grid-template-areas:
    "head1 head1"
    "head2 head2"
    "sideBox editBox";
  background: #666666;
}

.head-1 {
  grid-area: head1;
  background: #5f5f63;
}
.head-1 ul {
  display: inline-block;
  margin: 0;
  width: 500px;
}
.head-1 li {
  color: white;
  display: inline-block;
  padding: 10px;
  list-style: none;
}
.head-1 li:hover {
  text-decoration-line: underline;
}
.head-1 p {
  display: inline-block;
  margin: 0 auto;
  font-size: 18px;
  color: white;
  text-align: center;
}
.head-2 {
  grid-area: head2;
  display: inline-block;
  background: #5f5f63;
  display: grid;
  grid-template-columns: auto 450px auto auto;
  grid-template-rows: 50px;
  grid-template-areas: "step play BPM volume";

  height: 50px;
}
.step {
  grid-area: step;
  margin: 0 50px;
}
.step button{
  display: inline-block;  
  height: 40px;
  width: 50px;
  background: #383838;
  padding: 4px 6px;
  border: 2px solid #5f5f63;
  border-radius: 5px;
  color: #c0c0c0;
  
}
.play {
  grid-area: play;
}
.play button{
  height: 40px;
  width: 50px;
  background: #383838;
  border: 2px solid #5f5f63;
  border-radius: 5px;
  color: #c0c0c0;
}
.play p{
  display: inline-block;
  margin: 0 auto;
  width: 120px ;
  background: #383838;
  border: 2px solid #5f5f63;
  border-radius: 5px;
  color: #c0c0c0;
  text-align: center;
  font-size: 23px;
  padding: 15px;
  padding-top: 2px;
  padding-bottom: 7px;
}
.BPM {
  grid-area: BPM;

}
.BPM p {
  display: inline-block;
  margin: 0 auto;
  width: 100px ;
  background: #383838;
  border: 2px solid #5f5f63;
  border-bottom-left-radius: 5px;
  border-top-left-radius: 5px;
  color: #c0c0c0;
  text-align: center;
  font-size: 23px;
  padding: 20px;
  padding-top: 2px;
  padding-bottom: 7px;
}
.BPM button{
  height: 37px;
  width: 50px;
  background: #383838;
  color: #c0c0c0;
  border: 1px solid #5f5f63;
}


.volume {
  grid-area: volume;
}

.side-box {
  grid-area: sideBox;
  background: #2a2a31;
}
.edit-box {
  grid-area: editBox;
  background: #202020;
}
.bottom {
  height: 5vh;
  width: 100%;
  background: #323238;
}
</style>
