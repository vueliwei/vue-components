<template>
  <layout>
    <x-header slot="header">
      <div slot="title">Badge</div>
    </x-header>
    <x-body slot="body" class="badge-demos">
      <group>
        <cell>
          <div slot="title">红点</div>
          <div slot="value">新消息<badge class="badge"/></div>
        </cell>
        <cell @click="clickHandler">
          <div slot="title">个位数红点(点击累加)</div>
          <div slot="value">新消息<badge class="badge" :text="count"/></div>
        </cell>
        <cell>
          <div slot="title">超出最大值显示(ellipsis)红点</div>
          <div slot="value">新消息<badge class="badge" :text="Number(20)"/></div>
        </cell>
        <cell>
          <div slot="title">多位数红点</div>
          <div slot="value">新消息<badge class="badge" text="888"/></div>
        </cell>
      </group>
    </x-body>
  </layout>
</template>

<script>
import {
  Layout,
  XHeader,
  XBody,
  Badge,
  Group,
  Cell
} from 'components'
export default {
  components: {
    Layout,
    XHeader,
    XBody,
    Badge,
    Group,
    Cell
  },
  methods: {
    clickHandler () {
      this.count++
    }
  },
  data () {
    return {
      count: 8
    }
  }
}
</script>

<style lang="scss">
  .badge-demos{
    .badge{
      margin-left:5px;
      margin-right:2px;
    }
  }
</style>
