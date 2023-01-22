<template>
  <div id="accordion" v-for="(data, i) in formDataArray" v-bind:key="i">
    <div class="card">
      <div class="card-header" :id="'heading' + i">
        <h5 class="mb-0">
          <button
            class="btn btn-link collapsed"
            data-toggle="collapse"
            :data-target="'#collapse' + i"
            aria-expanded="true"
            :aria-controls="'collapse' + i"
          >
            [ {{ data.date }} ] {{ data.name }}
          </button>
        </h5>
      </div>

      <div
        :id="'collapse' + i"
        class="collapse show"
        aria-labelledby="headingOne"
        data-parent="#accordion"
      >
        <div class="card-body">
          <p class="mb-0"><strong>เขียนที่: </strong>{{ data.WriteNo }}</p>
          <p class="mb-0"><strong>วันที่: </strong>{{ data.date }}</p>
          <p class="mb-0"><strong>ชื่อ-นามสกุล: </strong>{{ data.name_lastname }}</p>
          <p class="mb-0"><strong>คะแนนที่สอบได้: </strong>{{ data.score }}</p>
          <p class="mb-0"><strong>โรงเรียน: </strong>{{ data.school }}</p>
          <p class="mb-0"><strong>เมื่อ: </strong>{{ data.date_end }}</p>
          <p class="mb-0"><strong>ที่อยู่ปัจจุบัน: </strong>{{ data.home }}</p>
          <p class="mb-0"><strong>โทรศัพท์: </strong>{{ data.tel }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
defineProps({
  formDataArray: Array,
});
</script>
<style scoped>
</style>
