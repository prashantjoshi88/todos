<template>
<div class="q-pa-md row items-start q-gutter-md">
    <q-card class="my-card">
      <q-card-section>
        <div class="q-pa-md">
    <q-table
    
      title="Treats"
     
      :rows="bata"
      row-key="name"
      dark
      color="amber"
    />
  </div>
      </q-card-section>
    </q-card>
  <h1>Employee</h1>
<!-- <table border="2">
  <tr>
    <th>
      Name
    </th>
    <th>
      Salary
    </th>
    <th>
      Age
    </th>
  </tr>
  <tr v-for="item in bata" :key="item.id">
    <td>
      {{item.employee_name}}
    </td>
    <td>
      {{item.employee_salary}}
    </td>
    <td>
      {{item.employee_age}}
    </td>
  </tr>
</table> -->
 <!-- <div class="q-pa-md">
    <q-table
    v-for="item in bata" :key="item.id"
      title="Treats"
      :rows="[{
        name: item.employee_name,
        Salary: item.employee_salary,
        age: item.employee_age
      }]"
      :columns="columns"
      row-key="name"
      dark
      color="amber"
    /> -->
  </div> 
</template>
<script>



export default {
  name: "index",
  data(){
    return{
      bata :[]
    }
  },
  mounted(){
    this.$axios('http://dummy.restapiexample.com/api/v1/employees').then((resp)=>{
      console.log(resp.data.data)
      this.bata = resp.data.data
    })
  }
}
</script>
