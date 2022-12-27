<script>
import check from "../../src/assets/check.png";
export default {
  props: {
    checked: {
      type: Boolean,
      required: false,
    },
    click: {
      type: Function,
      required: false,
      default() {
        return false;
      },
    },
  },
  data() {
    return {
      checkedClick: false,
    };
  },
  methods: {
    handleChecked() {
      this.checkedClick = !this.checkedClick;
      !!this.click() && this.click();
    },
  },
};
</script>

<template>
  <div
    class="checkbox"
    v-if="!checkedClick && !checked"
    @click="handleChecked"
  ></div>
  <div
    class="checkboxChecked"
    v-if="checkedClick || checked"
    @click="handleChecked"
  >
    <img src="../../src/assets/check.png" class="img" />
  </div>
</template>

<style scoped>
.checkboxChecked {
  height: 20px;
  width: 20px;
  margin-right: 10px;
  background-color: #7f00b2;
  border-radius: 5px;
  cursor: pointer;
}
.checkbox {
  height: 20px;
  width: 20px;
  margin-right: 10px;
  border-radius: 5px;
  border: 1px solid #0000;
  background-color: #ffff;
  cursor: pointer;
}
.img {
  width: 20px;
  height: 20px;
}
</style>
