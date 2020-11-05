<script>
// @ is an alias to /src
import MeetupCard from '@/components/meetup-card.vue'
import {mapState,mapActions} from 'vuex'
export default {
  name: 'Meetup',
  components: {
    MeetupCard
  },
  computed:{
    ...mapState(['meetup'])
    
  },
  methods:{
    ...mapActions(['fetchMeetup'])
    
  },
  created(){
    this.fetchMeetup(this.$route.params.id)
  }
}
</script>

<template lang='pug'>
  section
      meetup-card(:meetup="meetup")
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
