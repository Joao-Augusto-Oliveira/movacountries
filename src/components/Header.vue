<template>
  <div>
      <header class="headerContainer">
            <div class="headerContent">
                <img src="../assets/logo.svg" alt="logo mova"/> 
                <div class="buttonBack">
                    <a  href="/app">
                        <img src="../assets/return.svg" alt="back"/>
                        Voltar
                    </a>
                </div>
              
            </div>

    </header>

  </div>
</template>

<script>
export default {

}
</script>

<style>
.headerContainer {
    height: 5rem;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}

.headerContent {
    max-width: 1500px;
    height: 5rem;
    margin: 0 auto;
    padding: 0 2rem;
    display: flex;
    align-items: center;
   
}
.buttonBack {
    display: flex;
    margin-left: auto;
    
}

.buttonBack a {
    height: 2.25rem;
    width: 8.375rem;
    border-radius: 0;
    border: 1px solid #6D2080;
    box-sizing: border-box; 
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    font: 400 1.125rem Montserrat; 
}

.buttonBack a img {
margin-left: 8.33%;
margin-right: 12.5%;
margin-top: 25%;
margin-bottom: 25%;

}


</style>