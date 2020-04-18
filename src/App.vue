<template>
  <div id="app">
    <div class="layout" :class="[isEdit ? 'editTrack':'justTrack']">
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
        <Head2 :BPM="BPM" :time="time" />
      </div>

      <div class="track">

        <div class="side-box">
          <button @click="track++" class="addButton">+ add track</button>
          <Track v-for="num in trackIndex" :key="num" />
        </div>

        <div class="track-box">
          <div class="timeline">
            <ul>
              <li v-for="i in 16" :key="i">{{i}}</li>
            </ul>
          </div>
          <TrackEdit v-for="num in trackIndex" :key="num" />
        </div>

      </div>

      <div v-if="isEdit" class="Edit-box">Edit-box</div>

    </div>

    <div class="bottom">
      <button @click="Ins=!Ins; edithandler()">Instrument</button>
      <button @click="Fx=!Fx; edithandler()">Fx</button>
      <button @click="MIDI=!MIDI; edithandler()">MIDI Editor</button>
    </div>
  </div>
</template>

<script rel='stylesheet' href='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css'/>
<script>
import Track from "@/components/Track/index.vue";
import Head2 from "@/components/Head2/index.vue";
import TrackEdit from "@/components/TrackEdit/index.vue";
export default {
  name: "App",
  components: {
    Track,
    Head2,
    TrackEdit
  },
  computed: {
    trackIndex() {
      return this.track;
    }
  },
  data() {
    return {
      hi: "hello",
      BPM: 120,
      time: "00:00.0",
      track: 0,
      Ins: false,
      Fx: false,
      MIDI: false,
      isEdit: false
    };
  },
  methods: {
    edithandler() {
      this.isEdit = !this.isEdit;
    }
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
}
.justTrack {
  display: grid;
  grid-template-rows: 50px 50px auto;
  grid-template-areas:
    "head1"
    "head2"
    "track";
  background: #666666;
}
.editTrack {
  display: grid;
  grid-template-rows: 50px 50px 300px auto;
  grid-template-areas:
    "head1"
    "head2"
    "track"
    "editBox";
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
}
.leftRadius {
  border-bottom-left-radius: 5px;
  border-top-left-radius: 5px;
}
.rightRadius {
  border-bottom-right-radius: 5px;
  border-top-right-radius: 5px;
}

.track{
  grid-area: track;
  display: grid;
  grid-template-columns: 350px auto;
  grid-template-areas: "sideBox trackBox";
  overflow-y: auto;
  overflow-x: hidden;
}
.side-box {
  grid-area: sideBox;
  background: #2a2a31;

}
.addButton {
  display: inline-block;
  margin: 5px;
  border-radius: 5px;
  width: 95%;
  height: 30px;
}
::-webkit-scrollbar {
  width: 5px;
  height: 5px;
}
::-webkit-scrollbar-track {
  background-color: #858585;
} /* the new scrollbar will have a flat appearance with the set background color */

::-webkit-scrollbar-thumb {
  background-color: rgba(255, 255, 255, 0.774);
} /* this will style the thumb, ignoring the track */

::-webkit-scrollbar-corner {
  background-color: black;
}
.track-box {
  grid-area: trackBox;
  background: #202020;
  overflow-x: auto;
  overflow-y: hidden;
}
.timeline {
  display: inline-block;
  background: #38383a;
  border-radius: 5px;
  height: 35px;
  width: 2000px;
}
.timeline ul {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  margin: 0px;
  margin-top: 7px;
  margin-left: 5px;
  padding: 0px;
}
.timeline li {
  width: 20px;
  list-style-type: none;
  color: white;
}
.edit-box {
  grid-area: editBox;
  background: #858585;
}
.bottom {
  height: 5vh;
  width: 100%;
  background: #323238;
}
</style>
