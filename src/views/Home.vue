<template>
  <div class="home">
    <div class="mybox --bgc">我盒子</div>
    <el-select
      @change="changeColor"
      v-model="value"
      placeholder="请选择背景颜色"
    >
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      >
      </el-option>
    </el-select>
  </div>
</template>

<script>
export default {
  data () {
    return {
      value: '',
      options: [{
        value: '#0094ff',
        label: '蓝色'
      }, {
        value: 'green',
        label: '绿色'
      }, {
        value: 'skyblue',
        label: '天蓝色'
      }, {
        value: '#006584',
        label: '颜色4'
      }, {
        value: '#0082cc',
        label: '颜色5'
      }]
    }
  },
  methods: {
    changeColor (val) {
      // console.log(val);
      document.body.style.setProperty('--bgc', val);
    },
  }
}
</script>

<style lang="less" scoped>
.home {
  .mybox {
    width: 50px;
    height: 50px;
    background-color: var(--bgc);
  }
}
</style>