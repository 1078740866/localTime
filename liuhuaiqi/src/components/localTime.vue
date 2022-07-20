<!-- import { METHODS } from "http"; -->
<template>
  <div>
    <h1>現在時刻</h1>
    <p id="now">{{ localTime }}</p>
  </div>
</template>

<script>
export default {
  name: "GenZai",
  props: {},
  data() {
    return {
      localTime: " ",
      value: 0,
      intervalId: null,
    };
  },
  methods: {
      // 计时器为空，操作
      showLocaleTime: function () {
      var time = this;
      setInterval(function () {
       time.localTime = new Date();
    }, 1000);
   }
    },
    // 停止定时器
    
  computed: {
    now: function () {
      return Date();
    },
  },
  destroyed() {
    // 在页面销毁后，清除计时器
    this.clear();
  },
  mounted() {
    this.showLocaleTime()
},
}
</script>
