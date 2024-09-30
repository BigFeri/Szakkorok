<template>
  <div class="my-container">
    <h1 class="sticky-top">Szakkörök</h1>
    <div class="row">
      <table class="table">
        <thead>
          <tr>
            <th scope="col">Tanuló</th>
            <th scope="col">Osztály</th>
            <th scope="col">Szakkör</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="diak in diakok" :key="diak.id">
            <td>{{ diak.nev }}</td>
            <td>{{ diak.osztaly }}</td>
            <td>
              <select class="form-select" v-model="diak.szakkorId" @change="TanuloSzakkor(diak)">
                
              </select>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      diakok: [
        { id: 1, nev: "Németh László", osztaly: "9.B", szakkorId: 4 },
        { id: 2, nev: "Kovács Zita", osztaly: "10.A", szakkorId: 4 },
        { id: 3, nev: "Farkas Péter", osztaly: "11.B", szakkorId: 4 },
        { id: 4, nev: "Varga Eszter", osztaly: "9.B", szakkorId: 4 },
        { id: 5, nev: "Hegedűs Dávid", osztaly: "10.A", szakkorId: 4 },
        { id: 6, nev: "Szőke Katalin", osztaly: "11.B", szakkorId: 4 },
        { id: 7, nev: "Molnár Gábor", osztaly: "10.A", szakkorId: 4 },
        { id: 8, nev: "Kiss Anikó", osztaly: "9.B", szakkorId: 4 },
        { id: 9, nev: "Barna Tamás", osztaly: "10.A", szakkorId: 4 },
        { id: 10, nev: "Tóth Júlia", osztaly: "11.B", szakkorId: 4 },
        { id: 11, nev: "Fekete Anna", osztaly: "10.A", szakkorId: 4 },
        { id: 12, nev: "Nagy Balázs", osztaly: "11.B", szakkorId: 4 },
        { id: 13, nev: "Sipos Mária", osztaly: "9.B", szakkorId: 4 },
        { id: 14, nev: "Kerekes János", osztaly: "11.B", szakkorId: 4 },
        { id: 15, nev: "Varga Csilla", osztaly: "10.A", szakkorId: 4 },
      ],
      activities: [
        {
          id: 1,
          nev: "Football",
        },
        {
          id: 2,
          nev: "Röplabda",
        },
        {
          id: 3,
          nev: "Dráma",
        },
        {
          id: 4,
          nev: "Nem jár szakkörre",
        },
      ],
      szakkorTanulo:{
        Football:[],
        Röplabda:[],
        Dráma:[]
      }
    };
  },
};
</script>

<style>
</style>