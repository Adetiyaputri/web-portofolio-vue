<template>
  <nav class="navbar">
    <div class="container">
      <h2 class="logo">Octavia Rahmawati</h2>
      <ul class="nav-links">
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/skills">Skills</router-link></li>
        <li><router-link to="/projects">Projects</router-link></li>
        <li><router-link to="/contact">Contact</router-link></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  width: 100%;
  display: flex;
  position: sticky;
  align-items: center;
  top: 0;
  z-index: 10;
  background-color: #f860ae;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 60px;
  max-width: 1200px;
  margin: auto;
}

.logo {
  font-weight: 700;
  font-size: 22px;
  color: #111;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 25px;
}

.nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: 0.2s;
}

.nav-links a:hover,
.nav-links a.router-link-exact-active {
  color: #0077ff;
}
</style>
