<template>
    <div class="table-conponent">
        <table class="table">
        <CPTTableHeader />
        <CPTTableBodyVue :tableList="tableList" @handleDeleteChildren="handleDeleteChildren" />
        </table>
    </div>
</template>
<script>
import CPTTableHeader from './component/CPT-tableHeader.vue';
import CPTTableBodyVue from './component/CPT-tableBody.vue';
export default {
    props: {
        tableList: Array
    },
    components: {
        CPTTableHeader,
        CPTTableBodyVue
    },
    methods: {
        handleDeleteChildren(item) {
            this.$emit('handleDeleteParent', item)
        }
    }
    
}
</script>
<style>
    
</style>