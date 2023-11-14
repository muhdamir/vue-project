<template>
    <el-scrollbar>
        <el-menu class="menu-vertical" :default-active="$router.currentRoute.value.fullPath" :collapse="isCollapse"
            @open="handleOpen" @close="handleClose" :router="true">
            <el-menu-item index="" @click="isCollapse = !isCollapse">
                <el-icon>
                    <DArrowRight v-if="isCollapse" />
                    <DArrowLeft v-else />
                </el-icon>
                <template #title>{{ isCollapse ? "Expand" : "Collapse" }}</template>
            </el-menu-item>
            <el-sub-menu index="/1">
                <template #title>
                    <el-icon>
                        <location />
                    </el-icon>
                    <span>Navigator One</span>
                </template>
                <el-menu-item-group>
                    <template #title><span>Group One</span></template>
                    <el-menu-item index="/1-1">item one</el-menu-item>
                    <el-menu-item index="/1-2">item two</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group title="Group Two">
                    <el-menu-item index="1-3">item three</el-menu-item>
                </el-menu-item-group>
                <el-sub-menu index="1-4">
                    <template #title><span>item four</span></template>
                    <el-menu-item index="1-4-1">item one</el-menu-item>
                </el-sub-menu>
            </el-sub-menu>
            <el-menu-item index="/2">
                <el-icon><icon-menu /></el-icon>
                <template #title>Navigator Two</template>
            </el-menu-item>
            <el-menu-item index="3" disabled>
                <el-icon>
                    <document />
                </el-icon>
                <template #title>Navigator Three</template>
            </el-menu-item>
            <el-menu-item index="/4">
                <el-icon>
                    <setting />
                </el-icon>
                <template #title>Navigator Four</template>
            </el-menu-item>
        </el-menu>
    </el-scrollbar>
</template>
  
<script lang="ts" setup>
import { ref } from 'vue'
import {
    Document,
    Menu as IconMenu,
    Location,
    Setting,
    DArrowLeft,
    DArrowRight
} from '@element-plus/icons-vue'

const isCollapse = ref(true)
const handleOpen = (key: string, keyPath: string[]) => {
    console.log(key, keyPath)
}
const handleClose = (key: string, keyPath: string[]) => {
    console.log(key, keyPath)
}
</script>
  
<style scoped>
.menu-vertical:not(.el-menu--collapse) {
    width: 200px;
    /* min-height: 400px; */
}

.menu-vertical {
    /* height: 100vh; */
    min-height: calc(100vh - var(--el-menu-horizontal-height));
    /* overflow-y: scroll; */
}
</style>
  