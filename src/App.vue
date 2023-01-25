<template>
  <div class="container">
    <div class="row mt-5">
      <div class="col-md-4">
        <div class="card">
          <div class="card-header">เขียนคำร้องทั่วไป</div>
          <div class="card-body">
            <form class="form">
              <div class="form-group">
                <label for="date">วันที่ :</label>
                <input
                  class="form-control"
                  type="date"
                  v-model="formData.date"
                  id="date"
                />
              </div>
              <div class="form-group">
                <label for="subject">วิชา :</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.subject"
                  id="subject"
                />
              </div>
              <div class="form-group">
                <label for="to">ถึง :</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.to"
                  id="to"
                />
              </div>

              <div class="form-group">
                <label for="name">ชื่อ-สกุลนักศึกษา :</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.name"
                  id="name"
                />
              </div>
              <div class="form-group">
                <label for="studentID">รหัสนักศึกษา :</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.studentID"
                  id="studentID"
                />
              </div>

              <div class="form-group">
                <label for="major">สาขา :</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.major"
                  id="major"
                />
              </div>
              <div class="form-group">
                <label for="faculty">คณะ :</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.faculty"
                  id="faculty"
                />
              </div>
              <div class="form-group">
                <label for="telephone">เบอร์โทรศัพท์ :</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.telephone"
                  id="telephone"
                  maxlength="10"
                />
              </div>
              <div class="form-group">
                <label for="email">อีเมล :</label>
                <input
                  class="form-control"
                  type="email"
                  v-model="formData.email"
                  id="email"
                />
              </div>

              <div class="form-group">
                <label for="reason">เหตุผล :</label>
                <textarea
                  class="form-control"
                  v-model="formData.reason"
                  id="reason"
                ></textarea>
              </div>

              <button
                type="submit"
                class="btn btn-primary"
                @click.prevent="submitForm"
              >
                คลิ๊ก ! เพื่อส่งฟอร์ม
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
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
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
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
      };
    },
  },
};
</script>
