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
 
  
  <h2>
    
  </h2>

  <div class="Employer">

    <nav>
      <br>
      <br>
      <RouterLink to="/about" class="top-button">New Employee</RouterLink>
      <RouterLink to="/about" class="top-button"> Register New Inventory</RouterLink>
      <RouterLink to="/about" class="top-button">Update Employee</RouterLink>
      <RouterLink to="/about" class="top-button">Inventory</RouterLink>
    </nav>

    <br>
    <h2 style="text-align: Center; margin-bottom: 1rem; color: #333; font-size: 40px;">Employee</h2>
    
    <table>
      <tr>
        
      <tr>
        <th>Employer</th>
        <th>Date Of Birth</th>
        <th>Role</th>
        <th>KRA pin</th>
        <th>Phone Numbers</th>
      </tr>
      
      </tr>
      
    </table>    
    <table style="">
    
     
      <tr>
        <div v-for="datas in data" key="data.pk" >
      
          <tr>
            <td >{{ datas.employer_name }}</td>
            <td>{{ datas.dob }}</td>
            <td>{{ datas.role }}</td>        
            <td>{{datas.kra_pin}}</td>
            <td>{{ datas.phone_number }}</td>
            
          </tr>
          
          </div>
        
      </tr>
      
    </table>

    <br>
    <br>
    <h2 style="text-align: Center; margin-bottom: 1rem; color: #333; font-size: 40px;"> On Leave</h2>
    
    <table>
      <tr>

        
      <tr>
        <th>User</th>
        <th>Start Date</th>
        <th>End Date</th>
        <th>Comments</th>
      </tr>
      
      </tr>
      
    </table>    
    <table style="">
    
     
      <tr>
        <div v-for="datas in leave" key="data.pk" >
      
          <tr>
            <td >{{ datas.user }}</td>
            <td>{{ datas.start }}</td>
            <td>{{ datas.end }}</td>        
            <td>{{datas.comments}}</td>
            
          </tr>
          
          </div>

          
      </tr>
      
    </table>

    <br>
    <br>
    <h2 style="text-align: Center; margin-bottom: 1rem; color: #333; font-size: 40px;">Assets</h2>
    
    <table>
      <tr>
      <tr>
        <th>Asset ID</th>
        <th>Asset Name</th>
        <th>Available</th>
        <th>Price</th>
      </tr>
      
      </tr>
      
    </table>  
    
    <table style="">
    
     
      <tr>
        <div v-for="datas in asset" key="data.pk" >
      
          <tr>
            <td >{{ datas.pk }}</td>
            <td >{{ datas.asset_name }}</td>
            <td>{{ datas.available }}</td>
            <td> --</td>  
            
          </tr>
          
          </div>
        
      </tr>
      
    </table>

    <br>
    <br>
    <h2 style="text-align: Center; margin-bottom: 1rem; color: #333; font-size: 40px;">Inventory</h2>
    
    <table>
      <tr>
        
      <tr>
        <th>ID</th>
        <th>Asset ID</th>
        <th>Borrowed-On</th>
        <th>Returned-On</th>
      </tr>
      
      </tr>
      
    </table>  
    
    <table style="">
    
     
      <tr>
        <div v-for="datas in inventory" key="data.pk" >
      
          <tr>
            <td >{{ datas.pk }}</td>
            <td>{{ datas.asset_id }}</td>
            <td>{{ datas.taking }}</td>        
            <td>{{datas.returning}}</td>
            
          </tr>
          
          </div>
        
      </tr>
      
    </table>

    <br>
    <br>
    <h2 style="text-align: Center; margin-bottom: 1rem; color: #333; font-size: 40px;"> Management Made Easy</h2>
    <table style="">
    
      <tr>
        <th>-</th>
        <th>-</th>
        <th>-</th>
        <th>-</th>
        <th>-</th>
        <th>-</th>
        <th>-</th>
        <th>-</th>
        <th>-</th>
        
        
        <th>-</th>
        
      </tr>
      <tr>
        <td>MariaAnders</td>
        <td>Germany</td>
        <td>MariaAnders</td>
        <td>Germany</td>
        <td>Germany</td>
        <td>MariaAnders</td>
        <td>Germany</td>
        <td>Germany</td>
        <td>MariaAnders</td>
        <td>Germany</td>
        
      </tr>
      
      
    </table>

    


    
  </div>
</template>


<script>
  export default {
    data() {
      return {
        data: null,
        asset: null,
        leave: null,
        inventory: null,
      };
    },
    methods: {
      async fetchData() { 
        /* Employee Fetch data */     
        const response = await fetch("http://127.0.0.1:8000/employee/");      
        this.data = await response.json();

        /* Asset fetch data */
        const assets = await fetch("http://127.0.0.1:8000/asset/");      
        this.asset = await assets.json();

        /* On Leave Fetch data */
        const leaves = await fetch("http://127.0.0.1:8000/timeoff/");      
        this.leave = await leaves.json();

        /* inventory fetch */
        const inventorys = await fetch("http://127.0.0.1:8000/inventory/");      
        this.inventory = await inventorys.json();
      },    
    },
    mounted() {
      this.fetchData();
    },
  };
</script>



<style scoped>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
  border-radius: 12px;
}
td{
  color: #666;
  background-color: #8194d613;
  border: 1px solid #999;
  font-size: 16px;
  font-weight: bold;
  margin-left: 20px;
  padding: 10px 25px 10px 25px;
  flex-wrap: nowrap;
  width: 250px;

  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
 th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 18px;
  color: #ffffff;
  font-size: 18px;
  
  background-color: hsla(206, 100%, 37%, 0.865);
   width: 250px; 
}

tr:nth-child(even) {
  background-color: #ffffff;
  width: 200px;
}
h2{
  font-family: 'Times New Roman', Times, serif;
}

.top-button{
  padding: 10px 8px 10px 8px;
  background-color: hsla(206, 96%, 44%, 0.829);
  margin: 10px;
  width: 90px;
  color: white;
  border-radius: 6px;
  font-size: 15px;

  
  
}

.top-button:hover{
  padding: 10px 8px 10px 8px;
  background-color: hsla(206, 100%, 28%, 0.865);
  margin: 10px;
  width: 90px;
  color: white;
  font-size: 20px;

  
  
}
</style>



