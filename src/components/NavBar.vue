<template>
  <header class="navbar row">
    <b-navbar toggleable="md" variant="white" class="">
      <b-navbar-brand href="#" class="">
        <img src="https://via.placeholder.com/70" alt="" />
      </b-navbar-brand>

      <b-navbar-toggle target="nav_collapse" class=""></b-navbar-toggle>

      <b-collapse is-nav id="nav_collapse">
        <b-navbar-nav class="">
          <b-nav-item href="#">الصفحة الرئيسية</b-nav-item>
          <b-nav-item href="#">منتجاتنا</b-nav-item>
          <b-nav-item href="#">مقياس الاستدامة المالية</b-nav-item>
          <b-nav-item href="#">حول المقياس</b-nav-item>
          <b-nav-item href="#">من نحن</b-nav-item>
          <b-nav-item href="#">تواصل معنا</b-nav-item>
          <b-nav-item href="#">الأسئلة الشائعة</b-nav-item>
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
header {
  padding: 0;
  margin: 0;
  > * {
    padding: 0;
    margin: 0;
  }
  .burger-icon {
    display: none;
  }
  ul {
    list-style: none;
    font-size: 0.9em;
    * {
      &:hover {
        color: #000 !important;
        cursor: pointer;
      }
    }
  }
}


@media (max-width: 768px) {
  .navbar-nav {
    padding-right: 20px;
  }
}
</style>