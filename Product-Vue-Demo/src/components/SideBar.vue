<template>
  <div class="side-bar-container">
    <div class="side-bar">
      <div class="back-button"></div>
      <span class="text-back">Back</span>
      <div class="icon-flash"></div>
      <span class="text-flash">Flashcashs</span>

      <div class="process-container">
        <div class="done"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "navigation-container",
};
</script>

<style  scoped>
/* side-bar */
.side-bar {
  position: absolute;
  top: 62px;
  left: 0px;
  width: 288px;
  height: 836px;
  background: #ffffffff;
  border-radius: 0px;
  box-shadow: 0px 0px 7px #333a47, 0px 0px 2px #333a47;
}
.back-button {
  background-image: url(~@/assets/arrow_back_ios.svg);
  background-repeat: no-repeat;
  background-size: 35%;
  position: absolute;
  top: 28px;
  left: 24px;
  width: 60px;
  height: 22px;
  cursor: pointer;
}
/* Text 7 */
.text-back {
  position: absolute;
  top: 25px;
  left: 45px;
  font-family: Epilogue;
  font-size: 18px;
  line-height: 28px;
  color: #21262eff;
  cursor: pointer;
}
/* Layers 1 */
.icon-flash {
  position: absolute;
  top: 106px;
  left: 24px;
  width: 28px;
  height: 28px;
  fill: #000000;
  opacity: 1;
  background-image: url(~@/assets/layers.svg);
  background-repeat: no-repeat;
}

/* Text 8 */
.text-flash {
  position: absolute;
  top: 104px;
  left: 63px;
  font-family: Epilogue;
  font-size: 20px;
  line-height: 30px;
  color: #21262eff;
}

/* Container 3 */
.done {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 160px;
  height: 10px;
  background: #d4c3a5ff;
  border-radius: 5px;
}

.process-container {
  position: absolute;
  top: 191px;
  left: 24px;
  width: 199px;
  height: 11px;
  background: #dee1e6ff;
  border-radius: 5.5px;
}
</style>