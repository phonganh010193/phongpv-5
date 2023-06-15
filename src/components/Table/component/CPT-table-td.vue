<template >
    <td>{{ name === 'first' ? item.first : item.last }}</td>
</template>
<script>
export default {
    props: {
        item: Object,
        name: String
    }
    
}
</script>
<style >
    
</style>