<template>
    <div>
        <div class="row">
            <input type="text" class="form-control col-12 col-md-9" placeholder="Buscar...">
             <b-form-select class="col-12 col-md-3" v-model="selectRegion" :options="regiones"></b-form-select>
        </div>

    <div class="row mt-5">
      <div class="col-6 col-md-4">
        <div class="card mb-3" style="max-width: 540px">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img src="" class="card-img" alt="" />
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <h5 class="card-title">El Salvador</h5>
                <p><b>Capital: </b></p>
                <p><b>Region: </b></p>
                <p><b>Sub-Region: </b></p>
                <p class="card-text">
                  <b>Pobliacion: </b><small class="text-muted"></small>
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
}
</script>