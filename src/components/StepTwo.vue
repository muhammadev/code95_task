<template>
  <div class="container text-center">
    <form action="" class="px-5 m-5">
      <h5 class="mb-5 text-primary">بيانات المسؤولين</h5>
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

      <button class="next-btn btn btn-primary my-5">طلب المنتج</button>
    </form>
    <div class="carousel mb-5">
      <div class="dot current" v-on:click="switchStep(1)"></div>
      <div class="dot" v-on:click="switchStep(0)"></div>
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
li {
  list-style: none !important;
}

.next-btn {
  display: inline-block !important;
  width: 70%;
}

.multiselect {
  padding: 0 10px;
  border: 1px solid #ced4da;
  border-radius: 0.25rem;
  cursor: pointer;
  ul.multiselect__content {
    list-style: none !important;
    padding: 0 10px;

    li:hover {
      background: #e7e7e7;
      border-radius: 0.25rem;
      text-align: center;
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
    background: #666;
    cursor: pointer;
    &.current {
      background: #0d6efd !important;
    }
  }
}
</style>