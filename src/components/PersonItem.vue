<template>
  <div class="actor-item">
    <el-avatar fit="cover" shape="square" :size="70" :src="avatar"></el-avatar>
    <dir>{{ name }}</dir>
    <i class="el-icon-error" @click="deleteActor()"></i>
  </div>
</template>
<script>
export default {
  props: ["id", "name", "avatar"],
  data() {
    return {};
  },
  methods: {
    // 删除演员接口
    deleteActor() {
      // 通知父组件，演员已经删除，主动触发在父组件中监听的delete事件
      this.$emit("delete");
    },
  },
};
</script>

<style scoped>
.actor-item {
  display: inline-block;
  margin: 20px 20px 0 0;
  text-align: center;
  position: relative;
}
.actor-item:hover i {
  display: block;
}
.actor-item i {
  position: absolute;
  font-size: 1.2em;
  top: -9px;
  right: -9px;
  display: none;
  color: #777;
}
.actor-item div {
  font-size: 0.9em;
}
.actor-item >>> img {
  width: 100%;
}
</style>
