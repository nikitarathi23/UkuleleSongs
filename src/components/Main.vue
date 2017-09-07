<template>
  <div id="main">
    <h1> {{msg}} </h1>
    <a v-on:click="renderSongList" class="button is-light is-large">
      <span class="icon">
        <i class="fa fa-list"></i>
      </span>
      <span>View Song Index</span>
    </a>
    <br/>
    <a class="button is-light is-large">
      <span class="icon">
        <i class="fa fa-music"></i>
      </span>
      <span> Search by song</span>
    </a>
    <a class="button is-light is-large">
      <span class="icon">
        <i class="fa fa-user"></i>
      </span>
      <span>Search by artist</span>
    </a>

    <div class="container"></div>
  </div>
</template>

<script>
  import Firebase from 'firebase'

  var config = {
    apiKey: 'AIzaSyDaiI6P0pee-yRzgm49aSymQ16-EvB1HKQ',
    authDomain: 'vue-firebase-62e7a.firebaseapp.com',
    databaseURL: 'https://vue-firebase-62e7a.firebaseio.com',
    projectId: 'vue-firebase-62e7a',
    storageBucket: 'vue-firebase-62e7a.appspot.com',
    messagingSenderId: '435872392293'
  }

  let app = Firebase.initializeApp(config)
  let db = app.database()
  let songs = db.ref('songs')

  export default {
    name: 'main',
    data: {
      msg: 'Welcome to Ukulele Tabs',
      songs: songs
    },
    methods: {
      renderSongList: function () {

      }
    }
  }
</script>

<style scoped>
  h1 {
    font-weight: normal;
    font-size: 50px;
    padding: 8px;
  }

  .button {
    margin: 8px;
  }

</style>
