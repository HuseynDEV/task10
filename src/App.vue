<template>
  <div id="app">
    <header-side></header-side>

    <div class="px-[120px] mt-5">
      <div class="flex gap-x-5">
        <div class="w-[20%]">
          <filter-side
            :changeData="changeData"
            :sortingDataRating="sortingDataRating"
            :sortingDataCount="sortingDataCount"
          ></filter-side>
        </div>
        <div class="w-[80%]">
          <user-container :data="data"></user-container>
        </div>
      </div>
    </div>
    <download-side></download-side>
    <footer-side></footer-side>
  </div>
</template>

<script>
import HeaderSide from "./components/HeaderSide";
import FilterSide from "./components/FilterSide";
import UserContainer from "./components/UserContainer";
import DownloadSide from "./components/DownloadSide";
import FooterSide from "./components/FooterSide";
import { taskers } from "./data";

export default {
  name: "App",
  components: {
    HeaderSide,
    FilterSide,
    UserContainer,
    DownloadSide,
    FooterSide,
  },

  data() {
    return {
      data: taskers,
      sortingAccess:''
    };
  },

  methods: {
    changeData(item) {
      this.data = taskers;
      if (item == "supervisor") {
        this.data = this.data.filter((data) => {
          return data.supervisor == true;
        });
      } else if (item == "eliteTasker") {
        this.data = this.data.filter((data) => {
          return data.eliteTasker == true && data.supervisor == false;
        });
      } else if (item == "newbie") {
        // time ile bezi problmeler yasadigim ucun bu sekilde yazdim
        this.data = this.data.filter((data) => {
          if (data.startDate != null) {
            return data.eliteTasker == false && data.supervisor == false;
          }
          
        });
      }
    },



    sortingDataRating(value) {

        if (value == "ascending") {
        this.data = this.data.sort((a, b) => a.averageRating - b.averageRating);
      } else if (value == "descending") {
        this.data = this.data.sort((a, b) => b.averageRating - a.averageRating);
      }
      
    },
    sortingDataCount(value) {
      if (value == "ascending") {
        this.data = this.data.sort(
          (a, b) => a.completedTasks - b.completedTasks
        );
      } else if (value == "descending") {
        this.data = this.data.sort(
          (a, b) => b.completedTasks - a.completedTasks
        );
      }
    },
  },
};
</script>

<style></style>
