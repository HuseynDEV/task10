<template>
  <div>
    <div>
      <h1 class="font-bold mb-7 text-2xl">Filters</h1>
      <div class="flex items-center gap-x-[11px] mb-3">
        <input
          type="radio"
          id="check1"
          class="w-[18px] h-[18px]"
          value="supervisor"
          @change="changeData(userData.filter)"
          v-model="userData.filter"
        />
        <label for="check1" class="text-[15px]">Supervisors</label>
      </div>
      <div class="flex items-center gap-x-[11px] mb-3">
        <input
          type="radio"
          id="check2"
          class="w-[18px] h-[18px]"
          value="eliteTasker"
          @change="changeData(userData.filter)"
          v-model="userData.filter"
        />
        <label for="check2" class="text-[15px]">Elite Tasker</label>
      </div>
      <div class="flex items-center gap-x-[11px] mb-3">
        <input
          type="radio"
          id="check3"
          class="w-[18px] h-[18px]"
          value="newbie"
          @change="changeData(userData.filter)"
          v-model="userData.filter"
        />
        <label for="check3" class="text-[15px]">Newbie</label>
      </div>
      <div class="flex items-center gap-x-[11px] mb-3">
        <input
          type="radio"
          id="check4"
          class="w-[18px] h-[18px]"
          value="all"
          @change="changeData(userData.filter)"
          v-model="userData.filter"
        />
        <label for="check4" class="text-[15px]">All</label>
      </div>
    </div>
    <div class="mt-7">
      <h1 class="font-bold mb-3 text-2xl">Sorting</h1>
      <div>
        <h3 class="my-3">By Rating</h3>
        <select
          name=""
          id=""
          class="p-2 w-[200px] border-solid border-[2px] border-[#C7C9CB]"
          @change="sortingDataRating(userData.sortingRating)"
          v-model="userData.sortingRating"
        >
          <option value="descending" selected>Descending</option>
          <option value="ascending">Ascending</option>
        </select>
      </div>

      <div>
        <h3 class="my-3">By Tasks Count</h3>
        <select
          name=""
          id=""
          class="p-2 w-[200px] border-solid border-[2px] border-[#C7C9CB]"
          @change="sortingDataCount(userData.sortingCount)"
          v-model="userData.sortingCount"
        >
          <option value="ascending">Ascending</option>
          <option value="descending" selected>Descending</option>
        </select>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["changeData", "sortingDataRating", "sortingDataCount"],

  data() {
    return {
      userData: {
        filter: "",
        sortingRating: "ascending",
        sortingCount: "descending",
      },
    };
  },

  methods:{
    sendEvent(){
      this.$emit('changeData', this.userData.filter)
    }
  }
};
</script>

<style></style>
