<template>
  <div id="app">
    <h1>Demo Chessboard Viewer</h1>
    <div>Fen: {{ currentFen }}</div>
    <ChessViewer :fen="currentFen" />
  </div>
</template>

<script>
import ChessViewer from "./components/ChessViewer.vue";

export default {
  name: "App",
  components: {
    ChessViewer
  },
  data() {
    return {
      currentFen: ""
    };
  },
  methods: {
    loadFen(fen) {
      this.currentFen = fen;
    }
  },
  created() {
    let uri = window.location.href.split("?");
    if (uri.length === 2) {
      this.currentFen = decodeURI(uri[1])
    } else {
      this.currentFen = "3rkb1r/5pp1/p1Pp3p/1pnN1P2/8/4P3/P5PP/R4Rq1 w - - 0 1"
    }
    this.fens = [
      "3rkb1r/5pp1/p1Pp3p/1pnN1P2/8/4P3/P5PP/R4Rq1 w - - 0 28",
      "5rk1/3r1p2/p5pp/1p2p3/2Bn4/1P4QP/5PP1/5RK1 w - - 0 28",
      "4r1k1/2RR2p1/p7/1p5p/6n1/1P3NPq/P4P2/6K1 w - - 0 28",
      "5rk1/pb1n1p2/1p2pP2/4R3/1p3P2/3P4/P1r1B1p1/5RK1 w - - 0 28"
    ];
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
