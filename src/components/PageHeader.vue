<template>
    <el-menu :default-active="activeIndex" mode="horizontal" :ellipsis="false" @select="handleSelect" :router="true">
        <el-menu-item index="/0">
            <h1>Template</h1>
        </el-menu-item>
        <div class="flex-grow" />
        <el-menu-item index="/login">Login</el-menu-item>
        <el-sub-menu index="2">
            <template #title>Workspace</template>
            <el-menu-item index="2-1">item one</el-menu-item>
            <el-menu-item index="2-2">item two</el-menu-item>
            <el-menu-item index="2-3">item three</el-menu-item>
            <el-sub-menu index="2-4">
                <template #title>item four</template>
                <el-menu-item index="2-4-1">item one</el-menu-item>
                <el-menu-item index="2-4-2">item two</el-menu-item>
                <el-menu-item index="2-4-3">item three</el-menu-item>
            </el-sub-menu>
        </el-sub-menu>
        <!-- <button @click="toggleDark()">hahahaha</button> -->
        <el-switch :active-action-icon="Moon" :inactive-action-icon="Sunny" v-model="isDark"
            class="custom-menu-item switch-theme" />
    </el-menu>
</template>
  
<script lang="ts" setup>
import { computed, ref } from 'vue'
import { useDark, useToggle } from '@vueuse/core'
import { Sunny, Moon } from '@element-plus/icons-vue'
import { useRouter } from 'vue-router';


const isDark = useDark()
// const toggleDark = useToggle(isDark)

// router is reactive by default
const router = useRouter()
const activeIndex = computed(() => router.currentRoute.value.fullPath)

const handleSelect = (key: string, keyPath: string[]) => {
    console.log(key, keyPath)
}
</script>
  
<style scoped>
.flex-grow {
    flex-grow: 1;
}

.custom-menu-item {
    align-self: center;
    padding: 0 var(--el-menu-base-level-padding);
}

.switch-theme {
    --el-switch-on-color: var(--el-switch-off-color);
}
</style>
  