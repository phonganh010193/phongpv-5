<template>
    <div class="detail-validate-component">
        <div class="message" v-if="condition"  :style="{ color: conditionStyle}">{{ showMessage }}</div>
    </div>
</template>
<script>
export default {
    props: {
        error: Object,
        success: Object,
        name: String
    },
    computed: {
        condition() {
            return this.name === 'error' ? this.error.status : this.success.status
        },
        conditionStyle() {
            return this.name === 'error' ? this.error.color : this.success.color
        },
        showMessage() {
            return this.name === 'error' ? this.error.message : this.success.message 
        }
    }
    
}
</script>
<style>
    
</style>