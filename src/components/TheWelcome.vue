<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'

import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo"  src="https://kaziquest.com/assets/images/primary-logo.png" width="325" height="125" />
    <br/>
    <RouterLink to="/home">Need Help?</RouterLink>

    
  </header>



  <!--==================   1 EMployer  ================== -->
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
 
    <template style='color:black;'>Employer</template>
    <!-- This are the titles for all attributes of the software -->
    <template #heading>Company Name | Employer</template>

    <h4 style='color:black; font-size:30px; font-weight:700; letter-spacing: 0.4px; color: #333;'> Employer | Company </h4>

    This is the management section of the  app, you can Create and Edit :-  Employees, Company Inventory and Company Assets 
    <RouterLink to="/about">Login | Register</RouterLink>
    
  </WelcomeItem>

  <!-- =======================  2 EMployee =============== -->
  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    
    <template #heading>Employee</template>

    <h4 style='color:black; font-size:30px; font-weight:700; letter-spacing: 0.4px; color: #333;'> Employee </h4>

    Follow this link to view or edit your employee profile
    <RouterLink to="/view-inventory"> Employee Profile</RouterLink>
    <br>
    <span style="color:#999; font-size: 12px;"> Details can be edited by management too</span>
    
  </WelcomeItem>


  <!-- ======================= 3  Company Assets    =============== -->
  <WelcomeItem>


    <template #icon>
      <EcosystemIcon />
    </template>
    <h4 style='color:black; font-size:30px; font-weight:700; letter-spacing: 0.4px; color: #333;'> Company Assets</h4>



    To see exisiting Company Inventories follow the link : 
      <RouterLink to="/view-inventory">Company assets</RouterLink>
    <br>
  
    
  </WelcomeItem>


  <!-- -===================== 4    Company Inventory ================ -->
  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    
    <template #heading>Company Inventory</template>

    <h4 style='color:black; font-size:30px; font-weight:700; letter-spacing: 0.4px; color: #333;'> Company Inventory </h4>

    Company Asset was given to? Inventory assesment, Create New Inventory Assignment
    <RouterLink to="/view-inventory">Assign Company Assets</RouterLink>
    <br />

  </WelcomeItem>


  <!--==================== Time Off ==============  -->
  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading>Employee On Leave</template>

    <h4 style='color:black; font-size:30px; font-weight:700; letter-spacing: 0.4px; color: #333;'> Employee On Leave</h4>

    Create a new Off day record for employees to track days off.
    <RouterLink to="/view-inventory"> Create new Leave for employee </RouterLink>
    <br>

    Click to see all existing Leave Records
  <RouterLink to="/view-inventory">View Leave Records</RouterLink>
  </WelcomeItem>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 40vh;
}

.logo {
  display: block;
  margin: 1rem 0 0 0 0;
  width: 100%;
  
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {

    display: block;
    place-items: center; 
    background-color: #0d6dfd26;
    padding-left: 30px;
    padding-right: 26px;
    padding-bottom: 10px;
    padding-top: 10px;
    border-radius: 6px;

    margin-right: 30px;
    margin-bottom: 20px;
  }

  .logo {
    margin: 1rem 1rem 0 0;
   
  }

  header .wrapper {
    display: block;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>


