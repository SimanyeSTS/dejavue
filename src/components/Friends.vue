<template>
    <div>
      <div v-if="friends.length > 0">
        <Card v-for="friend in friends" :key="friend.id" :class="{'border-gold': friend.gender === 'male', 'border-pink': friend.gender === 'female'}">
          <template v-slot:header>
            <h3>{{ friend.firstName }} {{ friend.lastName }}</h3>
          </template>
          
          <template v-slot:body>
            <p>ID: {{ friend.id }}</p>
            <p>Gender: {{ friend.gender }}</p>
            <p>Profile: {{ friend.profile }}</p>
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
            { id: 1, firstName: 'Yakupha', lastName: 'Ntonintshi', gender: 'female', profile: '' },
            { id: 2, firstName: 'Mbalentle', lastName: 'Diko', gender: 'female', profile: ''},
            { id: 3, firstName: 'Khanya', lastName: 'Pupuma', gender: 'male', profile: '' },
          
        ]
      };
    }
  }
  </script>
  
  <style>
  .border-gold {
    border-color: gold;
  }
  
  .border-pink {
    border-color: pink;
  }
  </style>
  