<template>
  <div>
    <label>
      <i class="far fa-calendar-alt"></i>
      <Datepicker
        v-model="date"
        locale="ja"
        :enableTimePicker="false"
        range
        multiCalendars
      />
    </label>
    <p v-if="settingDate">
      現在のピッチ資料は{{ settingDate }}から掲載しています
    </p>
  </div>
</template>

<script lang="ts" setup>
import { ref, defineProps } from "vue";
import Datepicker from "@vuepic/vue-datepicker";
import "@vuepic/vue-datepicker/dist/main.css";

defineProps({
  //現在のピッチ資料の掲載日
  settingDate: {
    type: String,
  },
});

const date = ref();
//データの初期値を直近7日間に設定
const endDate = new Date();
const startDate = new Date(new Date().setDate(endDate.getDate() - 7));
date.value = [startDate, endDate];
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";

div {
  label {
    line-height: 3.6rem;
    cursor: pointer;
    border-radius: 4px;
    background-color: $light-gray;
    display: block;
    font-size: $default;

    & .dp__main.dp__theme_light {
      opacity: 0;
    }
    & .fa-calendar-alt {
      color: $navy;
      font-size: $large;
    }
  }
  p {
    color: $gray;
    font-size: $small;
    letter-spacing: $narrow-spacing;
    line-height: 1.3;
    font-weight: $regular;
    position: relative;
    box-sizing: border-box;
    padding-left: 1.5rem;
    margin-top: 1rem;

    &::before {
      content: "※";
      position: absolute;
      left: 0;
      top: 0;
    }
  }
}
</style>
