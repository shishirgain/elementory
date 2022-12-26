<template>
    <el-container style="height: 100vh; border: 1px solid #eee">
        <side-bar :menuData="menuData" />
        <el-container>
            <el-header style="text-align: right; font-size: 12px">
                <el-dropdown>
                    <i class="el-icon-setting" style="margin-right: 15px"></i>
                    <el-dropdown-menu slot="dropdown">
                        <el-dropdown-item>View</el-dropdown-item>
                        <el-dropdown-item>Add</el-dropdown-item>
                        <el-dropdown-item>Delete</el-dropdown-item>
                    </el-dropdown-menu>
                </el-dropdown>
                <span>Tom</span>
            </el-header>

            <el-main>
                <el-table :data="tableData">
                    <el-table-column prop="date" label="Date" width="140">
                    </el-table-column>
                    <el-table-column prop="name" label="Name" width="120">
                    </el-table-column>
                    <el-table-column prop="address" label="Address">
                    </el-table-column>
                </el-table>
            </el-main>
        </el-container>
    </el-container>

</template>
<style>
.el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
}

.el-aside {
    color: #333;
}
</style>

<script>
import SideBar from './components/SideBar.vue';
export default {
    components: { SideBar },
    data() {
        const item = {
            date: '2016-05-02',
            name: 'Tom',
            address: 'No. 189, Grove St, Los Angeles'
        };
        return {
            tableData: Array(20).fill(item),
            menuData: [
                {
                    name: 'Menu 1',
                    hasIcon: true,
                    iconPath: '',
                    menu:[
                        {
                            name: 'Menu 1',
                            hasIcon: true,
                            iconPath: ''
                        }
                    ],
                    subMenu: [
                        {
                            name: 'Menu 1 1',
                            subMenu: [
                                {
                                    name: 'Menu 1 1 1',
                                    menu: [
                                        {
                                            name: 'Menu 1 1 1 1'
                                        }
                                    ]
                                },
                                {
                                    name: 'Menu 1 1 2'
                                },
                            ]
                        }
                    ]
                },
                {
                    name: 'Menu 2',
                    hasIcon: true,
                    iconPath: '',
                    subMenu: [
                        {
                            name: 'Menu 2 1',
                            subMenu: [
                                {
                                    name: 'Menu 2 1 1'
                                }
                            ]
                        }
                    ]
                },
                {
                    name: 'Menu 3',
                    hasIcon: true,
                    iconPath: '',
                    subMenu: {
                        name: 'Menu 3 1',
                        menu: {
                            name: 'Menu 3 1 1',
                            hasIcon: true,
                            iconPath: '',
                        }
                    }
                }
            ]
        }
    }
};
</script>