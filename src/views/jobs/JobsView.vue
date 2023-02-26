<template>
  <h1>Jobs</h1>
  <div v-if="jobs.length">
    <div v-for="job in jobs" :key="job.id" class="jobs">
      <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
        <h2>{{ job.title }}</h2>
      </router-link>
    </div>
  </div>
  <div v-else>
    <p>Loading ...</p> 
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [],
    };
  },

  mounted() {
    fetch("http://localhost:3000/jobs")
      .then((response) => response.json())
      .then((data) => {
        this.jobs = data;
      })
      .catch((error) => {
        console.log(err.message);
      });
  },
};
</script>

<style>
.jobs h2 {
  background: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
  margin: 10px auto;
  max-width: 600px;
  cursor: pointer;
  color: #444;
}

.jobs h2:hover {
  background: #ddd;
}

.jobs a {
  text-decoration: none;
}
</style>
