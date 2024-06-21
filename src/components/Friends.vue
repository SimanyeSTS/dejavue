<template>
    <div>
      <div v-if="friends.length > 0">
        <Card v-for="friend in friends" :key="friend.id" :class="{'border-gold': friend.gender === 'male', 'border-pink': friend.gender === 'female'}">
          <template #header>
              <img :src="friend.profile" :alt="friend.firstName" class="img-fluid" loading="lazy" width="200px" height="50px">
            </template>
            <template #body>
              <h3>{{ friend.firstName }} {{ friend.lastName }}</h3>
            <p>ID: {{ friend.id }}</p>
            <p>Gender: {{ friend.gender }}</p>
            <p>Profile:</p>

          </template>
        </Card>
      </div>
      <div v-else class="spinner-border" role="status">
        <span class="sr-only">Loading...</span>
      </div>
    </div>
  </template>
  
  <script>
  import Card from '@/components/Card.vue';
  
  export default {
    name: 'FriendsComp',
    components: { Card },
    data() {
      return {
        friends: [
          { id: 1, firstName: 'Yakupha', lastName: 'Ntonintshi', gender: 'female', profile: 'https://simanyests.github.io/Images/images/20240422_100127.jpg' },
          { id: 2, firstName: 'Mbalentle', lastName: 'Diko', gender: 'female', profile: 'https://simanyests.github.io/Images/images/20240422_100654.jpg' },
          { id: 3, firstName: 'Khanya', lastName: 'Pupuma', gender: 'male', profile: 'https://simanyests.github.io/Images/images/IMG-20231017-WA0028.jpg' }
        ]
      };
    }
  }
  </script>
  
  <style>
  .border-gold {
    border-color: gold !important;
  }
  
  .border-pink {
    border-color: pink !important;
  }
  
  .img-fluid {
    max-width: 100%;
    height: auto;
  }
  </style>
  