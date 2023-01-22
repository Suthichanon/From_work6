<template>
  <table class="table" style="font-size: 8pt">
    <thead>
      <tr>
        <th>วันที่</th>
        <th>ชื่อ-นามสกุล</th>
        <th>คะแนนที่สอบได้</th>
        <th>โรงเรียน</th>
        <th>เมื่อ</th>
        <th>ที่อยู่ปัจจุบัน</th>
        <th>โทรศัพท์</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(data, i) in formDataArray" v-bind:key="i">
        <td>{{ data.WriteNo }}</td>
        <td>{{ data.date }}</td>
        <td>{{ data.name_lastname }}</td>
        <td>{{ data.score }}</td>
        <td>{{ data.school }}</td>
        <td>{{ data.date_end }}</td>
        <td>{{ data.home }}</td>
        <td>{{ data.tel }}</td>
      </tr>
    </tbody>
  </table>
</template>
<script setup>
defineProps({
  formDataArray: Array,
});
</script>
<style scoped></style>
