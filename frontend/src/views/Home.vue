<script>
// @ is an alias to /src
import MeetupCard from '@/components/meetup-card.vue'
import {mapState,mapActions} from 'vuex'
export default {
  name: 'Home',
  components: {
    MeetupCard
  },
  computed:{
    ...mapState(['counter','meetups'])
    // ...mapState({
    //   counter:(state)=>state.counter
    // })
  },
  methods:{
    ...mapActions(['fetchMeetups','incrementCounter'])
    // ...mapActions({
    //   incrementCounter:'incrementCounter'
    // })
  },
  created(){
    this.fetchMeetups()
  }
}
</script>

<template lang='pug'>
  main
    section
      button.increment-button(@click="incrementCounter") Increment
      div {{counter}}
    section
      meetup-card(v-for="meetup in meetups",:meetup="meetup")
    
</template>

<style scoped>
section{
  padding: 40px 0;
}
  .increment-button{
    color:darkcyan;
    padding:10px 20px;
    border-radius: 8px;
    background-color: white;
    border:1px solid darkcyan;
    font-size: 14px;
    font-weight: 600;
    cursor: pointer;
    margin-bottom:20px
  }
  .increment-button:hover{
    background-color: darkcyan;
    color: white;
  }
</style>
