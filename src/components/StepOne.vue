<template>
  <div class="container text-center mt-5">
    <h1 class="text-dark">نموذج طلب المنتج "هندسة الموسم"</h1>
    <form action="#" class="step_one_form px-5 mt-5 mx-md-5">
      <h5 class="form_title mb-5">بيانات المنظمة</h5>
      <div class="row text-end">
        <div class="col-md">
          <label class="form_label" for="organization_name"
            >اسم المنظمة <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-input id="organization_name" required></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label class="form_label" for="organization_work"
            >نشاط المنظمة <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-input id="organization_work" required></b-form-input>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md">
          <label class="form_label" for="region">المنطقة</label>
          <div class="input-group">
            <b-form-input id="region"></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label class="form_label" for="state">المركز/المحافظة</label>
          <div class="input-group">
            <b-form-input id="state"></b-form-input>
          </div>
        </div>
      </div>
      <h5 class="form_title">الباقة المطلوبة</h5>
      <div class="row text-end">
        <div class="col-md-6">
          <label class="form_label" for="quota"
            >اختر الباقة <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-select
              id="quota"
              class="custom-select"
              :options="options"
              required
            ></b-form-select>
          </div>
        </div>
      </div>
      <button type="submit" class="next-btn btn my-3" v-on:click="next">
        التالي
      </button>
    </form>
    <div class="carousel mb-5">
      <div class="dot current" v-on:click="switchStep(0)"></div>
      <div class="dot" v-on:click="switchStep(1)"></div>
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
      // for "next" button, switches to the next step
      e.preventDefault();
      this.checkRequiredFields(1);
    },

    switchStep: function (step) {
      // for carousel, switches to the given step variable
      this.checkRequiredFields(step);
    },

    checkRequiredFields: function (step) {
      let allInputs = Array.prototype.slice.call(
        document.querySelectorAll("input[required]")
      );
      allInputs.push(document.querySelector("select[required]"));


      let breakLoop = false;
      allInputs.forEach((npt, i) => {
        // if no empty fields found yet
        if (!breakLoop) {
          // if not falsy
          if (npt.value) {
            // submit if last element to check, else.. continue the loop
            if (i === allInputs.length-1) {
              this.$emit('step', step)
            }
          } else {
            breakLoop = true;
            npt.focus();
          }
        }
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.form_title {
  color: #65bde1;
}

label {
  color: #666;
  margin-bottom: 10px;
}

.custom-select {
  width: 100%;
  background: #fff;
  padding: 7px;
  border: 1px solid #ced4da;
  border-radius: 0.25rem;
}

.next-btn {
  display: inline-block !important;
  width: 70%;
  background: #65bde1;
  color: #fff;
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
      background: #65bde1 !important;
    }
  }
}
</style>