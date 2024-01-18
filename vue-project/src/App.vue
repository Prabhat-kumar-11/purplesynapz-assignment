<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>


    <div >
     
      <nav class="Navbar">
        <RouterLink to="/"><button>Home</button></RouterLink>
        <RouterLink to="/about"><button>About</button></RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>


<style>

.Navbar{
  display: flex;
  gap: 55px;
 

}
.Navbar button {
  background-color: rgb(237, 237, 32);
  color: #0b2ba1;
  padding: 10px 20px;
  border: none; 
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer; 
  transition: background-color 0.3s ease;


  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);


  &:hover {
    background-color: rgb(133, 133, 2); 
  }
}
</style>

