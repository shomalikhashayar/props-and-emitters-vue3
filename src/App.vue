<template>
  <card :userData="userData" @readMore="readMore" />
  <div id="myModal" class="modal" v-if="showModal">
    <!-- Modal content -->
    <div class="modal-content">
      <span class="close" @click="showModal = false">&times;</span>
      <p>{{ userData[0].description }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Card from "./components/Card.vue";
const showModal = ref(false);
const userData = ref([
  {
    id: "001",
    name: "Khashayar Shomali",
    jobTitle: "Front-end Developer(Vue.js)",
    description:
      "Khashayar Shomali is a talented and innovative Front-End Developer, specializing in Vue.js, who has made significant contributions to the world of web development. With a passion for crafting seamless user experiences and a keen eye for design, Khashayar has earned a reputation for building cutting-edge and visually stunning web applications.",
  },
  {
    id: "002",
    name: "Yousef Aria",
    jobTitle: "Front-end Developer(Vue.js)",
    description:
      "Yousef Aria is a talented and innovative Front-End Developer, specializing in Vue.js, who has made significant contributions to the world of web development. With a passion for crafting seamless user experiences and a keen eye for design, Khashayar has earned a reputation for building cutting-edge and visually stunning web applications.",
  },
  {
    id: "003",
    name: "Mohammad Saba",
    jobTitle: "Front-end Developer(React.js)",
    description:
      "Mohammad Saba is a talented and innovative Front-End Developer, specializing in React.js, who has made significant contributions to the world of web development. With a passion for crafting seamless user experiences and a keen eye for design, Khashayar has earned a reputation for building cutting-edge and visually stunning web applications.",
  },
  {
    id: "004",
    name: "Ali Mohammadi",
    jobTitle: "UI/UX Designer",
    description:
      "Ali Mohammadi is a talented and innovative UI/UX Designer, specializing in Figma, who has made significant contributions to the world of web development. With a passion for crafting seamless user experiences and a keen eye for design, Khashayar has earned a reputation for building cutting-edge and visually stunning web applications.",
  },
]);

function readMore() {
  showModal.value = true;
}
</script>

<style>
body {
  background-color: rgb(169, 188, 140);
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: sans-serif;
  overflow: hidden;
}

.modal {
  position: fixed; 
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%; 
  height: 100%; 
  overflow: auto; 
  background-color: rgb(0, 0, 0); 
  background-color: rgba(0, 0, 0, 0.4); 
}

.modal-content {
  background-color: #fefefe;
  border-radius: 16px;
  font-size: 24px;
  font-weight: bold;
  line-height: 3rem;
  margin: 15% auto; 
  padding: 16px 24px;
  border: 1px solid #888;
  width: 80%; 
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
</style>
