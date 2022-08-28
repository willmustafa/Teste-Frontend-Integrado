<template>
  <nav class="navbar">
    <div class="container">
      <a class="navbar-brand" href="#">
        <img
          src="../../assets/images/logo-branca.png"
          alt=""
          height="36"
          aria-label="Logotipo da Integrado"
        />
      </a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#mainMenu"
        aria-controls="mainMenu"
        aria-expanded="false"
        aria-label="Alternar navegação"
      >
        <span></span>
      </button>
      <div class="navbar-collapse show" id="mainMenu">
        <ul>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Leads</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Sair</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "MainNavbar",
};
</script>

<style scoped>
.navbar {
  position: sticky;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  justify-content: space-between;
  background-color: var(--background-dark);
  box-sizing: border-box;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.7);
  min-height: 100px;
}

.navbar > .container {
  display: flex;
  flex-wrap: inherit;
}

.navbar-brand {
  padding-top: 0.3rem;
  padding-bottom: 0.3rem;
  margin-right: 1rem;
  font-size: 1.25rem;
  text-decoration: none;
  white-space: nowrap;
  display: flex;
  justify-content: center;
  align-items: center;
}

.navbar-toggler {
  color: var(--secondary);
  border-color: var(--background-darker);
  padding: 0.25rem 0.75rem;
  font-size: 1.25rem;
  line-height: 1;
  background: transparent;
  border: none;
  cursor: pointer;
}

.navbar-toggler > span {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba%28255, 255, 255, 0.55%29' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
  display: inline-block;
  width: 1.5rem;
  height: 1.5rem;
  vertical-align: middle;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 100%;
}

.navbar-collapse {
  flex-grow: 1;
  align-items: center;
  display: flex;
}

.navbar-collapse:not(.show) {
  display: none;
}

.navbar-collapse > ul {
  display: flex;
  margin-left: auto;
  list-style: none;
  color: var(--secondary);
}

.navbar-collapse .nav-link {
  display: block;
  padding: 0.5rem 1rem;
  text-decoration: none;
  transition: color 0.15s ease;
}

.nav-link {
  color: var(--secondary);
}

.nav-link.active,
.nav-link:hover {
  color: white;
}

@media (min-width: 992px) {
  .navbar {
    flex-wrap: nowrap;
    justify-content: flex-start;
  }

  .navbar-toggler {
    display: none;
  }

  .navbar-collapse > ul {
    flex-direction: row;
  }
}
</style>
