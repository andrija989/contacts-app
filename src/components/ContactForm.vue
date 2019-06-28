<template>
    <form @submit.prevent="handleAdd">
    <div>
      <label for="firstName">First Name</label>
      <input type="text" id="firstName" v-model="newContact.firstName" required>
    </div>
    <div>
      <label for="lastName">Last Name</label>
      <input type="text" id="lastName" v-model="newContact.lastName" required>
    </div>
    <div>
      <label for="email">Email</label>
      <input type="email" id="email" v-model="newContact.email" required>
    </div>

    <div>
      <button type="submit">Add Contact</button>
    </div>
  </form>
</template>

<script>
export default {
    data() {
        return {
            newContact: {
                firstName:'',
                lastName:'',
                email:''
            },
        }
    },
    methods: {
        handleAdd() {
            this.$emit('add-contact', this.newContact)
            this.newContact = {
                firstName:'',
                lastName:'',
                email:''
            }
        }
    }
}
</script>
