<template>
  <el-row class="tac">
    <el-col :span="6">
      <el-menu
        active-text-color="#ffd04b"
        background-color="#545c64"
        class="el-menu-vertical-demo"
        default-active="2"
        text-color="#fff"
        router
        @open="handleOpen"
        @close="handleClose"
      >
        <el-sub-menu index="1">
          <template #title>
            <el-icon><location /></el-icon>
            <span>Monitoring</span>
          </template>
          <el-menu-item-group title="Servers">
            <el-menu-item index="1-1" @click="handleClick" route="/about"
              >DB Server</el-menu-item
            >
            <el-menu-item index="1-2">Kafka</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="Services">
            <el-menu-item index="1-3">Scheduler</el-menu-item>
            <el-menu-item index="1-4">FileTransport</el-menu-item>
          </el-menu-item-group>
          <el-sub-menu index="1-5">
            <template #title>Processor</template>
            <el-menu-item index="1-5-1">compress</el-menu-item>
          </el-sub-menu>
        </el-sub-menu>
        <el-menu-item index="2">
          <el-icon><icon-menu /></el-icon>
          <span>Transfer Tasks</span>
        </el-menu-item>
        <el-menu-item index="3" disabled>
          <el-icon><document /></el-icon>
          <span>Charting</span>
        </el-menu-item>
        <el-menu-item index="4">
          <el-icon><setting /></el-icon>
          <span>Settings</span>
        </el-menu-item>
      </el-menu>
    </el-col>
  </el-row>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import {
  Location,
  Document,
  Menu as IconMenu,
  Setting,
} from "@element-plus/icons-vue";

export default defineComponent({
  components: {
    Location,
    Document,
    Setting,
    IconMenu,
  },
  setup() {
    const handleClick = (key: unknown) => {
      console.log("handle click", key);
    };
    const handleOpen = (key: unknown, keyPath: unknown) => {
      console.log(key, keyPath);
    };
    const handleClose = (key: unknown, keyPath: unknown) => {
      console.log(key, keyPath);
    };
    return {
      handleOpen,
      handleClose,
      handleClick,
    };
  },
});
</script>
