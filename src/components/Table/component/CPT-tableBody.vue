<template>
    <tbody>
        <template v-if="tableList.length">
            <tr v-for="item in tableList" :key="item.id">
                <CPTTableTh :item="item" />
                <CPTTableTdVue :item="item" :name="'first'"/>
                <CPTTableTdVue :item="item" :name="'last'"/>
                <CPTButtonDeleteVue @handleDelete="handleDelete" :item="item"/>
            </tr>
        </template>
        <template v-else>
            <div class="text-center">Không có dữ liệu nào</div>
        </template>
        
    </tbody>
</template>
<script>
import CPTTableTh from './CPT-table-th.vue';
import CPTButtonDeleteVue from './CPT-buttonDelete.vue'
import CPTTableTdVue from './CPT-table-td.vue';
export default {
    props: {
        tableList: Array
    },
    components: {
        CPTButtonDeleteVue,
        CPTTableTh,
        CPTTableTdVue
    },
    methods: {
        handleDelete(item) {
            this.$emit('handleDeleteChildren', item)
        }
    }
    
}
</script>
<style >
    
</style>