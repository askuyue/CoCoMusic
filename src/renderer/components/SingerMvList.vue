<template>
  <div>
    <f-mv-list
     :mvList="list"></f-mv-list>
    <button class="btn btn-block" v-show="!isEnd" :class="{'loading': loading}"
      @click="!isEnd && getTheList(page + 1)">更多</button>
    <div class="divider text-center" data-content="没有了" v-show="isEnd" ></div>
  </div>
</template>
<script>
import fMvList from './MvList'
import {getSingerMvList} from '../../spider/index.js'
import listMixins from './common/listMixins.js'

export default {
  mixins: [listMixins],
  data () {
    return {
      getList: getSingerMvList
    }
  },
  components: {
    fMvList
  }
}
</script>
<style scoped>
  
</style>
