<template>
  <div class="tab-control">
    <div :class="{active : index===currentIndex}" @click="itemClick(index)" v-for="(items,index) in title" class="tab-control-item">
      <span>{{items}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TabControl',
  data(){
    return {
      currentIndex:0
    }
  },
  props: {
    title: {
      type:Array,
      default() {
        return []
      }
    }
  },
  methods:{
    itemClick(index){
      this.currentIndex = index
      this.$emit('tabClick', index)
    }
  }
}
</script>

<style scoped>
  .tab-control {
    display: flex;
    text-align: center;
    font-size: 15px;
    height: 40px;
    line-height: 40px;
  } 
  .tab-control-item{
    flex: 1;
  }
  .tab-control-item span {
    padding: 5px;
  }
  .active{
    color: var(--color-high-text);
  }
  .active span {
    border-bottom: 3px solid  var(--color-high-text);
  }
</style>