<template>
  <div id="app">
    <div class="container">
      
      <div class="row">
        <h2> Desafio Netsupport</h2> 
          <table border="2px" cellpadding = "5px" callpacing="0" id="alter">
            
            <thead>
              <tr>
                  <th>Id</th>
                  <th>Situação</th>
                  <th>Status</th>
                  <th>Tipo do serviço</th>
                  <th>cidade</th>
                  <th>Data agendamento</th>
                  <th>Data chegada</th>
              </tr>
            </thead>

            <tbody>
              
              <tr class="dif" v-for="Info in info" :key="Info.id">
                <td>{{ Info.id_job }}</td>
                <td id="color">{{ Info.situacao }}</td>
                <td>{{ Info.status }}</td>
                <td>{{ Info.tipo_servico }}</td>
                <td>{{ Info.cidade }}</td>
                <td>{{ Info.dh_agendamento_cliente }}</td>
                <td>{{ Info.dh_chegada }}</td>
              </tr>

            </tbody>
          </table>
      </div>
   </div>
  </div>
</template>


<script>

import Agenda from './services/agenda'


export default{
  
  nome: "App",
  data(){
    return{ 
      info: {}
    }
 },

 mounted(){
   Agenda.listar().then(resposta =>{
     this.info = resposta.data
     
   })

 }
}



</script>

<style>
budy,html
{
  width: auto;
  height: auto;
}
h2
{
  text-align: center;
  color: SkyBlue;
}
th
{
  width: 120px;
}
thead
{
  color:white;
}
tbody
{
  color: black;
}

/* linhas ímpares (odd) */
tbody td:nth-child(odd) {
    background-color: #FFF;
}

table
{
    
    background: #FFFFF0;
    border-collapse: collapse;
    text-align: center; 
    border-color: SkyBlue;
    
    
}
table#alter tr
{
  background:SkyBlue;
}
table#alter tr.dif {
	background: #eee;
}
@media(min-width: 700px) 
{
    table
  {
    margin: auto;
    
    
  }

}

.row
{
  margin-top: 10%;
}


</style>