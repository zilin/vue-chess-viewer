<template>
  <div id="app">
    <h1>Demo Chessboard Viewer</h1>
    <ChessViewer :fen="currentFen"/>
    <chessboard :fen="currentFen"/>
      <button class="button is-light" @click="loadFen(fen)" v-for="fen in fens" :key="fen">
        {{fen}}
      </button>
  </div>
</template>

<script>
import ChessViewer from './components/ChessViewer.vue'

export default {
  name: 'App',
  components: {
    ChessViewer
  },
  data () {
    return {
      currentFen: '',
    }
  },
  methods: {
    loadFen(fen) {
      this.currentFen = fen
    },
  },
  created() {
    this.fens = ['5rr1/3nqpk1/p3p2p/Pp1pP1pP/2pP1PN1/2P1Q3/2P3P1/R4RK1 b - f3 0 28',
                'r4rk1/pp1b3p/6p1/8/3NpP2/1P4P1/P2K3P/R6R w - - 0 22'
                ]
  }
}
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
