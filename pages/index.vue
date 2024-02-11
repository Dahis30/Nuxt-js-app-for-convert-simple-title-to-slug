<template>
  <div>

    <form>
      <label for="">Enter a title</label>
      <input type="text" v-model="title" >
    </form>
    <br>
    <button @click="generateSlug()">Generate a slug</button>
    <br>
    <br>
    <div>
      https://www.generateslug.com/ <span>{{ output }}</span>
    </div>

  </div>
 
</template>

<script>
export default {

  data:()=>({
    title:'',
    output:'',
  }),
  methods:{
    generateSlug(){

      // 1) convert the title to lowercasa
      var Slug = this.title.toLowerCase() ;

      // 2) replace the space around words with  dashes 
      var Slug = Slug.replace(/\s+/g,'-') ;

      // 3) replace ampersand with dashes and space
      var Slug = Slug.replace(/&/,'-and-')


      this.output= Slug;

    },
  }
}
</script>
