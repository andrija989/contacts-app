<template>
  <div>
    <router-link :to="routeToContact">
      {{ fullName }} - {{ contact.email }}
    </router-link>
    <button @click="handleDelete">Delete</button>
  </div>
</template>

<script>
export default {
  props: ['contact'],

  data () {
    return {
      age: 1
    }
  },

  watch: {
    age (newValue, oldValue) {
      if (oldValue >= 18 && parseInt(newValue, 10) < 18) {
        alert('You are underage!')
        this.age = oldValue
      }
    }
  },

  methods: {
    handleDelete () {
      this.$emit('delete-contact')
    }
  },

  computed: {
    fullName () {
      return `${this.contact.firstName} ${this.contact.lastName}`
    },

    routeToContact () {
      return `/contacts/${this.contact.id}`
    }
  }

  // props: {
  //   contact: Object
  // },

  // props: {
  //   contact: {
  //     type: Object,
  //     required: false,
  //     default: {
  //       firstName: 'Jane',
  //       lastName: 'Doe',
  //       email: 'janedoe@example.com'
  //     }
  //   }
  // }
}
</script>
