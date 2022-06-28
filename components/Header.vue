<template>
  <header>
    <!-- Top bar-->
    <div class="top-bar d-none d-md-block">
      <div class="container-fluid">
        <p class="mb-0">ТОТАЛЬНИЙ РОЗПРОДАЖ ДО -50%</p>
      </div>
    </div>
    <div class="header-container">
      <div class="container-fluid">
        <div class="row align-items-center">
          <div
            class="col-lg-3 col-md-3 col-sm-1 col-1 d-flex align-items-center"
          >
            <button class="toggle-nav">
              <span></span><span></span><span></span>
            </button>
            <div class="logo d-none d-md-block">
              <a href="#"><img src="~/static/images/logo.svg" alt="logo" /></a>
            </div>
          </div>
          <div
            class="
              col-lg-9 col-md-9 col-sm-11 col-11
              d-flex
              justify-content-between
              align-items-center
            "
          >
            <a class="btn btn-primary catalog-link d-none d-lg-block" href="#">
              <img src="~/static/images/icon-catalog.svg" /><span>Каталог</span></a
            >
            <div class="header-search">
              <form>
                <div class="form-group position-relative">
                  <span class="search-icon">
                    <img src="~/static/images/icon-search.svg"
                  /></span>
                  <input type="text" placeholder="Я шукаю..." />
                  <button class="btn btn-primary" type="submit">Знайти</button
                  ><span class="mic-icon">
                    <img src="~/static/images/icon-mic.svg"
                  /></span>
                </div>
              </form>
            </div>
            <ul class="nav header-nav align-items-center">
              <li class="nav-item mb-0 d-none d-md-block">
                <div class="tarrif text-white text-center">
                  <p class="mb-0">Спробуйте</p>
                  <a
                    class="
                      badge
                      bg-warning
                      rounded-pill
                      text-decoration-none text-dark
                    "
                    href="#"
                    >PREMIUM</a
                  >
                </div>
              </li>
              <li class="nav-item mx-4 mb-0 d-none d-md-block">
                <a class="open-popup" href="#login-popup">
                  <img src="~/static/images/icon-user.svg"
                /></a>
              </li>
              <li class="nav-item position-relative mb-0">
                <a href="#">
                  <img src="~/static/images/icon-basket.svg" /><span
                    class="
                      position-absolute
                      top-0
                      start-100
                      translate-middle
                      badge
                      rounded-pill
                      bg-primary
                    "
                    >2</span
                  ></a
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style>
</style>
