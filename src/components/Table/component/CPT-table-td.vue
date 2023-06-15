<template >
    <td>{{ showContent }}</td>
</template>
<script>
export default {
    props: {
        item: Object,
        name: String
    },
    computed: {
        showContent() {
            return this.name === 'first' ? this.item.first : this.item.last 
        }
    }

    
}
</script>
<style >
    
</style>