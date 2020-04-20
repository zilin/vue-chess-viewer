<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Simple Chessboard with legal moves</h1>
    <ChessViewer/>

    <h1>Simple Chessboard with free moves</h1>
    <ChessViewer :free="true"/>
  </div>
</template>

<script>
import ChessViewer from './components/ChessViewer.vue'

export default {
  name: 'App',
  components: {
    ChessViewer
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
