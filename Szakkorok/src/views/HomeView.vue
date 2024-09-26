<template>
  <div class="container">
    <h2>Tanulók és szakkörök</h2>
    <table class="table table-bordered">
      <thead>
        <tr>
          <th>Név</th>
          <th>Osztály</th>
          <th>Szakkör</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(student, index) in students" :key="index">
          <td>{{ student.name }}</td>
          <td>{{ student.class }}</td>
          <td>
            <select v-model="student.selectedActivity" class="form-select">
              <option v-for="activity in activities" :key="activity" :value="activity">
                {{ activity }}
              </option>
            </select>
          </td>
        </tr>
      </tbody>
    </table>

    <pre>{{ students }}</pre>
</div>
</template>

<script>
export default {
  data() {
    return {
      students: [
        { nev: "Oláh Péter", osztaly: "13D", selectedActivity: null },
        { nev: "Nagy Ferenc", osztaly: "14K", selectedActivity: null },
        { nev: "Juhász Kristóf", osztaly: "2C", selectedActivity: null },
      ],
      activities: ["Foci", "Röpi", "Színjátszás", "Nincs szakkör"],
    };
  },
};
</script>

<style scoped>

</style>