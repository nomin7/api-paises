<template>
    <div>
        <div class="row">
            <input type="text" class="form-control col-12 col-md-9" placeholder="Buscar...">
             <b-form-select class="col-12 col-md-3" v-model="selectRegion" :options="regiones" @change="getRegiones()"></b-form-select>
        </div>

    <div class="row mt-5">
      <div class="col-6 col-md-4" v-for="(item, index) in paises" :key="index">
        <div class="card mb-3" style="max-width: 540px">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img :src="item.flag" class="card-img" alt="" />
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <h5 class="card-title">{{item.name}}</h5>
                <p><b>Capital: </b>{{item.capital}}</p>
                <p><b>Region: </b>{{item.region}}</p>
                <p><b>Sub-Region: </b>{{item.subregion}}</p>
                <p class="card-text">
                  <b>Pobliacion: </b><small class="text-muted">{{item.population}}</small>
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Paises',
    data() {
      return {
        paises: [],
        selectRegion: null,
        regiones: [
          {value: null, text: 'Seleccione una region'},
          {value: 'americas', text: 'America'},
          {value: 'europe', text: 'Europa'},
          {value: 'africa', text: 'Africa'},
          {value: 'asia', text: 'Asia'},
          {value: 'oceania', text: 'Oceania'},
        ]
      }
    },
    methods: {
      getRegiones(){
        if (this.selectRegion !== null) {
          const url = `https://restcountries.eu/rest/v2/region/${this.selectRegion}`;
          axios.get(url)
          .then(res => {
            console.log(res)
            this.paises = res.data
          })
          .catch(err => {
            console.error(err); 
          })
        }
        

      }
    },

    computed: {
      
    },
}
</script>