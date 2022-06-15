<template>
  <!--<Tutorial/>-->

  <!-- Content start-->
  <div class="container">

    <!-- <ul>
        <li
            v-for="catalog in catalogs"
            :key="catalog.portalId"
        >
              {{ catalog }}
        </li>
    </ul> -->

    <div class="row">
      <!-- Left side bar-->
      <div class="col-lg-3 col-md-3 d-none d-lg-block">
        <div class="card card-box mb-3">
          <ul class="nav flex-column side-nav">
            <li v-for="(category, index) in categories" :key="category.portalId" class="nav-item">
              <a class="nav-link" href="category.html">
                <svg>
                  <use :xlink:href="require('@/assets/images/sprite.svg') + `#nav-icon-${index+1}`"></use>
                </svg>
                <span>{{ category.title }}</span>
              </a>
            </li>
          </ul>
        </div>
        <div class="card card-box mb-3">
          <ul class="nav flex-column side-nav">
            <li class="nav-item"><a class="nav-link" href="#">
                <svg>
                  <use xlink:href="../assets/images/sprite.svg#icon-support"></use>
                </svg><span>Довідковий центр</span></a></li>
          </ul>
        </div>
        <div class="card card-box mb-3">
          <h6 class="text-center">Ласкаво просимо!</h6>
          <p class="text-center font-size-13">Увійдіть, щоб отримувати рекомендації, персональні бонуси та знижки.</p><a class="btn btn-primary rounded-pill mb-3 font-size-13" href="#">Увійдіть до особистого кабінету</a>
        </div>
        <div class="card card-box mb-3">
          <p class="font-size-13">Ми в соціальних мережах</p>
          <ul class="d-flex justify-content-between align-items-center social-link m-0 p-0">
            <li><a href="#">
                <svg>
                  <use xlink:href="../assets/images/sprite.svg#facebook"></use>
                </svg></a></li>
            <li><a href="#">
                <svg>
                  <use xlink:href="../assets/images/sprite.svg#twitter"></use>
                </svg></a></li>
            <li><a href="#">
                <svg>
                  <use xlink:href="../assets/images/sprite.svg#youtube"></use>
                </svg></a></li>
            <li><a href="#"><img src="../assets/images/instagram.svg" alt="instagram"></a></li>
            <li><a href="#">
                <svg>
                  <use xlink:href="../assets/images/sprite.svg#viber"></use>
                </svg></a></li>
            <li><a href="#"><img src="../assets/images/telegram.svg" alt="telegram"></a></li>
          </ul>
        </div>
        <div class="card card-box mb-3">
          <p class="mb-2 font-weight-500">Допомога</p>
          <ul class="nav flex-column side-nav mb-4">
            <li><a class="nav-link" href="#">Доставка та оплата</a></li>
            <li><a class="nav-link" href="#">Кредит</a></li>
            <li><a class="nav-link" href="#">Гарантія</a></li>
            <li><a class="nav-link" href="#">Повернення товару</a></li>
            <li><a class="nav-link" href="#">Сервісні центри</a></li>
            <li><a class="nav-link" href="#">Відстежити замовлення</a></li>
          </ul>
          <p class="mb-2 font-weight-500">Інформація про компанію</p>
          <ul class="nav flex-column side-nav mb-4">
            <li><a class="nav-link" href="#">Про нас</a></li>
            <li><a class="nav-link" href="#">Умови використання сайту</a></li>
            <li><a class="nav-link" href="#">Вакансії</a></li>
            <li><a class="nav-link" href="#">Контакти</a></li>
          </ul>
          <p class="mb-2 font-weight-500">Сервіси</p>
          <ul class="nav flex-column side-nav mb-4">
            <li><a class="nav-link" href="#">Бонусний рахунок</a></li>
            <li><a class="nav-link" href="#">Premium</a></li>
            <li><a class="nav-link" href="#">Подарункові сертифікати</a></li>
            <li><a class="nav-link" href="#">Обмін</a></li>
            <li><a class="nav-link" href="#">Rozetka Travel</a></li>
          </ul>
          <p class="mb-2 font-weight-500">Партнерам</p>
          <ul class="nav flex-column side-nav mb-4">
            <li><a class="nav-link" href="#">Франчайзинг</a></li>
            <li><a class="nav-link" href="#">Продавати на Розетці</a></li>
            <li><a class="nav-link" href="#">Співпраця з нами</a></li>
          </ul>
          <hr>
          <div class="d-flex justify-content-between align-items-center"><img src="../assets/images/mastercard-logo.png" alt="mastercard-logo"><img src="../assets/images/visa-logo.png" alt="visa-logo"></div>
        </div>
      </div>
      <!-- Content-->
      <div class="col-lg-9 col-md-12">
        <!-- Slider-->
        <div class="wrap-slider">
          <div class="index-slider"><img src="../assets/images/banner.png" alt="banner-image"><img src="../assets/images/banner.png" alt="banner-image"><img src="../assets/images/banner.png" alt="banner-image"></div>
        </div><a class="btn btn-primary catalog-link mt-4 d-md-none d-block" href="#">
          <svg>
            <use xlink:href="../assets/images/sprite.svg#icon-catalog"></use>
          </svg><span>Каталог</span></a>
        <div class="d-flex align-items-center justify-content-between my-3">
          <h4>Акційні пропозиції</h4><a class="btn btn-light btn-lg ml-auto d-none d-sm-block" href="#">Всі акції <span>1036</span></a>
        </div>
        <div class="row">
          <div class="col-lg-6 col-md-12 mb-2">
            <div class="card product-item large-product"><a class="add-to-favorite" href="#">
                <svg>
                  <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                </svg></a><a href="#"><img src="../assets/images/product-1.png" alt="product-image"><span>Ноутбук ASUS VivoBook S14 S435EA-HM020 (90NB0SU1-M00330) Deep Green</span></a>
              <p class="text-decoration-line-through price-before">33 999 ₴</p>
              <p class="current-price mb-0">30 999 ₴</p>
            </div>
          </div>
          <div class="col-lg-6 ps-lg-1 pe-lg-3">
            <div class="row index-action" data-masonry="{&quot;percentPosition&quot;: true }">
              <div class="col-lg-6 col-sm-6 col-6">
                <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                    <svg>
                      <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                    </svg></a><a href="#">
                    <div class="product-img"><img src="../assets/images/product-2.png" alt="product-image"></div><span>Віскі Chivas Regal 1 л 12 років витримки 40% в подарунковій упаковці</span></a>
                  <p class="text-decoration-line-through price-before mb-2">1670 ₴</p>
                  <p class="current-price mb-0">1049 ₴</p>
                </div>
              </div>
              <div class="col-lg-6 col-sm-6 col-6">
                <div class="card product-item mb-2"><a class="add-to-favorite" href="#">
                    <svg>
                      <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                    </svg></a><a href="#">
                    <div class="product-img"><img src="../assets/images/product-3.png" alt="product-image"></div><span>Ігрова консоль Microsoft Xbox Series X 1TB (RRT-00010)</span></a>
                  <p class="text-decoration-line-through price-before mb-2">22 745 ₴</p>
                  <p class="current-price mb-0">22 195 ₴</p>
                </div>
              </div>
              <div class="col-lg-6 col-sm-6 col-6 d-none d-md-block">
                <div class="card product-item mb-2"><a class="add-to-favorite" href="#">
                    <svg>
                      <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                    </svg></a><a href="#">
                    <div class="product-img"><img src="../assets/images/product-5.png" alt="product-image"></div><span>Електросамокат Xiaomi Mi Electric Scooter 1S Black</span></a>
                  <p class="text-decoration-line-through price-before mb-2">13 999 ₴</p>
                  <p class="current-price mb-0">11 999 ₴</p>
                </div>
              </div>
              <div class="col-lg-6 col-sm-6 col-6 d-none d-md-block">
                <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                    <svg>
                      <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                    </svg></a><a href="#">
                    <div class="product-img"><img src="../assets/images/product-4.png" alt="product-image"></div><span>Мобільний телефон Apple iPhone 12 mini 128 GB White Офіційна гарантія</span></a>
                  <p class="text-decoration-line-through price-before mb-2">23 999 ₴</p>
                  <p class="current-price mb-0">21 999 ₴</p>
                </div>
              </div>
              <div class="col-lg-6"><a class="btn card text-decoration-none show-more font-size-13" href="#">Показати ще</a></div>
            </div>
          </div>
        </div>
        <div class="mt-5">
          <h4>Зараз шукають</h4>
          <div class="row">
            <div class="col-lg-3 col-sm-6 col-6">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-6.png" alt="product-image"></div><span>Телефон Apple iPhone 13 Pro Max 256 GB Sierra Blue</span></a>
                <p class="text-decoration-line-through price-before mb-2">47 499 ₴</p>
                <p class="current-price mb-0">46 499 ₴</p>
              </div>
            </div>
            <div class="col-lg-3 col-sm-6 col-6">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-7.png" alt="product-image"></div><span>Ігрова приставка PS5 PlayStation 5 Digital Edition</span></a>
                <p class="text-decoration-line-through price-before mb-2">&#8203;</p>
                <p class="current-price mb-0">17 899 ₴</p>
              </div>
            </div>
            <div class="col-lg-3 col-sm-6 col-6 d-none d-md-block">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-8.png" alt="product-image"></div><span>Кавомашина PHILIPS Series 2200 EP2235/40</span></a>
                <p class="text-decoration-line-through price-before mb-2">17 999 ₴</p>
                <p class="current-price mb-0">17 499 ₴</p>
              </div>
            </div>
            <div class="col-lg-3 col-sm-6 col-6 d-none d-md-block">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-9.png" alt="product-image"></div><span>Фен Dyson Supersonic HD03 (фуксія)</span></a>
                <p class="text-decoration-line-through price-before mb-2">&#8203;</p>
                <p class="current-price mb-0">14 490 ₴</p>
              </div>
            </div>
            <div class="col-12 d-block d-md-none"><a class="btn card text-decoration-none show-more font-size-13" href="#">Показати ще</a></div>
          </div>
        </div>
        <div class="mt-5">
          <h4>Кращі подарунки на Новий рік</h4>
          <div class="row">
            <div class="col-lg-6 col-md-6 col-sm-12">
              <div class="card product-item mb-2 bg-green text-white d-block product-cover">
                <div class="title-product w-75">
                  <p class="mb-0">Добірка подарунків у розділі</p>
                  <p>Товари для краси, здоров'я і догляду за тілом</p>
                </div><a class="btn btn-primary rounded-pill font-size-13" href="#">Перейти</a>
              </div>
            </div>
            <div class="col-lg-6 col-md-6 col-sm-12">
              <div class="card product-item mb-2 bg-brown text-white d-block product-cover">
                <div class="title-product w-75">
                  <p class="mb-0">Добірка подарунків у розділі</p>
                  <p>Побутова техніка</p>
                </div><a class="btn btn-primary rounded-pill font-size-13" href="#">Перейти</a>
              </div>
            </div>
          </div>
        </div>
        <div class="mt-5">
          <h4>Рекомендації на основі ваших переглядів</h4>
          <div class="row">
            <div class="col-lg-3 col-md-6 col-6">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-10.png" alt="product-image"></div><span>Фен ROWENTA CV9820 Ultimate Experience</span></a>
                <p class="text-decoration-line-through price-before mb-2">9 499 ₴</p>
                <p class="current-price mb-0">6 999 ₴</p>
              </div>
            </div>
            <div class="col-lg-3 col-md-6 col-6">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-11.png" alt="product-image"></div><span>Фен Philips серії 3000 BHD350/10</span></a>
                <p class="text-decoration-line-through price-before mb-2">&#8203;</p>
                <p class="current-price mb-0">799 ₴</p>
              </div>
            </div>
            <div class="col-lg-3 col-md-6 col-6 d-none d-md-block">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-12.png" alt="product-image"></div><span>Фен PHILIPS DryCare BHD274/00 ACmotor</span></a>
                <p class="text-decoration-line-through price-before mb-2">1 594 ₴</p>
                <p class="current-price mb-0">1 494 ₴</p>
              </div>
            </div>
            <div class="col-lg-3 col-md-6 col-6 d-none d-md-block">
              <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-13.png" alt="product-image"></div><span>Фен PHILIPS 5000 series BHD530/00</span></a>
                <p class="text-decoration-line-through price-before mb-2">&#8203;</p>
                <p class="current-price mb-0">1 799 ₴</p>
              </div>
            </div>
            <div class="col-12 d-block d-md-none"><a class="btn card text-decoration-none show-more font-size-13" href="#">Показати ще</a></div>
          </div>
        </div>
        <div class="mt-5">
          <h4>Найбільш очікуванні товари</h4>
          <div class="row">
            <div class="col-lg-6 col-md-12">
              <div class="card product-item large-product mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#"><img src="../assets/images/product-14.png" alt="product-image"><span>Ноутбук Apple MacBook Pro 16" M1 Max 1TB 2021 (MK1A3UA/A) Space Gray</span></a>
                <p class="text-decoration-line-through price-before mb-2">136 999 ₴</p>
                <p class="current-price mb-0">122 999 ₴</p>
                <p class="mt-2 mb-0 font-size-13">Очікуєтся</p>
              </div>
            </div>
            <div class="col-lg-6 col-md-12 d-flex d-lg-block justify-content-between">
              <div class="card product-item mb-4 add-height waited"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-15.png" alt="product-image"></div><span>Бездротовий геймпад PlayStation 5 Dualsense Purple для PS5/PS 5 Digital Edition</span></a>
                <p class="current-price mb-0 text-dark">2 999 ₴</p>
                <p class="mt-1 mb-0 font-size-13">Очікуєтся</p>
              </div>
              <div class="card product-item mb-4 add-height waited"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#">
                  <div class="product-img"><img src="../assets/images/product-16.png" alt="product-image"></div><span>Планшет Apple iPad mini 2021 Wi-Fi 256 GB Space Gray (MK7T3RK/A)</span></a>
                <p class="text-decoration-line-through price-before mb-2">25 999 ₴</p>
                <p class="current-price mb-0">23 999 ₴</p>
                <p class="mt-1 mb-0 font-size-13">Очікуєтся</p>
              </div>
            </div>
          </div>
          <div class="text-center my-4"><a class="btn btn-light btn-lg" href="#">Показати ще</a></div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'IndexPage',
  layout: 'custom',

  data() {
      return {
          catalogs: [],
          categories: []
      }
  },

  methods: {
    async getCategories() {
      const response = await fetch('https://rozetka-web.azurewebsites.net/api/v1/portals')
      const formatedResponse = await response.json()
      console.log("forma: ", formatedResponse)
      this.categories = formatedResponse.values
    }
  },

  async created () {
      const response = await fetch('https://rozetka-web.azurewebsites.net/api/v1/products')
      //const response = await fetch('https://jsonplaceholder.typicode.com/users')
      this.catalogs = await response.json()

      this.getCategories()
  }

}
</script>
