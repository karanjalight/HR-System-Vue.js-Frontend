<script setup>
import EmployeeView from '../components/EmployeeView.vue';

</script>

<template>
  <header>
    <img alt="Vue logo" style="margin-top: 18rem; padding-right: 4rem;" class="logo"  src="https://kaziquest.com/assets/images/primary-logo.png" width="495" height="120" />
    <br/>
    <RouterLink to="/"> &nbsp; ⬅ Back</RouterLink>

    
  </header>
  
  <EmployeeView class="detail" />

  <div class="detail" style="height: 1000px; background-color:;"> </div>
    <!-- <Employer /> -->
  
</template>

<style>
.detail{
  margin-top: 80px;
  height: 700px;
}

</style>
