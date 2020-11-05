<script>
export default {
    name:'PeopleCard',
    props:['people'] /// same in home.vue :meetup
}
</script>
<template lang="pug">
    article.card
        img(:src="`https://picsum.photos/300/200?random=${people._id}`",alt='')
        h2.card-title {{people.name}} 
        
</template>

<style scoped>
    .card{
        display: inline-block;
        color:blue;
        text-align: left;
        padding: 20px;
        border:1px solid #ddd;
        border-radius: 3px;
        margin: 20px;
        min-width: 200px;
    }

</style>