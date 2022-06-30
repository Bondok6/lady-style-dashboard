<template>
  <div>
    <div :class="{ sidebar: true, activeMenu: menu }">
      <!-- <img
        src="@/assets/images/icons/logout.svg"
        alt="menu-icon"
        class="menu-icon"
        @click="active"
      /> -->

      <section class="sidebar__list-items">
        <nuxt-link
          exact-active-class="active-sideitem"
          class="sidebar-item"
          tag="div"
          :to="'/'"
        >
          <img
            class="sidebar-item__icon"
            src="@/assets/images/icons/sidebar/chart.svg"
            alt="chart-icon"
          />
          <h6 class="sidebar-item__label">الإحصائيات</h6>
        </nuxt-link>

        <nuxt-link
          exact-active-class="active-sideitem"
          class="sidebar-item"
          tag="div"
          :to="'/orders'"
        >
          <img
            class="sidebar-item__icon"
            src="@/assets/images/icons/sidebar/orders.svg"
            alt="orders-icon"
          />
          <h6 class="sidebar-item__label">الحجوزات</h6>
        </nuxt-link>

        <nuxt-link
          exact-active-class="active-sideitem"
          tag="div"
          class="sidebar-item"
          :to="'/add-order'"
        >
          <img
            class="sidebar-item__icon"
            src="@/assets/images/icons/sidebar/add.svg"
            alt="add-icon"
          />
          <h6 class="sidebar-item__label">اضافة حجز جديد</h6>
        </nuxt-link>

        <nuxt-link
          exact-active-class="active-sideitem"
          tag="div"
          class="sidebar-item"
          :to="'/employees'"
        >
          <img
            class="sidebar-item__icon"
            src="@/assets/images/icons/sidebar/person.svg"
            alt="person-icon"
          />
          <h6 class="sidebar-item__label">العاملات</h6>
        </nuxt-link>

        <nuxt-link
          exact-active-class="active-sideitem"
          tag="div"
          class="sidebar-item"
          :to="'/customers'"
        >
          <img
            class="sidebar-item__icon"
            src="@/assets/images/icons/sidebar/customers.svg"
            alt="customers-icon"
          />
          <h6 class="sidebar-item__label">قائمة العملاء</h6>
        </nuxt-link>

        <nuxt-link
          exact-active-class="active-sideitem"
          tag="div"
          class="sidebar-item"
          :to="'/credits'"
        >
          <img
            class="sidebar-item__icon"
            src="@/assets/images/icons/sidebar/mark.svg"
            alt="mark-icon"
          />
          <h6 class="sidebar-item__label">اعتمادات</h6>
        </nuxt-link>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: false,
    };
  },
  mounted() {
    const navLinks = document.querySelectorAll(".sidebar-item");
    navLinks.forEach((link) => {
      link.addEventListener("click", this.active);
    });
  },
  methods: {
    active() {
      this.menu = !this.menu;
    },
  },
};
</script>

<style></style>
