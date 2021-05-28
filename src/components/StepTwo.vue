<template>
  <div class="container text-center">
    <form action="" class="px-5 mt-5 mx-md-5">
      <h5 class="form_title mb-5">بيانات المسؤولين</h5>
      <div class="row text-end">
        <div class="col-md">
          <label class="form_label" for="person_name"
            >اسم المسؤول <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-input id="person_name" required></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label class="form_label" for="person_position"
            >منصبه <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-input id="person_position" required></b-form-input>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md-6 row p-0 m-0">
          <label class="form_label" for="tel_number">رقم الجوال</label>
          <div class="col-md-auto">
            <div class="input-group custom-multiselect">
              <multiselect
                v-model="first_selected_code"
                :options="options"
                :searchable="false"
              ></multiselect>
            </div>
          </div>
          <div class="col-md">
            <div class="input-group">
              <b-form-input id="tel_number" type="tel"></b-form-input>
            </div>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md">
          <label class="form_label" for="comunicator_name"
            >اسم المفوض بالتواصل <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-input id="comunicator_name" required></b-form-input>
          </div>
        </div>

        <div class="col-md">
          <label class="form_label" for="comunicator_position"
            >منصبه <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-input id="comunicator_position" required></b-form-input>
          </div>
        </div>
      </div>

      <div class="row my-5 text-end">
        <div class="col-md-6 row p-0 m-0">
          <label class="form_label" for="comunicator_tel_number"
            >رقم الجوال</label
          >
          <div class="col-md-auto">
            <div class="input-group custom-multiselect">
              <multiselect
                v-model="second_selected_code"
                :options="options"
                :searchable="false"
              ></multiselect>
            </div>
          </div>
          <div class="col-md">
            <div class="input-group">
              <b-form-input
                id="comunicator_tel_number"
                type="tel"
              ></b-form-input>
            </div>
          </div>
        </div>

        <div class="col-md-6">
          <label class="form_label" for="email"
            >البريد الإلكتروني <span class="text-danger">&ast;</span></label
          >
          <div class="input-group">
            <b-form-input id="email" type="email" required></b-form-input>
          </div>
        </div>
      </div>

      <div class="row text-end">
        <div class="col-md">
          <label class="form_label" for="notes">ملاحظات</label>
          <div class="input-group">
            <b-form-textarea id="notes"></b-form-textarea>
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
      first_selected_code: "+93",
      second_selected_code: "+213",
      options: ["+93", "+358", "+355", "+213", "+376", "+244"],
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

// scoped styling not used for styling elements created on render
<style lang="scss">
.form_title {
  color: #65bde1;
}

label.form_label {
  color: #666;
  margin-bottom: 10px;
}

.next-btn {
  display: inline-block !important;
  width: 70%;
  background: #65bde1 !important;
  color: #fff !important;
}

.multiselect {
  padding: 0 5px;
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
      padding: 5px 10px;

      li {
        list-style: none !important;

        span {
          padding: 2px;
          margin: 2px;
          border-radius: 0.25rem;
          text-align: center;
          transition: 0.1s;
          &:hover {
            background: #e7e7e7;
          }
        }
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