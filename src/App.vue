<template>
  <div id="app">
    <FormView 
        @addUser="addUser" 
        @handleInput="handleInput"
        @handleShowValidateForm="handleShowValidateForm"
        @handlemMessageAddSuccess ="handlemMessageAddSuccess"
        :error="error" 
        :success="success" 
     />
    <TableViewVue :tableList="tableList" @handleDeleteParent="handleDeleteParent"/>
  </div>
</template>

<script>
import FormView from './components/Form/FormView.vue';
import TableViewVue from './components/Table/TableView.vue';
export default {
  name: 'App',
  components: {
    FormView,
    TableViewVue
  },
  data() {
    return {
        tableList: [
            {
            id: 1,
            first: 'Mark',
            last: 'Otto'
            },
            {
            id: 2,
            first: 'Jacob',
            last: 'Thornton'
            },
            {
            id: 3,
            first: 'Lazy',
            last: 'Bird'
            }
        ],
        error: {
            status: false,
            message: 'không được để trống!',
            color: 'red',
        },
        success: {
            status: false,
            message: 'Thêm thành công!',
            color: 'green',
        }
    }
  },
  methods: {
    addUser(firstName, lastName) {
      const value = {
        id: this.tableList.length + 1,
        first: firstName,
        last: lastName
      }
      this.tableList.push(value)
    },
    handleInput() {
        this.error.status = false
        this.success.status = false
    },
    handleShowValidateForm() {
        this.error.status = true
        this.success.status = false
    },
    handlemMessageAddSuccess() {
        this.success.status = true
    },
    handleDeleteParent(item) {
        this.tableList= this.tableList?.filter(el => el.id !== item.id)
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
