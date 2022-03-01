<template>
  <button @click="adder()">count: {{ count }}</button>
  <br />
  <div class="space-y-2 p-1">
    <UserCard
      v-for="n in stops"
      v-bind="n"
      :key="n['設置位置']"
      class="rounded-lg border border-gray-400 bg-white p-1.5"
    />
  </div>
</template>

<script>
import axios from "axios";
import UserCard from "./components/UserCard.vue";

export default {
  data() {
    return {
      count: 0,
      users: [
        { id: 1, name: "John", email: "john1@gmail.com" },
        { id: 2, name: "Marry", email: "marry2@gmail.com" },
      ],
      stops: [],
      url: "https://data.tainan.gov.tw/dataset/c8c29fd8-5731-4723-8df1-44d31d3c0429/resource/c372392b-2b73-4abf-909f-5075fa378732/download/opendata.json",
    };
  },
  mounted() {
    axios.get(this.url).then((response) => {
      // handle success
      this.stops = response.data;
    });
  },
  methods: {
    adder() {
      this.users.push({
        id: 3,
        name: "Paul",
        email: "paul3@gmail.com",
      });
    },
  },
  components: {
    UserCard,
  },
};
</script>
