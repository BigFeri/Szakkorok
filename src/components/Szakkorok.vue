<template>
  <div class="card card-border-dark">
    <div class>{{ szakkor.nev }}</div>
    <div class="card-body text-dark">
      <span class="span" v-for="(diak, index) in Szakkorosok" :key="diak.id"
        >{{ diak.nev }}<span v-if="index < Szakkorosok.length - 1">, </span>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["szakkor", "diakok"],
  computed: {
    Szakkorosok() {
      return this.diakok
        .filter((d) => d.szakkorId === this.szakkor.id)
    },
  },
};
</script>

<style scoped>
.card {
  background: linear-gradient(135deg, rgba(240, 240, 240, 0.9), rgba(200, 200, 200, 0.9));
  border-radius: 10px;
  padding: 20px;
  margin-bottom: 20px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.5);
}

.card-header {
  font-size: 1.5rem;
  font-weight: bold;
  color: #343a40; /* Sötétszürke szín */
  text-align: center;
  padding: 10px;
  border-radius: 10px 10px 0 0;
  background: #ffffff; /* Fehér háttér */
  border-bottom: 2px solid #007bff; /* Kék alsó határ */
}

.card-body {
  color: #495057; /* Világos szürke */
  padding: 15px;
}

.span {
  display: inline-block;
  margin-right: 5px;
  color: #007bff; /* Kék szín */
  font-weight: 500;
}

.span:hover {
  color: #0056b3; /* Sötétebb kék hover hatás */
  transition: color 0.3s ease;
}
</style>
