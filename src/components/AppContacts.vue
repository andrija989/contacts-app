<template>
  <router-view
    :contact="contact"
    :contacts="contacts"
    @add-contact="addContact"
    @delete-contact="deleteContact"
  />
</template>

<script>
export default {
  data () {
    return {
      contacts: [
        { id: 1, firstName: 'John', lastName: 'Doe', email: 'johndoe@example.com' },
        { id: 2, firstName: 'Jane', lastName: 'Doe', email: 'janedoe@example.com' },
        { id: 3, firstName: 'Jason', lastName: 'Doe', email: 'jasondoe@example.com' }
      ]
    }
  },

  computed: {
    contact () {
      return this.contacts.find(contact => {
        return contact.id == this.$route.params.id
      })
    }
  },

  methods: {
    deleteContact (index) {
      this.contacts.splice(index, 1)
      this.$router.push('/contacts/list')
    },

    addContact (contact) {
      this.contacts.push({ ...contact })
      this.$router.push('/contacts/list')
    }
  }
}
</script>