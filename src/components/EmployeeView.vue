<template>
  <div class="items">
    <h3> Employee Details</h3>
  

   <table style="">
    
    <tr>





      <th >Employee</th>
      <th>Details</th>
    </tr
    ><tr>
      <td>Name:</td>
      <td>Paul_Karanja</td>
      
    </tr>
    <tr>
      <td>Email:</td>
      <td>Paulo@gmail.com</td>
      
      
    </tr>
    <tr>
      <td>Date Of Birth:</td>
      <td>23/02/1989</td>
      
      
    </tr>

    <tr>
      
      <td></td>
      <td></td>
      
    </tr>
    
  </table>



  <div v-for="datas in data" key="data.pk" >
    {{ datas.pk }}
    {{ datas.user }}
    {{ datas.role }}
    {{ datas.kra_pin }}
    {{ datas.phone_number }}
  </div>



   
  </div>
</template>

<script>
  export default {
    data() {
      return {
        data: null,
      };
    },
    methods: {
      async fetchData() {      
        const response = await fetch("http://127.0.0.1:8000/employee/");      
        this.data = await response.json();
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
  color: #444;
  font-size: 20px;
  font-family: 'Times New Roman', Times, serif;
  font-weight: 700;
  padding: 10px 25px 10px 10px;
  
  margin-bottom: 40px;
  text-align: left;
}
 th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 18px;
  color: #ffffff;
  font-size: 18px;
  font-size: 25px;
  
  background-color: hsla(206, 100%, 37%, 0.865);
   width: 100%; 
}

tr:nth-child(even) {
  background-color: #ffffff;
  width: 200px;
}


.items{
  margin-left: 10px;
}

.items h3{
  font-size: 35px;
  font-family: 'Times New Roman', Times, serif;
  color: #444;
  text-align: center;
  padding-bottom: 15px;
}
.items span{ 
  color: #444;
  font-size: 30px;
  font-family: 'Times New Roman', Times, serif;
  font-weight: 700;
  padding: 10px 25px 10px 10px;
  
  margin-bottom: 40px;
  text-align: right;

}

.items .attribute{ 
  text-align: center;
  color: hsla(206, 100%, 37%, 0.865);;
  font-size: 15px;
  font-family: 'Times New Roman', Times, serif;
  font-weight: 700;
  padding: 10px 40px 10px 10px;
  margin-bottom: 40px;

}

</style>

