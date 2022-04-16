<template>
  <div class="contact-card">
    <header>
            <h3>{{ contact.name  }}</h3>
            <button id='toggle-btn' @click="toggleOpen">
                <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M19 13l-7 7-7-7m14-8l-7 7-7-7" />
                </svg>
            </button>

            <div className="actions">
                <button id='edit-btn' @click="$emit('editContact', contact.id)">
                    <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
                    </svg>
                </button>
                <button id="delete-btn" @click="$emit('deleteContact', contact.id)">
                    <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M6 18L18 6M6 6l12 12" />
                    </svg>
                </button>
            </div>
        </header>
        
        <div v-if="isOpen" className="content">
            <p><b>Email:</b> {{ contact.email }}</p>
            <p><b>Phone:</b> {{ contact.phone }}</p>
        </div>
        
  </div>
</template>

<script>
export default {
  name: 'ContactCard',
  props: {
    contact: Object,
  },
  data(){
      return {
        isOpen: false
      }
    },
    methods: {
      toggleOpen () {
        this.isOpen = !this.isOpen
      }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
.contact-card {
    border: 1px solid #ccc;
    border-radius: 10px;
    padding: 20px;
}

.contact-card header {
    display: flex;
}

.contact-card header button {
    padding: 5px;
    border: none;
    background-color: transparent;
    cursor: pointer;
    margin: 0px 10px;
}

.contact-card header svg {
    width: 20px;
}

.contact-card header .actions {
    margin-left: auto;
}

.contact-card .content {
    border: 1px solid #ccc;
    border-radius: 10px;
    margin-top: 10px;
}

.contact-card .content p {
    padding: 15px 10px;
}

.contact-card .content p:not(:last-child) {
    border-bottom: 1px solid #ccc;
}
</style>
