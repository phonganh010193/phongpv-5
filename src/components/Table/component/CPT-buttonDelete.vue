<template>
        <td><button type="button" class="btn btn-danger" @click="$emit('handleDelete', item)">Delete</button></td>
</template>
<script>
export default {
    props: {
        item: Object
    }
}
</script>
<style>
    
</style>