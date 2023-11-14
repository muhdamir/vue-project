<template>
    <el-container class="main-container">
        <el-header class="common-container">
            <PageHeader />
        </el-header>
        <el-container class="content-container">
            <el-aside class="aside-container">
                <PageAside />
            </el-aside>
            <el-container>
                <el-main class="common-container">
                    <el-scrollbar>
                        <RouterView />
                    </el-scrollbar>
                </el-main>
                <el-footer class="footer-container">
                    <PageFooter />
                </el-footer>
            </el-container>
        </el-container>
    </el-container>
</template>

<script setup lang="ts">
import PageHeader from '@/components/PageHeader.vue'
import PageAside from '@/components/PageAside.vue'
import PageFooter from './components/PageFooter.vue';
</script>

<style scoped>
.main-container {
    height: 100vh;
}

.common-container {
    padding: 0;
}

.content-container {
    height: calc(100vh - var(--el-menu-horizontal-height));
}

.aside-container {
    width: initial;
}

.footer-container {
    padding: 0;
}
</style>