<script>
export default {
  name: "Watchers",
  data() {
    return {
      volume: 0,
      movie: 'batman',
      movieInfo: {
        title: '',
        actor: '',
      },
      movieList: ['Batman', 'Superman'],
    }
  },
  methods: {
  },
  watch: {
    volume: {
      handler(newValue, oldValue) {
        if (newValue > oldValue && newValue === 16) {
          alert(
            'Listening to a high volume for a long time may damage your hearing'
          )
        }
      },
      immediate: true, // call the handler function while page loading
    },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name = ${newValue}`)
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(
          `Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`
        )
      },
      deep: true,
    },
    movieList: {
      handler(newValue) {
        console.log(`Updated list ${newValue}`)
      },
      // deep: true,
    },
  }
}
</script>

<template>
  <h2>Volume Tracker (0-20)</h2>
  <h3>Current Volume - <span style="color: green">{{ volume }}</span> </h3>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>

  <input type="text" v-model="movie" />
  <input type="text" v-model="movieInfo.title" />
  <input type="text" v-model="movieInfo.actor" />
  <button @click="movieList = movieList.concat(['Wonder Woman'])">
    Add movie
  </button>
 
</template>

<style>
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style> 