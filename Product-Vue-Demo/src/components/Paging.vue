<template>
  <div id="paging">
    va day la {{pageSize}}
    <a v-if="currentPage > 1" href="javascript:void(0)" @click="changePage(-1)"
      >Previous</a
    >
    <div class="page">
      <span>{{`${currentPage} Of ${pageNumber}`}}</span>
    </div>
    <a
      v-if="currentPage < pageNumber"
      href="javascript:void(0)"
      @click="changePage(1)"
      >Next</a
    >
  </div>
</template>

<script>
export default {

  props: {
    productne: Array,
    pageSize: Number,
    currentPage: Number,
  },
  methods: {
    changePage(number) {
      // this.currentPage += number;
      this.$emit("current_Page", (this.currentPage+= number));
    },
  },
  computed: {
    pageNumber() {
      if (this.productne.length % this.pageSize == 0) {
        return this.productne / this.pageSize;
      } else {
        return Math.floor(this.productne.length / this.pageSize) + 1;
      }
    },

  },
};
</script>

<style scoped>
#paging a:hover {
  color: #5a6372;
  background: #ced2d9;
}
/* Pressed */
#paging a:hover:active {
  color: #5a6372;
  background: #bbc0c9;
}
/* Disabled */
#paging a:disabled {
  opacity: 0.4;
}
#paging .page {
  font-family: Josefin Sans;
  font-size: 14px;
  line-height: 22px;
  color: #8e949f;
  margin: 0px 20px 0px 20px;
}
#paging {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 30px;

  /* Hover */
}

#paging .a {
  width: 80px;
  height: 36px;
  padding: 0 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: Josefin Sans;
  font-size: 14px;
  line-height: 22px;
  color: #5a6372;
  background: #eaecf0;
  border: none;
  border-radius: 6px;
  text-decoration: none;
}
</style>




