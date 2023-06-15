<template>
    <div class="table-component">
        <CPTH2 />
        <div class="input-group flex-nowrap">
            <span class="input-group-text" id="addon-wrapping">@</span>
            <input type="text" class="form-control" v-model="firstName" placeholder="FirstName" aria-label="FirstName" @input="$emit('handleInput')"
                aria-describedby="addon-wrapping">
        </div>
        <div class="input-group flex-nowrap">
            <span class="input-group-text" id="addon-wrapping">@</span>
            <input type="text" class="form-control" v-model="lastName" placeholder="LastName" aria-label="LastName" @input="$emit('handleInput')"
                aria-describedby="addon-wrapping">
        </div>
        <CPTValidate :error="error" :success="success" />
        <CPTButton @handleAddUser="handleAddUser"/>
    </div>
</template>
<script>
import CPTH2 from './component/CPT-h2.vue'
import CPTValidate from './component/CPT-validate.vue'
import CPTButton from './component/CPT-button.vue'
export default {
    props: {
        error: Object,
        success: Object
    },
    components: {
        CPTH2,
        CPTValidate,
        CPTButton
    },
    data() {
        return {
            firstName: '',
            lastName: '',
        }
    },
    methods: {
        validateForm() {
          if(!this.firstName || !this.lastName) {
            this.$emit('handleShowValidateForm')
          }
          return;
        },
        handleAddUser() {
            this.validateForm()
            if(this.firstName && this.lastName) {
                this.$emit('addUser', this.firstName, this.lastName)
                this.$emit('handlemMessageAddSuccess')
                this.firstName = '',
                this.lastName = ''
            }
        }
    },

}
</script>
<style >
    
</style>