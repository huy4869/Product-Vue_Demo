<template>
  <div class="top-container">
    <div class="top">
      <div class="logo" />

      <div class="header-menu">
        <div class="header-menu-item selected">Home</div>
        <div class="header-menu-item">Explanations</div>
        <div class="header-menu-item">
          Library
          <svg class="arrow-icon"></svg>
        </div>

        <div class="header-menu-item" @click="showModal">
          Create
          <svg class="arrow-icon"></svg>
        </div>
        <Modal v-show="isModalVisible" @close="closeModal" />
        
      </div>
      <div class="textbox">
        <svg class="left"></svg>
        <input type="text" />
      </div>
      <div class="icon-noti"></div>
      <div class="avatar">
        <img />
        <div class="badge"></div>
      </div>
      <div class="text">HELO ae</div>
      <div class="icon-down"></div>
    </div>
  </div>
</template>

<script>
import Modal from "./Modal.vue";
export default {
  components: { Modal },
  data() {
    return {
      isModalVisible: false,
    }
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    }
  },
};
</script>

<style  scoped>
.logo {
  background-image: url("~@/assets/logo.png");
  /* background-repeat: no-repeat; */
  position: absolute;
  top: 8px;
  left: 24px;
  width: 96px;
  height: 40px;
  border-radius: 4px;
  background-size: cover;
  background-position: 0 -30px;
  cursor: pointer;
}

/* header */
.top {
  position: absolute;
  top: -2px;
  left: 0px;
  width: 1440px;
  height: 64px;
  background: #ffffffff;
  border-radius: 0px;
  box-shadow: 0px 0px 7px #333a47, 0px 0px 2px #333a47;
}
/* Header menu 1 */
.header-menu {
  position: absolute;
  top: 4px;
  left: 160px;
  width: 431px;
  height: 54px;
  display: flex;
  align-items: center;
  font-family: Epilogue;
  font-size: 16px;
  line-height: 26px;
  opacity: 1;
}
/* Header menu 1 - Arrow icon */

.header-menu svg.arrow-icon {
  background-image: url("~@/assets/arrow-icon-4.svg");
  width: 24px;
  height: 24px;
  margin-left: 14px;
  fill: currentColor;
}
/* Header menu 1 - Item */
.header-menu .header-menu-item {
  padding: 17px 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #5a6372ff;
  background: transparent;
  border-radius: 0px;
  cursor: pointer;
  white-space: nowrap;
}
/* Header menu 1 - Hovered item */
.header-menu .header-menu-item:hover {
  color: #8f95a0ff;
  background: #dee1e6ff;
}
/* Header menu 1 - Pressed item */
.header-menu .header-menu-item:hover:active {
  color: #8f95a0ff;
  background: #bbc0c9ff;
}
/* Header menu 1 - Selected item */
.header-menu .header-menu-item.selected {
  position: relative;
  font-weight: bold;
  color: #9b7d4bff;
  background: #f4efe8ff;
}
/* Header menu 1 - Selected item */
.header-menu .header-menu-item.selected:hover:active {
  color: #9b7d4bff;
  background: #f4efe8ff;
}

/* Textbox 1 */
.textbox {
  position: absolute;
  top: 12px;
  left: 880px;
  opacity: 1;
}
.textbox input {
  width: 288px;
  height: 40px;
  padding-left: 42px;
  padding-right: 14px;
  font-family: Epilogue;
  font-size: 16px;
  background: #f9f9faff;
  border-radius: 4px;
  border-width: 0px;
  outline: none;
}
.textbox svg {
  position: absolute;
  top: 10px;
  right: 14px;
  width: 20px;
  height: 20px;
  fill: #21262e;
}
.textbox svg.left {
  background-image: url("~@/assets/left-icon.svg");
  cursor: pointer;

  left: 14px;
}
/* hover */
.textbox input:hover {
  color: #bbc0c9;
  background: #f9f9faff;
}
/* focused */
.textbox input:focused {
  color: #bbc0c9;
  background: #ffffffff;
}
/* disabled */
.textbox input:disabled {
  color: #bbc0c9;
  background: #f9f9faff;
}
.textbox :disabled + .icon,
.textbox :disabled + .icon + .icon {
  fill: #21262e;
}

/* Notifications 1 */
.icon-noti {
  background-image: url(~@/assets/notifications.svg);
  position: absolute;
  top: 18px;
  left: 1186px;
  width: 28px;
  height: 28px;
  fill: #8e949f;
  opacity: 1;
  cursor: pointer;
}

/* Avatar 1 */
.avatar {
  position: absolute;
  top: 12px;
  left: 1232px;
  width: 40px;
  height: 40px;
  background: #ffffffff;
  opacity: 1;
  overflow: hidden;
  border-radius: 20px;
  cursor: pointer;
}
.avatar img {
  background-image: url(~@/assets/I.jpg);
  background-repeat: no-repeat;
  background-position: center;
  width: 40px;
  height: 40px;
}
.avatar .badge {
  width: 10px;
  height: 10px;
  border-radius: 5px;
}
.avatar.active .badge {
  background: #6eed98;
  border-width: 1.5px;
  border-color: #ffffff;
}
.avatar.inactive .badge {
  background: #dee1e6;
  border-width: 1.5px;
  border-color: #ffffff;
}
.avatar.idle .badge {
  background: #f6e07e;
  border-width: 1.5px;
  border-color: #ffffff;
}
.avatar.do_not_disturb .badge {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 10px;
  line-height: 10px;
  color: #ffffff;
  background: #f27d81;
  border-width: 1.5px;
  border-color: #ffffff;
}

/* Text 5 */
.text {
  position: absolute;
  top: 19px;
  left: 1280px;
  font-family: Epilogue;
  font-size: 16px;
  line-height: 26px;
  color: #21262eff;
  cursor: pointer;
}

/* Chevron down large 1 */
.icon-down {
  background-image: url(~@/assets/chevron_down_large.svg);

  position: absolute;
  top: 19px;
  left: 1350px;
  width: 22px;
  height: 22px;
  fill: #8e949f;
  opacity: 1;
  cursor: pointer;
}
</style>