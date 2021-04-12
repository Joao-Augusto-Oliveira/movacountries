<template>
  <div id="app">
    <Header />
    <div class="container">
      <input
        class="inputCountry"
        type="text"
        placeholder="Pesquisar País"
        v-model="busca"
      />
      <button class="btnSearch" @click="buscar">PESQUISAR</button>
    </div>
    <div v-for="(country, index) in filteredCountries" :key="index">
      <Country
        :name="country.name"
        :capital="country.capital"
        :region="country.region"
        :subregion="country.subregion"
        :population="country.population"
        :languages="country.languages[0].name"
        :flag="country.flag"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header";
import Country from "./components/Country";

export default {
  name: "App",
  data() {
    return {
      countries: [],
      busca: "",
      filteredCountries: []
    };
  },
  created: async function() {
    const response = await axios.get("https://restcountries.eu/rest/v2/all");
    if (response.status == 200) {
      this.countries = response.data;
      console.log(response.data);
    } else {
      console.error("Ocorreu erro na API");
    }
  },

  components: {
    Header,
    Country
  },
  methods: {
    buscar: function() {
      this.filteredCountries = this.countries;
      if (this.busca == "" || this.busca == " ") {
        this.filteredCountries = this.countries;
      } else {
        this.filteredCountries = this.countries.filter(
          countries => countries.name == this.busca
        );
      }
    }
  }
};
</script>

<style>
.container {
  display: flex;
  box-sizing: border-box;
  align-items: center;
  justify-content: center;
  margin-top: 2rem;
  padding: 0.5rem;
  gap: 1rem;
}
.inputCountry {
  border: 1px solid #a8a8a8;
  border-radius: 10px;
  box-sizing: border-box;
  font: 400 0.875rem Montserrat;
  color: #454545;
  line-height: 2.25rem;
  align-items: center;
  justify-content: center;
}

.btnSearch {
  background: #6d2080;
  border-radius: 10px;
  font: 400 0.875rem Montserrat;
  color: #ffffff;
  line-height: 2.25rem;
  cursor: pointer;
  width: 9.75rem;
  filter: brightness(0.8);
  transition: filter 0.2s;
}
</style>
