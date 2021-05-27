<template>
  <div class="container text-center mt-5">
    <h1>نموذج طلب المنتج "هندسة الموسم"</h1>
    <form action="#" class="px-5 mt-5 mx-md-5">
      <h5 class="mb-5 text-primary">بيانات المنظمة</h5>
      <div class="row text-end">
        <div class="col-md">
          <label for=""
            >اسم المنظمة <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label for=""
            >نشاط المنظمة <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md">
          <label for="">المنطقة</label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label for="">المركز/المحافظة</label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>
      </div>
      <h5 class="text-primary">الباقة المطلوبة</h5>
      <div class="row text-end">
        <div class="col-md-6">
          <label for=""
            >اختر الباقة <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-select
              class="custom-select"
              v-model="selected"
              :options="options"
            ></b-form-select>
          </div>
        </div>
      </div>
      <button class="next-btn btn btn-primary my-3" v-on:click="next">
        التالي
      </button>
    </form>
    <div class="carousel mb-5">
      <div class="dot" v-on:click="switchStep(1)"></div>
      <div class="dot current" v-on:click="switchStep(0)"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "StepOne",
  data() {
    return {
      options: [
        { value: "a", text: "باقة واحد" },
        { value: "b", text: "باقة اثنين" },
        { value: "c", text: "باقة ثلاثة" },
        { value: "d", text: "باقة أربعة" },
        { value: "e", text: "باقة خمسة" },
      ],
    };
  },
  methods: {
    next: function (e) {
      e.preventDefault();
      this.$emit("step", 1);
    },
    switchStep: function (step) {
      this.$emit("step", step);
    },
  },
};
</script>

<style lang="scss" scoped>
.custom-select{
  width: 100%;
  background: #fff;
  padding: 7px;
  border: 1px solid #ced4da;
  border-radius: 0.25rem;
}

.next-btn {
  display: inline-block !important;
  width: 70%;
}

.carousel {
  .dot {
    display: inline-block;
    width: 10px;
    height: 10px;
    margin: 0 3px;
    border-radius: 50%;
    background: #999;
    cursor: pointer;
    &.current {
      background: #0d6efd !important;
    }
  }
}
</style>