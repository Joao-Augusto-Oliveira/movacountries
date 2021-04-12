<template>
  <div>
    <div class="card" v-for="(country, index) in countries" :key="index">
      <img class="flag" :src="flag" alt="flag" />
      <ul id="features">
        <li>Nome: {{ name }}</li>
        <li>Capital: {{ capital }}</li>
        <li>Região: {{ region }}</li>
        <li>Sub-região: {{ subregion }}</li>
        <li>População: {{ population }}</li>
        <li>Língua: {{ languages }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      countries: [
        {
          flag: ""
        }
      ]
    };
  },
  props: {
    url: String,
    name: String,
    capital: String,
    region: String,
    subregion: String,
    languages: String,
    population: Number,
    flag: String
  }
};
</script>

<style>

.card {
  display:flex;
  box-sizing: border-box;
  align-items: center; 
  justify-content: center; 
  margin-top: 2rem;
  padding: 0.5rem 
}

.flag {
  width: 27.68rem;
  height: 16.125rem;  
}

#features {
  font: 400 1.125rem Montserrat;
  color: #454545;
  line-height: 2.5rem;
  
}

</style>