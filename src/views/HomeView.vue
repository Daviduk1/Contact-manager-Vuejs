<template>
  <div class="home">
    <main>
      <contact-card 
        v-for="user in users" 
        :key="user.id" 
        :contact="user"
        @edit-contact="(id) => editUser(id)"
        @delete-contact="(id) => deleteUser(id)"
        @new-user="(user) => demo(user)"
      >
      </contact-card>

    </main>
  </div>
</template>

<script>
  import axios from 'axios'
import ContactCard from '@/components/ContactCard.vue'
  export default {
  components: { ContactCard },
    name: 'HomeView',
    data(){
      return {
        users: []
      }
    },
    mounted() {
      axios
        .get ('https://jsonplaceholder.typicode.com/users')
        .then(res => {
          this.users = res.data
        })

        let params = this.$route.params
        console.log(typeof params.newUser);
    },
    methods: {
      editUser (id) {
          this.$router.push({name: 'add'})
        console.log('I am editing contact with id', id);
      },
      deleteUser (id) {
        let filteredUsers = this.users.filter(user => user.id !== id)
        this.users = filteredUsers
      },
      demo (user) {
        console.log(user);
      }
    }
  }
</script>
<style scoped>

.home {
    min-height:90vh;
    display: grid;
    grid-template-rows: 1fr auto;
}
  
.home main {
    padding: 10px 15%;
    display: flex;
    flex-direction: column;
    gap: 15px;
}
</style>