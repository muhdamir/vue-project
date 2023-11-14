<template>
    <el-divider class="custom-divider" />
    <el-row justify="space-between">
        <el-col :span="6">
            <div class="title-footer">Your Title</div>
        </el-col>
        <el-col :span="6">
            <div class="title-footer"> link|link|link
            </div>
        </el-col>
    </el-row>
</template>

<script setup lang="ts">
const today = new Date()
const year = today.getFullYear()
</script>

<style scoped>
.custom-divider {
    margin: 0;
}

.title-footer {
    padding: calc(var(--el-menu-base-level-padding) - 2px);
}
</style>