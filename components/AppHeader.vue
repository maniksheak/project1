<template>
<div class="container">
     <div class="header">
      <h1 class="title">Manik Makes </h1>
      <ul>
        <li>
            <nuxt-link to="/">Home</nuxt-link>
        </li>
        <li>
            <nuxt-link to="/about">About</nuxt-link>
        </li>
        <li>
            <nuxt-link to="/contact">Contact</nuxt-link>
        </li>
        <li>
            <nuxt-link to="/jokes">Jokes</nuxt-link>
        </li>
      </ul>
   </div>
</div>
</template>

<script>
export default {
};
</script>

<style>
  .container {
      max-width: 900px;
    }
   .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
    padding-bottom: 1rem;
    border-bottom: 1px dotted #ccc;
   }

   .header .title {
    font-size: 3rem;
    color: #526488;
   }
   .header ul {
    display: flex;
     list-style: none;
   }
   .header a {
    text-decoration: none;
    display: inline-block;
    background: #333;
    color: #fff;
    padding: 0.5rem 1rem;
    margin-right: 1rem;
   }

   .header a:hover {
    background:rgb(223, 55, 214) ;
    color: #333;
   }
</style>