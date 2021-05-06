<template>
  <div id="yamisok">
    <b-navbar toggleable="md" variant="dark" type="dark" sticky>
      <b-navbar-brand class="home-nav-p" style='width:150px;' to="/"><img alt="IVISTA YAMISOK"  class="home-ivista-logo" width="150" src="/static/img/logo2.png"></b-navbar-brand>
      <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
      <b-collapse is-nav id="nav_collapse">
        <b-navbar-nav class="text-center mt-md-0 mt-2">
          <b-nav-item class="px-3 text-uppercase" to="/home">Home</b-nav-item>
          <b-nav-item class="px-3 text-uppercase" to="/form">Form</b-nav-item>
        </b-navbar-nav>
        <b-navbar-nav class="ml-auto">
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>

    <main>
      <router-view></router-view>
    </main>
  </div>
</template>