<template>
  <div class="example">
    <v-contextmenu ref="contextmenu" :theme="theme">
      <v-contextmenu-item @click="handleClick">菜单1</v-contextmenu-item>
      <v-contextmenu-item disabled @click="handleClick">菜单2</v-contextmenu-item>

      <v-contextmenu-item divider></v-contextmenu-item>

      <v-contextmenu-submenu title="子菜单">
        <v-contextmenu-item @click="handleClick">菜单3</v-contextmenu-item>

        <v-contextmenu-item divider></v-contextmenu-item>

        <v-contextmenu-submenu disabled title="子菜单">
          <v-contextmenu-item @click="handleClick">菜单5</v-contextmenu-item>
        </v-contextmenu-submenu>

        <v-contextmenu-item @click="handleClick">菜单4</v-contextmenu-item>
      </v-contextmenu-submenu>
    </v-contextmenu>

    <div :class="['box', theme]" v-contextmenu:contextmenu>
      右键点击此区域
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Disabled',

    props: {
      theme: String,
    },

    methods: {
      handleClick (event, vm) {
        console.log(event, vm)
      },
    },
  }
</script>

<style scoped>
  .box {
    width: 100%;
  }
</style>
