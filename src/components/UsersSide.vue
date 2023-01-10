<template>
  <div
    class="mr-[20px] w-[430px] mb-5 p-[24px] border-solid border-[1px] border-[rgba(199, 201, 203, 0.5)] rounded-md bg-gray-100"
  >
    <div class="flex items-center gap-x-3">
      <img
        class="w-[56px] h-[56px] rounded-[50%] object-cover"
        :src="dataItem.user.profile_picture.publicUrl"
      />

      <div>
        <p class="font-semibold text-[20px]">
          {{ dataItem.user.name + dataItem.user.surname }}
        </p>
        <div class="flex">
          <div class="flex items-center gap-x-1">
            <i
              class="fa-solid fa-star text-yellow-500 text-[12px]"
              v-for="item in Math.round(dataItem.star)"
              :key="item"
            ></i>
            <!-- <i class="fa-solid fa-star text-yellow-500 text-[12px]"></i>
            <i class="fa-solid fa-star text-yellow-500 text-[12px]"></i>
            <i class="fa-solid fa-star text-yellow-500 text-[12px]"></i>
            <i class="fa-solid fa-star text-yellow-500 text-[12px]"></i> -->
            <p class="text-yellow-500">{{ dataItem.star }}</p>
          </div>
          <div class="ml-3 text-[#979797]">({{ dataItem.comment }})</div>
        </div>
      </div>
    </div>

    <div class="flex items-center gap-x-[45px] my-[25px]">
      <div class="flex items-center gap-x-1">
        <img src="../images/Group 26286.png" />
        <h3 class="font-normal text-sm ml-2">{{ dataItem.completedTasks }}</h3>
      </div>
      <div class="flex items-center gap-x-1">
        <img src="../images/Hashtag.svg" />

        <h3 class="font-normal text-sm ml-2">
          {{
            dataItem.supervisor
              ? "Supervisor"
              : dataItem.eliteTasker
              ? "EliteTasker"
              : "Newbie"
          }}
        </h3>
      </div>
    </div>

    <div class="text-[#999999]">
      {{ dataItem.bio }}
    </div>

    <div class="flex items-center text-[#5920BC] justify-between mt-8">
      <div class="text-sm">View profile</div>
      <div class="text-xl font-semibold">${{ dataItem.price }}</div>
      <div>Book Now</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["dataItem"],
};
</script>

<style></style>
