<template>
  <div class="container text-center">
    <form action="" class="px-5 m-5 mb-0">
      <h5 class="form_title mb-5">بيانات المسؤولين</h5>
      <div class="row text-end">
        <div class="col-md">
          <label for=""
            >اسم المسؤول <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label for=""
            >منصبه <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md-6 row p-0 m-0">
          <label for="">رقم الجوال</label>
          <div class="col-md-2">
            <div class="input-group custom-multiselect">
              <multiselect
                v-model="first_selected_code"
                :options="options"
                :searchable="false"
              ></multiselect>
            </div>
          </div>
          <div class="col-md-10">
            <div class="input-group">
              <b-form-input type="tel"></b-form-input>
            </div>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md">
          <label for=""
            >اسم المفوض بالتواصل <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label for=""
            >منصبه <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-input></b-form-input>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md-6 row p-0 m-0">
          <label for="">رقم الجوال</label>
          <div class="col-2">
            <div class="input-group custom-multiselect">
              <multiselect
                v-model="second_selected_code"
                :options="options"
                :searchable="false"
              ></multiselect>
            </div>
          </div>
          <div class="col-md-10">
            <div class="input-group">
              <b-form-input type="tel"></b-form-input>
            </div>
          </div>
        </div>

        <div class="col-md-6">
          <label for=""
            >البريد الإلكتروني <b-icon-dot class="text-danger"></b-icon-dot
          ></label>
          <div class="input-group">
            <b-form-input type="email"></b-form-input>
          </div>
        </div>
      </div>

      <div class="row text-end">
        <div class="col-md">
          <label for="">ملاحظات</label>
          <div class="input-group">
            <b-form-textarea></b-form-textarea>
          </div>
        </div>
      </div>

      <button class="next-btn btn my-3">طلب المنتج</button>
    </form>
    <div class="carousel mb-5">
      <div class="dot" v-on:click="switchStep(0)"></div>
      <div class="dot current" v-on:click="switchStep(1)"></div>
    </div>
  </div>
</template>

<script>
import Multiselect from "vue-multiselect";

export default {
  name: "StepTwo",
  components: {
    Multiselect,
  },
  data() {
    return {
      first_selected_code: "93",
      second_selected_code: "213",
      options: ["93", "358", "355", "213", "1684", "376", "244"],
    };
  },
  methods: {
    switchStep: function (step) {
      this.$emit("step", step);
    },
    customLabel({ code }) {
      return `${code}`;
    },
  },
};
</script>

<style lang="scss">
.form_title {
  color: #65bde1;
}

label {
  color: #666;
  margin-bottom: 10px;
}

li {
  list-style: none !important;
}

.next-btn {
  display: inline-block !important;
  width: 70%;
  background: #65bde1 !important;
  color: #fff !important;
}

.multiselect {
  padding: 0 10px;
  border: 1px solid #ced4da;
  border-radius: 0.25rem;
  cursor: pointer;

  .multiselect__content-wrapper {
    position: relative !important;

    ul.multiselect__content {
      position: absolute !important;
      z-index: 1000 !important;
      background: #fff !important;
      box-shadow: 1px 1px 5px 1px #ced4da;
      border: 1px solid #ced4da;
      list-style: none !important;
      padding: 0 10px;

      li:hover {
        background: #e7e7e7;
        border-radius: 0.25rem;
        text-align: center;
      }
    }
  }
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