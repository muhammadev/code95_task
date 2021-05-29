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
          <div class="col-md-4 custom-multiselect-wrapper">
            <div class="input-group custom-multiselect">
              <multiselect
                v-model="first_selected_code"
                label="code"
                track-by="code"
                placeholder="اختر كود الدولة"
                :options="options"
                :show-labels="false"
              >
                <template slot="singleLabel" slot-scope="props"
                  ><span class="option__title">{{ props.option.code }}</span
                  >&nbsp;<img
                    class="option__image"
                    :src="props.option.flag"
                    alt="country's flag"
                /></template>
                <template slot="option" slot-scope="props">
                  <div class="option__desc">
                    <span class="option__title">{{ props.option.code }}</span>
                  </div>
                  &nbsp;
                  <img
                    class="option__image"
                    :src="props.option.flag"
                    alt="country's flag"
                  />
                </template>
              </multiselect>
            </div>
          </div>
          <div class="col-md-8">
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
          <div class="col-md-4 custom-multiselect-wrapper">
            <div class="input-group custom-multiselect">
              <multiselect
                v-model="second_selected_code"
                label="code"
                track-by="code"
                placeholder="اختر كود الدولة"
                :options="options"
                :show-labels="false"
              >
                <template slot="singleLabel" slot-scope="props"
                  ><span class="option__title">{{ props.option.code }}</span
                  >&nbsp;<img
                    class="option__image"
                    :src="props.option.flag"
                    alt="country's flag"
                /></template>
                <template slot="option" slot-scope="props">
                  <div class="option__desc">
                    <span class="option__title">{{ props.option.code }}</span>
                  </div>
                  &nbsp;
                  <img
                    class="option__image"
                    :src="props.option.flag"
                    alt="country's flag"
                  />
                </template>
              </multiselect>
            </div>
          </div>
          <div class="col-md-8">
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
      first_selected_code: {
        code: "+20",
        flag: "https://restcountries.eu/data/egy.svg",
      },
      second_selected_code: {
        code: "+20",
        flag: "https://restcountries.eu/data/egy.svg",
      },
      options: [
        { code: "+20", flag: "https://restcountries.eu/data/egy.svg" },
        { code: "+966", flag: "https://restcountries.eu/data/sau.svg" },
        { code: "+974", flag: "https://restcountries.eu/data/qat.svg" },
        { code: "+973", flag: "https://restcountries.eu/data/bhr.svg" },
        { code: "+965", flag: "https://restcountries.eu/data/kwt.svg" },
        { code: "+212", flag: "https://restcountries.eu/data/mar.svg" },
        { code: "+249", flag: "https://restcountries.eu/data/sdn.svg" },
      ],
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

.input-group.custom-multiselect {
  width: 100%;
  height: 100%;
}

.multiselect {
  width: 100%;
  height: 100%;
  line-height: 2;
  text-align: center;
  padding: 0 5px;
  border: 1px solid #ced4da;
  border-radius: 0.25rem;
  .multiselect__input {
    outline: none;
    border: none;
  }

  .multiselect__single {
    cursor: pointer;
    .option__image {
      width: 20px;
      object-fit: contain;
    }
  }

  .multiselect__content-wrapper {
    position: relative !important;
    // width: 100px;
    ul.multiselect__content {
      position: absolute !important;
      left: 5%;
      width: 100%;
      max-width: 200px;
      max-height: 250px;
      overflow: auto;
      padding: 0;
      z-index: 1000 !important;
      background: #fff !important;
      box-shadow: 1px 1px 5px 1px #ced4da;
      border: 1px solid #ced4da;
      border-radius: 5px;
      list-style: none !important;
      li {
        list-style: none !important;
        margin: 10px 0;
        span {
          display: inline-block;
          width: 100% !important;
          border-radius: 0.25rem;
          text-align: center;
          cursor: pointer;
          &.multiselect__option--selected {
            background: #ced4da;
          }
          &.multiselect__option--highlight {
            background: #65bde1 !important;
            color: #fff !important;
          }
          &.multiselect__option--selected.multiselect__option--highlight {
            background: #e86975 !important;
            color: #fff !important;
          }

          .option__image {
            width: 20px;
            object-fit: contain;
          }

          .option__desc {
            display: inline-block;
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