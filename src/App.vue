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
          <button class="previousStep leftRadius">▲</button>
          <button class="nextStep rightRadius">▲</button>
        </div>
        <div class="play">
          <button class="before leftRadius">▲</button>
          <button class="play"><i class="fas fa-play"></i></button>
          <button class="after">▲</button>
          <p class="length rightRadius">{{time}}</p>
        </div>
        <div class="BPM">
          <p class="leftRadius">{{BPM}}bpm</p>
          <button class="speedUp">▲</button>
          <button class="slowDown rightRadius">▼</button>
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

  background: #5f5f63;
  padding: 5px;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-around;
  align-items: stretch;
}
.step {
  background: #5f5f63;
  flex-grow: 1;
  padding: 0 50px;
}
.step button {
  height: 40px;
  width: 50px;
  background: #383838;
  padding: 4px 6px;
  border: 1px solid #5f5f63;
  color: #c0c0c0;
  cursor: pointer;
}
.play {
  background: #5f5f63;
  padding: 0 50px;
  flex-grow: 2;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: stretch;
}
.play button {
  flex-grow: 1;
  height: 40px;
  width: 50px;
  background: #383838;
  border: 1px solid #5f5f63;
  color: #c0c0c0;
  cursor: pointer;

}
.play p {
  flex-grow: 1;
  margin: 0 auto;
  width: 120px;
  background: #383838;
  border: 1px solid #5f5f63;
  color: #c0c0c0;
  text-align: center;
  font-size: 23px;
  padding: 5px;
}
.BPM {
  background: #5f5f63;
  flex-grow: 1;
  padding: 0 35px;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: stretch;
}
.BPM p {
  flex-grow: 2;
  margin: 0 auto;
  width: 100px;
  background: #383838;
  border: 1px solid #5f5f63;
  color: #c0c0c0;
  text-align: center;
  padding: 5px;
  font-size: 23px;
}
.BPM button {
  flex-grow: 1;
  background: #383838;
  color: #c0c0c0;
  border: 1px solid #5f5f63;
  cursor: pointer;
}

.volume {
  background: #5f5f63;
  flex-grow: 1;
}
.leftRadius{
  border-bottom-left-radius: 5px; 
  border-top-left-radius: 5px;
}.rightRadius{
  border-bottom-right-radius: 5px; 
  border-top-right-radius: 5px;
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
