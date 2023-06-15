<template>
    <div class="validate-conponent">
        <CPTValidateDetailVue :error="error" :name="'error'"/>
        <CPTValidateDetailVue :success="success" :name="'success'"/>
    </div>
</template>
<script>
import CPTValidateDetailVue from './CPT-validateDetail.vue'
export default {
    components: {
        CPTValidateDetailVue
    },
    props: {
        error: Object,
        success: Object
    }
}
</script>
<style>
    
</style>