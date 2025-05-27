<template>
  <header id="navbar" class="w-full hidden lg:flex flex-col">
    <nav class="w-full flex justify-between border-bot">
      <github-corner url="https://github.com/SrDev36428" />
      <div class="flex">
        <NuxtLink id="nav-logo" to="/">
          <b>{{ config.logo_name }}</b>
        </NuxtLink>

        <NuxtLink id="nav-link" to="/" :class="{ active: isActive('/') }">
          Hello
        </NuxtLink>

        <NuxtLink id="nav-link" to="/about-me" :class="{ active: isActive('/about-me') }">
          About
        </NuxtLink>

        <NuxtLink id="nav-link" to="/projects" :class="{ active: isActive('/projects') }">
          Projects
        </NuxtLink>
      </div>

      <NuxtLink
        id="nav-link-contact"
        to="/contact-me"
        :class="{ active: isActive('/contact-me') }"
      >
        Contact 🤝
      </NuxtLink>
    </nav>
  </header>
</template>

<script setup>
import GithubCorner from "./GithubCorner.vue";
import config from "~/developer.json";

const isActive = (route) => {
  return route === route;
};
</script>

<script>
export default {
  name: "AppHeader",
};
</script>

<style>
#nav-link {
  border-right: 1px solid #1e2d3d;
  @apply text-menu-text font-fira_retina px-6 h-full flex items-center;
}

#nav-link-contact {
  border-left: 1px solid #1e2d3d;
  @apply text-menu-text font-fira_retina px-6 h-full flex items-center;
}

#nav-link:hover,
#nav-link-contact:hover {
  background-color: #1e2d3d74;
  color: white;
}

#nav-logo {
  border-right: 1px solid #1e2d3d;
  @apply text-menu-text font-fira_retina px-6 h-full flex items-center;
}

#nav-logo:hover {
  background-color: #1e2d3d74;
  color: white;
}

#nav-link.router-link-active,
#nav-link-contact.router-link-active {
  border-bottom: 2px solid #fea55f;
  color: white;
}

#nav-logo.router-link-active {
  border-right: 1px solid #1e2d3d;
  border-bottom: none;
  @apply text-menu-text;
}

#navbar > nav {
  height: 45px;
  font-size: 13px;
}
</style>
