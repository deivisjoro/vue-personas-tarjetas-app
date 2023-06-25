<template>

    <header class="header">
        <div class="brand">
            <span>Vue.js</span>
            <small>Aplicaciones practicas</small>
        </div>
        <ul>
            <li><a href="#">Tarjetas Empleados</a></li>
            <li><a href="#">opcion2</a></li>
            <li><a href="#">opcion3</a></li>
        </ul>
    </header>
  
</template>

<style scoped>
    
  .header{
    height: 70px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #19177a;
    color: #fff;
    padding: 0 20px;
  }

  .header ul{
    display: flex;
    height: 100%;
    align-items: center;
  }

  .header li{
    padding: 10px;
    height: 100%;
    display: flex;
    align-items: center;
  }

  .header li:hover{
    background-color: #fff;
  }

  .header li:hover a{
    color: #19177a;
  }

  .header ul a{
    color: #fff;
    text-decoration: none;
  }

  .brand{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;  
  }

  .brand span{
    font-size: 22px;
  }
</style>