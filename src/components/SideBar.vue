<template>
    <el-aside width="260px" style="background-color: rgb(238, 241, 246)">
        <el-menu :default-openeds="['1']">
            <menu-item v-for="(menu, index) in menuData" :id="`${index}`" :item="menu" :key="`menu-${index}`" />
        </el-menu>
    </el-aside>
</template>

<script>
import MenuItem from './MenuItem.vue'
export default {
    props: ['menuData'],
    components: { MenuItem },
    data() {
        return {}
    }
}
</script>