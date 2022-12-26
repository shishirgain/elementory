<template>
    <el-submenu :index="`${id}`">
        <template slot="title"><img class="el-icon-message" v-if="item.hasIcon" :src="icon" alt="ico"> {{item.name}}</template>
        <el-menu-item v-for="(menu, index) in item.menu" :key="`menu-${id}-${index}`" :index="`menu-${id}-${index}`">{{ menu.name }}</el-menu-item>
        <menu-item v-for="(submenu, i) in item.subMenu" :key="`${id}-${i}`" :item="submenu" :id="`${id}-${i}`" />
    </el-submenu>
</template>

<script>
import MenuItem from './MenuItem.vue'
export default {
    name: 'menu-item',
    props: ['item', 'id'],
    components: { MenuItem },
    data() {
        return {
            icon: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c6/Sign-check-icon.png/768px-Sign-check-icon.png'
        }
    }
}
</script>

<style scoped>
.icon{
    width: 20px;
    height: 20px;
}
</style>