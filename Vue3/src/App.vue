<script>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
//tempat ngoding javascript

export default{
  data(){
    return{
      datasensor: "60",
      datasensor2: "80"
    };
  },
  created(){
    //this.getData();
  },
  methods: {
    async getData() {
      const data = await fetch("http://localhost:3000/sensor1");
      const datajson = await data.json()
      this.datasensor = datajson.sensor1
    }
  },
}

</script>

<template>
  <!--tempat ngoding html-->
  <div>Hello {{ datasensor }}
  <button @click="getData">Ambil Data</button>
  </div>
</template>

<style>
</style>
