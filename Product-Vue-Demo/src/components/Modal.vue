<template>
  <div class="modal-backdrop">
    <div class="modal">
      <header class="modal-header">
        <slot name="header"> Product information </slot>
      </header>

      <div class="grid">
        <div class="field-box">
          <div class="row item-space-between">
            <label for="title">Title</label
            ><input
              id="title"
              type="text"
              class="textbox"
              placeholder="Title"
              v-model="Title"
            /><!---->
          </div>
          <div class="row item-space-between">
            <label for="tag">Tag</label
            ><input
              id="tag"
              type="text"
              class="textbox"
              placeholder="Tag"
              v-model="Tag"
            /><!---->
          </div>
          <div class="row item-space-between">
            <label for="link">Link</label
            ><input
              id="link"
              type="text"
              class="textbox"
              placeholder="Link"
              v-model="Link"
            /><!---->
          </div>
          <div class="row item-space-between">
            <label for="description">Description</label
            ><!----><textarea
              id="description"
              class="textbox"
              rows="7"
              placeholder="Add your note to your product"
              v-model="Description"
            ></textarea>
          </div>
        </div>
        <div class="row button-row">
          <a
            id="btn-close-modal"
            @click="close"
            href="javascript:void(0)"
            class="btn btn-light"
            >Close</a
          ><a
            id="btn-close-modal"
            href="javascript:void(0)"
            class="btn btn-primary"
            @click="addProductToList()"
            >Add</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      product: {
        title: "",
        description: "",
        tag: "",
        link: "",
      },
    };
  },
  methods: {
    close() {
      this.$emit("close");
    },
    addProduct() {
    },
    addProductToList() {
      let product = this.product;
      let listTags = this.product.tag.split(/\s*, \s*/);
      if (listTags.length > 0) {
        product.tags = listTags.filter((item) => item != null && item != "");
      } else {
        product.tags = [];
      }

    },
  },
};
</script>

<style scoped>
/* Rectangle 12 */
.modal-backdrop {
  position: fixed;
  top: 0px;
  left: 0px;
  width: 1440px;
  height: 900px;
  /* border-radius: 0px; */
  background: #21262e66;
}

.modal {
  position: absolute;
  top: 225px;
  left: 509px;
  width: 600px;
  height: 500px;
  background: #ffffffff;
  border-radius: 6px;
  box-shadow: 0px 2px 11px #333a47, 0px 0px 2px #333a47;
  padding: 35px;
}

.modal-header {
  position: absolute;
  /* top: 25px; */
  left: 28px;
  width: 512px;
  font-family: Inter;
  font-size: 32px;
  line-height: 48px;
  color: #21262eff;
  margin-left: 10px;
  font-weight: bold;
  margin-bottom: 30px;
}

.grid {
  display: grid;
  height: 95%;
  align-content: space-between;
  margin-top: 10%;
}
.row {
  display: flex;
  margin: 20px 0px;
  width: 100%;
}
.row label {
  /* font-family: Josefin Sans; */
  font-size: 14px;
  line-height: 22px;
  color: #21262eff;
}
.row .textbox {
  width: 424px;
  padding: 9px 14px;
  font-family: Josefin Sans;
  font-size: 14px;
  background: #ffffffff;
  border-radius: 6px;
  /* border-width: 1px;
         border-color: #bbc0c9ff; */
  border: none;
  outline: 1px solid #bbc0c9ff;
}

.row .textbox input:hover {
  color: #bbc0c9;
  background: #ffffffff;
  border-color: #56b4b8ff;
}
/* focused */
.row .textbox input:focused {
  color: #bbc0c9;
  background: #ffffffff;
  border-color: #56b4b8ff;
}
/* disabled */
.row .textbox input:disabled {
  color: #bbc0c9;
  background: #ffffffff;
  border-color: #bbc0c9ff;
}
.row .textbox :disabled + .icon,
.row .textbox :disabled + .icon + .icon {
  fill: #21262e;
}
.item-space-between {
  justify-content: space-between;
}
.button-row {
  justify-content: center;
}

.btn {
  padding: 10px 30px !important;
  margin: 0px 50px;
  border: none;
  border-radius: 6px;
  text-decoration: none;
}
.btn-primary {
  color: #fff;
  background: #56b4b8;
}
.btn-primary {
  color: #fff;
  background: #56b4b8;
}
.btn-light {
  color: #5a6372;
  background: #f3f4f6;
}
</style>