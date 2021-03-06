<template>
  <i-layout class="global-layout">
    <i-sider
      collapsible
      class="global-layout__sider"
      hide-trigger
      :width="256"
      :collapsed-width="64"
      v-model="isCollapsed"
    >
      <side-menu
        theme="dark"
        :accordion="true"
        :active-name="$route.name"
        :collapsed="isCollapsed"
        @on-select="turnToPage"
        :menu-list="menuList"
      >
        <div class="logo">
          <router-link to="/">
            <img class="logo__img" src="./../assets/images/logo.png">
            <h1 v-show="!isCollapsed" class="logo__title">{{ shortSiteName }}</h1>
          </router-link>
        </div>
      </side-menu>
    </i-sider>
    <i-layout
      :class="['global-layout__containers', this.isCollapsed ? 'global-layout__containers--expand-width' : '']"
    >
      <i-header
        :class="['global-layout__header', this.isCollapsed ? 'global-layout__header--expand-width' : '']"
      >
        <global-header :is-collapsed="isCollapsed" @toggleCollapse="toggleCollapse"/>
      </i-header>
      <i-content class="global-layout__content">
        <slot></slot>
      </i-content>
      <i-footer class="global-layout__footer">
        <global-footer/>
      </i-footer>
    </i-layout>
  </i-layout>
</template>

<script>
import { shortSiteName } from '@/config'
import SideMenu from '@/components/SideMenu'
import GlobalHeader from './GlobalHeader'
import GlobalFooter from './GlobalFooter'

export default {
  name: 'GlobalLayout',

  components: {
    SideMenu,
    GlobalHeader,
    GlobalFooter
  },

  filters: {},

  props: {},

  data() {
    return {
      isCollapsed: false,
      menuList: [],
      shortSiteName: shortSiteName
    }
  },

  computed: {},

  watch: {},

  created() {
    let list = this.$router.options.routes.find(item => item.path === '/').children
    this.menuList = this.$utils.getMenuList(list)
  },

  mounted() {},

  updated() {},

  activated() {},

  deactivated() {},

  destroyed() {},

  methods: {
    toggleCollapse() {
      this.isCollapsed = !this.isCollapsed
    },

    turnToPage(route) {
      let isLink = name.indexOf('href_') !== -1
      if (isLink) {
        window.open(name.split('_')[1])
        return
      }
      this.$router.push({ name: route })
    }
  }
}
</script>

<style lang="less">
.global-layout {
  &__sider {
    &.ivu-layout-sider {
      position: fixed;
      min-height: 100vh;
      box-shadow: 2px 0 6px rgba(0, 21, 41, 0.35);
      z-index: 9;
    }

    .logo {
      height: 64px;
      line-height: 64px;
      text-align: center;

      &__title {
        padding-left: 20px;
        box-sizing: border-box;
        font-size: 19px;
        font-weight: 600;
        display: inline-block;
        height: 32px;
        line-height: 32px;
        vertical-align: middle;
        text-transform: uppercase;
        color: #1890ff;
      }

      &__img {
        height: 34px;
        vertical-align: middle;
      }
    }
  }

  &__containers {
    min-height: 100vh;
    padding-left: 256px;

    &--expand-width {
      padding-left: 64px;
    }
  }

  &__header {
    width: 100%;
    position: fixed;
    top: 0;
    right: 0;
    width: calc(100% - 256px);
    z-index: 9;
    box-shadow: 0 1px 4px rgba(0, 21, 41, 0.08);
    transition: width 0.2s ease-in-out;

    &--expand-width {
      width: calc(100% - 64px);
    }
  }

  &__content {
    margin: 88px 24px 0px;
  }

  &__footer {
    text-align: center;
  }
}
</style>
