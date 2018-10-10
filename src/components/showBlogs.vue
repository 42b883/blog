<template>
  <div id="app">
    <div v-theme:colomn="'narrow'" id="show-blogs">
        <h1>All Blog Articles</h1>
        <input class="search" type="text" v-model="search" placeholder="search blogs">
        <div v-for="blog in filteredBlogs" class="single-blog">
            <router-link v-bind:to="'/blog/' + blog.id"><h2>{{blog.title | to-uppercase}}</h2></router-link>
             <article>{{blog.body  | snippet}}</article>
        </div>
    </div>
  </div>
</template>

<script>
import searchMixin from '../mixins/searchMixin';

export default {
 data() {
     return {
         blogs: [],
         search: ''
     }
 },
 methods: {

 },
 created() {
     this.$http.get('https://jsonplaceholder.typicode.com/posts').then(function(data){
         this.blogs = data.body.slice(0,10);
     })
 },
 computed: {
     filteredBlogs() {
         return this.blogs.filter((blog) => {
             return blog.title.match(this.search);
         })
     }
 },
filters: {
    toUppercase(value) {
        return value.toUpperCase();
    }
},
directives: {
    'rainbow': {
        bind(el,binding,vnode) {
            el.style.color = "#" + Math.random().toString().slice(2,8);
        }
    }
},
mixins: [searchMixin]


}
</script>

<style>
    #show-blogs {
        max-width: 800px;
        margin: 0 auto;
    }
    .single-blog {
        padding: 20px;
        margin: 20px 0;
        box-sizing: border-box;
        background: #eeeeee;
    }
    .search {
        width: 547px;
        height: 34px;
        padding: 5px;
    }
</style>


