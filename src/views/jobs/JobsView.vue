<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id" class="jobs">
    <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
      <h2>{{ job.title }}</h2>
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        { title: "UX Designer", id: 1, details: "lorem" },
        { title: "Wev Designer", id: 2, details: "lorem" },
        { title: "Vue Designer", id: 3, details: "lorem" },
      ],
    };
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
