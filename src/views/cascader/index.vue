<template>
  <div class="">
    <el-cascader
      :options="optionsData"
      placeholder="请选择"
      clearable
      v-model="selectValue"
      @change="handleChange"
      :show-all-levels="false"
      :props="{ emitPath: false }"
    />
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue";
const selectValue = ref();
const optionsData = [
  {
    value: "1",
    label: "1",
    children: [
      {
        value: "2",
        label: "2",
        children: [{ value: "3", label: "3", children: [] }],
      },
    ],
  },
];
const handleChange = () => {
  console.log("当绑定值变化时触发的事件");
  console.log(selectValue.value, "选中项绑定值");
};
</script>
<style lang="scss" scoped></style>
