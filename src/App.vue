<template>
    <div class="container">
      <div class="heading">
        <h2>Contact Manager</h2>
      </div>
      <nav>
        <span>
          <i class="fa-solid fa-house-chimney"></i>
          <router-link to="/">Home</router-link> 
        </span>
        <span>
          <i class="fa-solid fa-calendar-plus"></i>
          <router-link to="/add">Add</router-link> 
        </span>
        <span>
           <i class="fa-solid fa-circle-question"></i>
            <router-link to="/about">About</router-link>
        </span>
      </nav>

  </div>
  <router-view/>
  <footer>
    <a href="#">&copy;2022. David Ukpalichi</a>
  </footer>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Open Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}



.container {
  display: flex;
  justify-content: space-between;
  background-color: rgb(32, 32, 32);
  padding: 15px;
}

.heading {
  padding-left: 9%;
  color: white;
}

nav {
  padding-top: 15px;
  padding-right: 18%;

  
}

nav a {
  text-decoration: none;
  color:gainsboro;
  padding: 8px;
  cursor: pointer;
}

nav svg {
  color: gainsboro;
  cursor: pointer;
}

nav a.router-link-exact-active {
  color: white;
}

footer {
  background-color: rgb(32, 32, 32);
  padding: 15px;
  text-align: center;
  
}

footer a {
  cursor: pointer;
  color: white;
  text-decoration: none;
}
</style>
