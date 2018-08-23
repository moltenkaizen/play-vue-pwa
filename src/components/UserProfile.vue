<template>
    <div class="profile">
        <img class="profile__image" :src=user.picture.medium />
        <h3 class="profile__name" >{{ user.name.first }} {{ user.name.last }}</h3>
        <p class="profile__location" >{{ user.location.city }}, {{ user.location.state }}</p>
    </div>
</template>

<script>
  export default {
    props: ['user'],
    data () {
      return {}
    },
    methods: {},
    mounted () {

    }
  }
</script>

<style scoped>
    .profile {
        display: inline-block;
        width: 250px;
        box-shadow: 0 3px 8px rgba(0, 0, 0, 0.2);
        text-align: center;
        padding: 1.5em;
        margin: 1em;
        background-color: white;
        border-radius: 4px;
        text-transform: capitalize;
        color: #2f2f2f;
    }

    .profile__name {
        padding: 0;
        margin: 0;
        margin-top: 1em;
    }

    .profile__location {
        padding: 0;
        margin: 0;
        color: #3f3f3f;
        font-size: .8em;
    }
    .profile__image {
        border-radius: 50%;
    }

</style>
