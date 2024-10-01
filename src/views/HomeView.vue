<template>
  <div class="my-container">
    <h1 class="title">Szakkörök</h1>
    <div class="row">
      <div class="col-md-6">
        <table class="table table-striped">
          <thead>
            <tr>
              <th scope="col">Tanuló</th>
              <th scope="col">Osztály</th>
              <th scope="col">Szakkör</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="diak in diakok" :key="diak.id">
              <td class="my-td">
                <img src="../../public/g59.jpg" class="icon" />
                <!-- Itt van a PNG -->
                {{ diak.nev }}
              </td>
              <td class="my-td">{{ diak.osztaly }}</td>
              <td>
                <select
                  class="form-select"
                  v-model="diak.szakkorId"
                  @change="TanuloSzakkor(diak)"
                >
                  <option
                    v-for="szakkor in szakkorok"
                    :key="szakkor.id"
                    :value="szakkor.id"
                  >
                    {{ szakkor.nev }}
                  </option>
                </select>
              </td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="col-md-6">
        <div class="sticky-top">
          <h2 class="subtitle">Szakkörök</h2>
          <div class="row">
            <Szakkorok
              v-for="szakkor in szakkorok"
              :key="szakkor.id"
              :szakkor="szakkor"
              :diakok="diakok"
              class="col-6"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Szakkorok from "@/components/Szakkorok.vue";

export default {
  components: {
    Szakkorok,
  },
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
      szakkorok: [
        { id: 1, nev: "Football" },
        { id: 2, nev: "Röplabda" },
        { id: 3, nev: "Dráma" },
        { id: 4, nev: "Nem jár szakkörre" },
      ],
      szakkorTanulo: {
        Football: [],
        Röplabda: [],
        Dráma: [],
      },
    };
  },
  methods: {
    TanuloSzakkor(diak) {
      // Update student club selection logic
    },
  },
};
</script>

<style scoped>
.my-container {
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  animation: pulse 3s infinite;
}

.title {
  font-size: 2rem;
  margin-bottom: 20px;
  text-align: center;
  color: #333;
  animation: colorChange 5s infinite;
}

.subtitle {
  font-size: 1.5rem;
  margin-bottom: 15px;
  color: #555;
}

.table {
  background-color: white;
  border-radius: 8px;
  overflow: hidden;
}

.table th,
.table td {
  padding: 8px; /* Csökkentett padding */
  text-align: center;
  font-size: 0.9rem; /* Csökkentett betűméret */
}

.table th {
  background-color: #007bff;
  color: white;
}

.table-striped tbody tr:nth-of-type(odd) {
  background-color: #f2f2f2;
}

.form-select {
  border-radius: 5px;
  border: 1px solid #ccc;
  padding: 4px; /* Csökkentett padding */
  transition: border-color 0.3s, box-shadow 0.3s;
}

.form-select:focus {
  border-color: #007bff;
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
}

/* Animations */
@keyframes pulse {
  0% {
    box-shadow: 0 0 10px rgba(0, 123, 255, 0.7);
  }
  50% {
    box-shadow: 0 0 20px rgba(0, 123, 255, 0.4);
  }
  100% {
    box-shadow: 0 0 10px rgba(0, 123, 255, 0.7);
  }
}

@keyframes colorChange {
  0% {
    color: #ff4d4d;
  }
  25% {
    color: #ffcc00;
  }
  50% {
    color: #33cc33;
  }
  75% {
    color: #00ccff;
  }
  100% {
    color: #ff4d4d;
  }
}

.icon {
  width: 20px; /* Állítsd be az ikon szélességét */
  height: 20px; /* Állítsd be az ikon magasságát */
  margin-right: 8px; /* Kisebb távolság az ikon és a név között */
  vertical-align: middle; /* Igazítás a szöveggel */
}
</style>
