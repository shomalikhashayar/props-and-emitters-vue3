<template>
  <main class="main">
    <div class="card" v-for="(item, index) in items" :key="index">
      <section class="card-container">
        <div class="img-container">
          <img src="../assets/khashayar.jpeg" alt="user profile pic" />
          <h2>{{ item.name }}</h2>
        </div>
        <div class="description">
          <div class="job-title">
            <spa>Job Title:</spa>
            <strong>{{ item.jobTitle }}</strong>
          </div>
          <div class="">
            <div class="bio">
              <p>
                {{ item.description }}
              </p>
            </div>
          </div>
        </div>
        <div class="actions">
          <button class="read-more-btn" @click="$emit('read-more', 1)">Read more...</button>
        </div>
      </section>
    </div>
  </main>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps(["userData"]);
const emit = defineEmits(["read-more"]);

const items = ref(props.userData);
</script>

<style scoped>
.card-container {
  width: 350px;
  height: 525px;
  background-color: gainsboro;
  border-radius: 16px;
  border: 1px solid rgb(167, 167, 167);
  box-shadow: 0 0 8px 0 rgba(0, 0, 0, 0.3);
}

img {
  width: 42px;
  border-radius: 100%;
  border: 2px white solid;
}

.img-container {
  background-color: rgb(157, 157, 157);
  height: 72px;
  display: flex;
  align-items: center;
  padding: 0 12px;
  gap: 20px;
  border-radius: 16px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}

h2 {
  font-size: 22px;
}

.job-title {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 20px;
}

.bio {
  background-color: white;
  border-radius: 8px;
  margin: 4px 20px 20px 20px;
  padding: 8px 16px;
  line-height: 28px;
  text-align: justify;

  max-height: 300px; /* Set a maximum height for the description */
  overflow: hidden; /* Hide any overflow */
  text-overflow: ellipsis; /* Show ellipsis (...) for long text */
}

.main {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 42px;
}

.read-more-btn {
  padding: 8px 16px;
  background-color: aquamarine;
  border: 1px solid rgb(43, 43, 43);
  border-radius: 8px;
  cursor: pointer;
}

.read-more-btn:hover {
  background-color: rgb(180, 255, 230);
  box-shadow: 0 0 8px 0 rgba(0, 0, 0, 0.3);
}

.actions {
  padding: 4px 20px;
}
</style>
