<template>
  <nav
    class="navbar navbar-expand-lg navbar-light"
    style="background-color: #a29bfe;"
  >
    <a class="navbar-brand" href="#">Todo List</a>

    <div class="collapse navbar-collapse" id="navbarText">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <router-link to="/todos" class="nav-link">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/" class="nav-link">Todos</router-link>
        </li>
      </ul>
    </div>
  </nav>

  <router-view />
</template>

<style>
.nav-link {
  width: 150px;
  color: black;
}
</style>
