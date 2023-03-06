<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import Employer from '../components/Employer.vue';
</script>

<template>
  <header>
    <img alt="Vue logo" style="margin-top: 30px;" class="logo"  src="https://kaziquest.com/assets/images/primary-logo.png" width="300" height="80" />
    <br/>
    <RouterLink to="/"> ⬅ Back</RouterLink>

    
  </header>
    <Employer />
  
</template>
