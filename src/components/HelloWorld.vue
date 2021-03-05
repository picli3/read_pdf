<template>
  <div v-html="res3"></div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      links:[],
      res3: ""
    };
  },

  async created(){
      const headers = { "Content-Type": "text/html" };
      const myRequest = new Request('http://dl.icdst.org/pdfs/files/');

      const res = await fetch(myRequest,{headers})
      
      this.res3=await res.text()
      this.links = await document.getElementsByTagName("a") 


      
      
 
  }

}
</script>