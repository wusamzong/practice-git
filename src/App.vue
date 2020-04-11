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
        <p>Title</p>
      </div>

      <div class="head-2">
        <div class="step">
          <button class="previousStep"></button>
          <button class="nextStep"></button>
        </div>
        <div class="play">
          <button class="before"></button>
          <button class="play"></button>
          <button class="after"></button>
          <p class="Time"></p>
        </div>
        <div class="BPM">
          {{BPM}}
          <p>bpm</p>
          <button class="speedUp"></button>
          <button class="slowDown"></button>
        </div>
        <div class="volume">
          <input type="range" min="0" max="100">
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
      BPM: 120
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
