<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <br />
    <span> {{ message1 }} </span> <br />
    <span v-text="message1"></span>
    <hr />
    <span> {{ counter }} </span> <br />
    <button v-on:click="counter = counter + 1">+</button>
    <button v-on:click="minus">-</button>
    <hr />
    <span> {{ message3 }} </span> <br />
    <input type="text" v-bind:value="message3" />
    <input type="text" v-model="message3" />
    <select v-model="message3">
      <option value="choice01">Hello 1 !!</option>
      <option value="choice02">Hello 2 !!</option>
      <option value="choice03">Hello 3 !!</option>
    </select>
    <textarea v-model="message3"></textarea>
    <hr />
    <input v-bind:type="message3" />xxx<br />

    <img v-bind:src="require(`@/assets/images/` + imagename)" />
    <select v-model="imagename">
      <option value="img01.jpg">Image 1</option>
      <option value="img02.jpg">Image 2</option></select
    ><br /><br />
    <hr />

    <h1 v-show="isGreeting">Hello !!</h1>

    <hr />
    {{ htmlText }}<br />
    <span v-html="htmlText"></span>
    <hr/>

  <div v-bind:key="emp.id" v-for="emp in employees">
    <b>Id</b>: {{emp.id}},<br/>
    <b>Name</b>: <span v-bind:class="(emp.Salary>90000) ? 'high' : (emp.Salary>=30000) ? 'medium' : 'low' ">{{emp.name}}</span>,<br/>
    <b>Salary</b>: {{emp.Salary}}
    <span v-if="emp.Salary>90000">***</span>
    <span v-else-if="emp.Salary>=30000">**</span>
    <span v-else>*</span>
    <br/><br/><br/>
  </div>

  <hr/>
<div v-bind:key="std.studentId" v-for="std in students"> 
    <b>studentId :</b> {{std.studentId}},<br/>
    <b>firstname :</b> {{std.firstname}},<br/>
    <b>lastname :</b> {{std.lastname}},<br/>
    <b>score :</b> {{std.score}},<br/><br/><br/>
  </div>


    <input v-bind:type="inputtype" />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
  },
  data(){
    return{
      message1: "Hello World!!",
      message2 : "Helle World Again!!!",
      message3 : "Type Here!",
      inputtype: "text",
      imagename: "img01.jpg",
      counter: 0,
      htmlText: "<b>HTML TEXT</b>&nbsp;",
      isGreeting: true,
      employees:[{"id":1,"name":"John","Salary":30000},{"id":2,"name":"Trump","Salary":10000},{"id":3,"name":"Peter","Salary":99000}],
      students:[{"studentId":624235049,"firstname": "Suban","lastname":"Noksang","score":"100"},{"studentId":624235048,"firstname": "Warinthon","lastname":"kongjan","score":"100"},{"studentId":624235043,"firstname": "Natthawut","lastname":"Bunwisoot","score":"100"},{"studentId":624235043,"firstname": "Pathipan","lastname":"Siriwathano","score":"100"}]
    }  
  },
  methods: {
    minus: function() {
      this.counter=this.counter-2
    }

  }


}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.high{
  color: rgb(243, 52, 52);
}
.medium{
  color: rgb(0, 139, 253);
}
.low{
  color: rgb(22, 173, 22);
}
</style>