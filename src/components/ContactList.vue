<template>
<div>
  
  <ul>
    <li v-for='(contact,index) in contacts' :key="index">
      <SingleContact
      :contact="contact"
      @delete-contact="handleDelete(index)" />
    </li>
  </ul>
</div>
</template>

<script>

import SingleContact from "./SingleContact"

export default {
  components: {
    
    SingleContact
  },

  props:['contacts'],

  handleDelete(index) {
    this.$emit('dekete-contact', index)
  }
}
</script>
