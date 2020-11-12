<template>
  <ul v-if="totalPages" class="paginator">
    <li
      v-for="page in totalPages"
      :key="page"
      :class="{ 'paginator__item--active': currentPage === page }"
    >
      <a href="#" :title="`Página ${page}`" @click.prevent="handlePagination(page)">{{ page }}</a>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Paginator',
  props: {
    totalPages: {
      type: Number,
      default: 0
    },

    currentPage: {
      type: Number,
      default: 1
    }
  },
  methods: {
    handlePagination (page) {
      this.$emit('update', page)
    }
  }
}
</script>

<style>
.paginator {
  list-style-type: none;
  padding: 0;
  text-align: center;
}

.paginator li {
  display: inline-block;
  margin: 0 4px;
}

.paginator li a {
  align-items: center;
  border: 1px solid #3fba84;
  border-radius: 4px;
  display: flex;
  height: 30px;
  justify-content: center;
  text-decoration: none;
  width: 30px;
}

.paginator > li.paginator__item--active > a {
  background: #3fba84;
  color: #fff;
  cursor: pointer;
}
</style>
