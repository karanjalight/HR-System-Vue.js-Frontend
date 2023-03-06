<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import Employer from '../components/Employer.vue';
</script>

<template>
  <header>
    <img alt="Vue logo" style="margin-top: 18rem; padding-right: 4rem;" class="logo"  src="https://kaziquest.com/assets/images/primary-logo.png" width="495" height="120" />
    <br/>
    <RouterLink to="/about"> &nbsp; Need Help?</RouterLink>

    
  </header>
  
  <div style="height: 700px; margin-top:60px;"> 
    <h2 class="title"> Welcome To KaziQuest </h2>
    <h3 class="title"> Register </h3>
    <form @submit="register">
      <input type="text" placeholder="Enter Name">
      <br>
      <input type="text" placeholder="Role in the Company">
      <br>
      <input type="text" placeholder="Company Name">
      <br>
      <input type="text" placeholder="Email">
      <br>
      <input type="text" placeholder="Phone Number">
      <br>
      <input type="text" placeholder="Number of employees">
      <br>
      <RouterLink to="/home"> <button> Register </button></RouterLink>
      <br>
      <p>Are you already registered? proceed to <RouterLink to="/login">Login</RouterLink></p>
      
    </form>
  </div>
    <!-- <Employer /> -->
  
</template>

<style>
h2{
 font-size: 45px;
 color: #444;
 text-align: center;
 letter-spacing: 0.4px;
 font-family: 'Times New Roman', Times, serif;
}
h3{
  font-size: 35px;
  color: #444;
  text-align: center;
  letter-spacing: 0.4px;
  font-family: 'Times New Roman', Times, serif;
 }

 form {
  margin-top: 20px;
 }

 input{
  width: 100%;
  padding: 10px 10px 10px 10px;
  margin-bottom: 20px;
  border: none;
  box-shadow: 0px 0px 2px 2px #9999994a;
  border-radius: 6px;
  font-size: 15px;
 }

 button {
  padding: 10px;
  background-color: rgba(3, 81, 191, 0.88);
  color: white;
  font-size: 16px;
  border: none;
  border-radius: 6px;
  width: 150px;

 }

 
 button:hover {
  padding: 10px;
  background-color: rgba(17, 92, 196, 0.88);
  color: white;
  font-size: 20px;
  border: none;
  border-radius: 6px;
  width: 150px;

 }

</style>
