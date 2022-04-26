<template>
  <header>
    <router-link to="/" class="logo-hero">
      <Icon icon="logo" />
    </router-link>
    <nav>
      <router-link to="/login" class="login-btn">
        <span class="icon">
          <Icon icon="profile-circle" />
        </span>
        <span>Login</span>
      </router-link>
    </nav>
  </header>
</template>

<script>
import Icon from "./Icon";
export default {
  components: { Icon },
};
</script>

<style>
header {
  width: calc(100% - 20px);
  padding: 10px !important;
  margin: 10px !important;
  background: var(--brand-color);
  border-radius: 20px;
  box-shadow: 0px 4px 4px rgb(128 128 128 / 25%);
  display: flex !important;
  align-items: center;
  justify-content: space-between;
}

.logo-hero {
  display: inline-block;
  padding: 5px;
  background: var(--white-trns);
  border-radius: 15px;
  color: var(--white);
  transition: all 0.25s ease 0s;
}
.logo-hero svg {
  vertical-align: middle;
}

.login-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5px 10px;
  gap: 5px;
  background: var(--white-trns);
  border-radius: 15px;
  color: var(--white);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.25s ease 0s;
}
</style>
