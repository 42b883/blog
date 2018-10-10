<template>
    <nav>
        <ul>
            <li><router-link to="/" exact>Blog</router-link></li>
            <li><router-link to="/add" exact>Add a New Blog</router-link></li>
        </ul>
    </nav>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    ul {
        list-style-type: none;
        text-align: center;
        margin: 0;
    }
    li {
        display: inline-block;
        margin: 2px 10px 2px 10px;
        border: 2px solid transparent;
    }
    li:hover {
        background: rgb(58, 180, 129);
        border:2px solid #50b482;
        background: rgba(0,0,0,0);
    }
    a {
        color: #ffffff;
        text-decoration: none;
        padding: 6px 8px;
        border-radius: 10px;
    }
    nav {
        background: #002;
        padding: 14px 0;
        margin-bottom: 40px;
        height: 24px;
    }
    .router-link-active {

    }
</style>

