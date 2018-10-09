<template>
    <div>
        <div id="add-blog">
            <h2>Add a New Blog Post</h2>
            <form action="">
                <label for="">Blog Title:</label>
                <input type="text" required v-model.lazy="blog.title">
                <label for="">Blog Content:</label>
                <textarea v-model.lazy="blog.content" name="" id="" cols="30" rows="10"></textarea>
                <div id="checkboxes">
                    <label for="">Ninjas</label>
                    <input type="checkbox" value="ninjas" v-model="blog.categories">
                    <label for="">Wizards</label>
                    <input type="checkbox" value="wizards" v-model="blog.categories">
                    <label for="">Kashuri</label>
                    <input type="checkbox" value="kashuri" v-model="blog.categories">
                    <label for="">Nakamuro</label>
                    <input type="checkbox" value="nakamuro" v-model="blog.categories">
                </div>
                <label for="">Author:</label>
                <select v-model="blog.author" name="" id="">
                    <option v-for="author in authors">{{author}}</option>
                </select>
            </form>
            <div id="preview">
                <h3>Preview</h3>
                <p>Blog title: {{blog.title}}</p>
                <p>Blog content:</p>
                <p>{{blog.content}}</p>
                <p>Blog Categories:</p>
                <ul>
                    <li v-for="category in blog.categories">{{category}}</li>
                </ul>
                <p>Author: {{blog.author}}</p>
            </div> 
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                blog: {
                    title: "",
                    content: "",
                    categories: [],
                    author: ""
                },
                authors: ['The Net Ninjf','The Angular Avenger', 'The Vue Vindicator']
            }
        }
    }
</script>

<style>
    #add-blog *{
        box-sizing: border-box;
    }
    #add-blog {
        margin: 20px auto;
        max-width: 500px;
    }
    label {
        display: block;
        margin: 20px 0  10px;
    }
    input[type="test"].textarea {
        display: block;
        width: 100%;
        padding: 8px;
    }
    #preview {
        padding: 10px 20px;
        border: 1px dotted #ccc;
        margin: 30px 0;
    }
    h3 {
        margin-top: 10px;
    }
    #checkboxes input {
        display: inline-block;
        margin-right: 10px;
    }
    #checkboxes label {
        display: inline-block;

    }
    
</style>