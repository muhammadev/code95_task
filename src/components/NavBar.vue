<template>
  <header>
    <b-navbar toggleable="lg">
      <b-navbar-brand href="#"
        ><img src="@/assets/logo-removebg-preview.png" alt=""
      /></b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="mx-lg-2 mx-xl-5">
          <b-nav-item href="#">الصفحة الرئيسية</b-nav-item>
          <b-nav-item href="#">منتجاتنا</b-nav-item>
          <b-nav-item href="#">مقياس الاستدامة المالية</b-nav-item>
          <b-nav-item href="#">حول المقياس</b-nav-item>
          <b-nav-item href="#">من نحن</b-nav-item>
          <b-nav-item href="#">تواصل معنا</b-nav-item>
          <b-nav-item href="#">الأسئلة الشائعة</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="side-nav-btns">
          <button class="search-icon"><b-icon-search></b-icon-search></button>
          <button class="side-logo">
            <img src="@/assets/logo-removebg-preview.png" alt="" />
          </button>
          <button class="register-btn">تسجيل الدخول</button>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <!-- <b-navbar toggleable="xl" variant="white" class="">
      <b-navbar-brand href="#" class="">
        <img src="@/assets/logo-removebg-preview.png" alt="" />
      </b-navbar-brand>

      <b-navbar-toggle target="nav_collapse" class=""></b-navbar-toggle>

      <b-collapse is-nav id="nav_collapse" class="row">
        <b-navbar-nav class="col-xl-8 mx-lg-3 mx-xl-5">
          <b-nav-item href="#">الصفحة الرئيسية</b-nav-item>
          <b-nav-item href="#">منتجاتنا</b-nav-item>
          <b-nav-item href="#">مقياس الاستدامة المالية</b-nav-item>
          <b-nav-item href="#">حول المقياس</b-nav-item>
          <b-nav-item href="#">من نحن</b-nav-item>
          <b-nav-item href="#">تواصل معنا</b-nav-item>
          <b-nav-item href="#">الأسئلة الشائعة</b-nav-item>
        </b-navbar-nav>
        <div class="col-xl-4 bg-primary">hello</div>
      </b-collapse>
    </b-navbar> -->
  </header>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style lang="scss">
.navbar {
  padding-top: 0 !important;
  padding-bottom: 0 !important;
  border-bottom: 1px solid #ced4da;
  .navbar-collapse {
    justify-content: space-between;
    min-height: 80px;
    font-size: 16px;
    > * {
      height: 100%;
      align-items: center;
    }
    .side-nav-btns {
      button {
        height: 100%;
        padding: 0 25px;
        background: transparent !important;
        border: none;
        outline: none;
        border-right: 1px solid #ced4da;
        &.search-icon {
          color: #666 !important;
        }
        &.side-logo {
          padding: 0 10px !important;
        }
        &.register-btn {
          color: #fff !important;
          background: #65bde1 !important;
        }
      }
    }
  }
}
// up to 991 && starting from 992
@media screen and (max-width: 991px) {
  .navbar-toggler {
    margin-left: 10px;
  }

  .navbar-collapse {
    ul {
      font-size: 16px !important;
    }
    .side-nav-btns {
      display: none !important;
    }
  }
}

@media screen and (min-width: 992px) {
  .navbar-collapse {
    > * {
      height: 80px !important;
    }
    ul {
      font-size: 12px !important;
    }
  }
}

@media screen and (min-width: 1200px) {
  .navbar-collapse {
    ul {
      font-size: 16px !important;
    }
  }
}
</style>