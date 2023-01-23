<template>
  <div class="container">
    <div class="row mt-5">
      <div class="col-md-4">
        <div class="card">
          <div class="card-header">คำร้องขอใบแปลใบเทียบวุฒิการศึการศึกษา</div>
          <div class="card-body">
            <form class="form">
              <div class="form-group">
                <label for="write_no">เขียนที่:</label>
                <input class="form-control" type="text" v-model="formData.WriteNo" id="write_no1" />
              </div>
              <div class="form-group">
                <label for="date">วันที่:</label>
                <input class="form-control" type="date" v-model="formData.date" id="date" required />
              </div>
              <div class="form-group">
                <label for="name_lastname">ชื่อ-นามสกุล:</label>
                <input class="form-control" type="text" v-model="formData.name_lastname" id="name_lastname" required />
              </div>
              <div class="form-group">
                <label for="score">คะแนนที่สอบได้:</label>
                <input class="form-control" type="text" v-model="formData.score" id="score" required />
              </div>
              <div class="form-group">
                <label for="school">โรงเรียน:</label>
                <input class="form-control" type="text" v-model="formData.school" id="school" required />
              </div>
              <div class="form-group">
                <label for="date_end">เมื่อ:</label>
                <input class="form-control" type="date" v-model="formData.date_end" id="date_end" required />
              </div>
              <div class="form-group">
                <label for="home">ที่อยู่ปัจจุบัน:</label>
                <input class="form-control" type="text" v-model="formData.home" id="home" required />
              </div>
              <div class="form-group">
                <label for="tel">โทรศัพท์:</label>
                <input class="form-control" type="text" v-model="formData.tel" id="tel" required />
              </div>
              <button type="submit" class="btn btn-primary" @click.prevent="submitForm">
                Submit
              </button>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-8">
        <AccordionItems :formDataArray="formDataArray" />
      </div>
    </div>
  </div>
</template>


<script>
import AccordionItems from "./components/AccordionItems.vue";

export default {
  data() {
    return {
      formData: {
        WriteNo: null,
        date: "",
        name_lastname: "",
        score: "",
        school: "",
        date_end: "",
        home: "",
        tel: "",
      },
      formDataArray: [],
    };
  },
  components: {
    AccordionItems,
  },
  methods: {
    submitForm() {
      // Add the form data to the formDataArray
      this.formDataArray.push(this.formData);
      // Reset the formData object
      this.formData = {
        WriteNo: null,
        date: "",
        name_lastname: "",
        score: "",
        school: "",
        date_end: "",
        home: "",
        tel: "",
      };
    },
  },
};
</script>

<style scoped>
.form {
  padding: 20px;
  margin: 0 auto;
}

/* Make the input fields larger */
.form-control-lg {
  height: 50px;
  font-size: 1.5rem;
}

/* Center the submit button */
.btn-primary {
  display: block;
  margin: 20px auto;
  text-align: center;
}

/* Add some hover effect to the submit button */
.btn-primary:hover {
  background-color: #3a45dd;
  color: #fff;
  cursor: pointer;
}

/* Add some border-radius to the card */
.card {
  border-radius: 10px;
}

/* Add some styles to the card-header */
.card-header {
  background-color: #007bff;
  color: #fff;
  font-size: 1.5rem;
  text-align: center;
  padding: 20px;
  border-radius: 10px 10px 0 0;
}
</style>