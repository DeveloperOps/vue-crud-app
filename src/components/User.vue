<template>
  <h1>{{ user.username }} {{fullname}}</h1>
  <h1>Followers {{ foll }}</h1>
  <button @click="follow"> Follow</button>
</template>

<script>

export default {
  name: 'User',
  data() {
    return {
      foll: 0,
      user: {
        id: 1,
        username: "developer",
        first: "Saumya",
        last: "Tripathi",
        isAdmin: true,
        email: "coding.@fmaj.com"
      }
    }
  },
  computed: {
    fullname() {
      return `${this.user.first} ${this.user.last}`
    }
  },
  methods: {
    follow() {
       this.foll = this.foll + 1;
    }
  },
  //lifecycle methods when component loads for the first time ie can do api calls
  mounted() {

  },
  //works like state ie  perform action on the change of previous value and current value
  //watch for chnages
  watch: {
    foll(newVal , oldVal) {
      if(newVal > oldVal) {
        console.log("follower gain")
      }
    }
  }
}
</script>

<style>

</style>
