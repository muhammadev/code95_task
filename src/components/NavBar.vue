<template>
  <header>
    <b-navbar toggleable="lg" class="p-0">
      <b-navbar-brand href="#"
        ><img src="@/assets/logo.png" alt="logo"
      /></b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- right nav links -->
        <b-navbar-nav class="mx-lg-2 mx-xl-5">
          <b-nav-item href="#">الصفحة الرئيسية</b-nav-item>
          <b-nav-item href="#">منتجاتنا</b-nav-item>
          <b-nav-item href="#">مقياس الاستدامة المالية</b-nav-item>
          <b-nav-item href="#">حول المقياس</b-nav-item>
          <b-nav-item href="#">من نحن</b-nav-item>
          <b-nav-item href="#">تواصل معنا</b-nav-item>
          <b-nav-item href="#">الأسئلة الشائعة</b-nav-item>
        </b-navbar-nav>

        <!-- left nav buttons -->
        <b-navbar-nav class="side-nav-btns">
          <button class="search-icon"><b-icon-search></b-icon-search></button>
          <button class="side-logo">
            <img src="@/assets/side_logo.png" alt="side logo" />
          </button>
          <button class="register-btn">تسجيل الدخول</button>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
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
          color: #818181 !important;
          &:hover {
            background: #ddd !important;
          }
        }
        &.side-logo {
          padding: 0 10px !important;
        }
        &.register-btn {
          color: #fff !important;
          background: #65bde1 !important;
          &:hover {
            background: #3eadda !important;
          }
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
      button {
        border-right: none !important;
        margin: 10px 0;
        &.register-btn {
          padding: 10px;
        }
      }
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