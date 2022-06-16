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
          <div class="col-lg-6 col-md-12 mb-2" v-if="Object.keys(promotionalOffers.largeProduct).length">
            <div class="card product-item large-product"><a class="add-to-favorite" href="#">
                <svg>
                  <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                </svg></a><a href="#"><img :src="promotionalOffers.largeProduct.image_url" :alt="promotionalOffers.largeProduct.label"><span>{{ promotionalOffers.largeProduct.title }}</span></a>
              <p class="text-decoration-line-through price-before" v-if="promotionalOffers.largeProduct.before_price">{{ promotionalOffers.largeProduct.before_price }} ₴</p>
              <p class="current-price mb-0">{{ promotionalOffers.largeProduct.price }} ₴</p>
            </div>
          </div>
          <div class="col-lg-6 ps-lg-1 pe-lg-3">
            <div class="row index-action" data-masonry="{&quot;percentPosition&quot;: true }">
              <div class="col-lg-6 col-sm-6 col-6" v-for="(product, index) in promotionalOffers.normalProducts" :key="index">
                <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                    <svg>
                      <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                    </svg></a><a href="#">
                    <div class="product-img"><img :src="product.image_url" :alt="product.label"></div><span>{{ product.title }}</span></a>
                  <p class="text-decoration-line-through price-before mb-2" v-if="product.before_price">{{ product.before_price }} ₴</p>
                  <p class="current-price mb-0">{{ product.price }} ₴</p>
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
            <div v-for="catalog in catalogs" :key="catalog.productId" class="col-lg-3 col-md-6 col-6">
              <div class="card product-item add-height mb-2">
                <a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg>
                </a>
                <a href="#">
                  <div class="product-img">
                    <img :src="catalog.image_url" :alt="catalog.label">
                  </div>
                  <span>{{ catalog.title }}</span>
                </a>
                <p class="text-decoration-line-through price-before mb-2" v-if="catalog.price_before">{{ catalog.price_before }} ₴</p>
                <p class="current-price mb-0">{{ catalog.price }} ₴</p>
              </div>
            </div>
            <div class="col-12 d-block d-md-none"><a class="btn card text-decoration-none show-more font-size-13" href="#">Показати ще</a></div>
          </div>
        </div>
        <div class="mt-5">
          <h4>Найбільш очікуванні товари</h4>
          <div class="row">
            <div class="col-lg-6 col-md-12" v-if="Object.keys(anticipatedGoods.largeProduct).length">
              <div class="card product-item large-product mb-2"><a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg></a><a href="#"><img :src="anticipatedGoods.largeProduct.image_url" :alt="anticipatedGoods.largeProduct.label"><span>{{ anticipatedGoods.largeProduct.title }}</span></a>
                <p class="text-decoration-line-through price-before mb-2" v-if="anticipatedGoods.largeProduct.price_before">{{ anticipatedGoods.largeProduct.price_before }} ₴</p>
                <p class="current-price mb-0">{{ anticipatedGoods.largeProduct.price }} ₴</p>
                <p class="mt-2 mb-0 font-size-13">Очікуєтся</p>
              </div>
            </div>
            <div class="col-lg-6 col-md-12 d-flex d-lg-block justify-content-between">
              <div v-for="good in anticipatedGoods.normalProducts" :key="good.productId" class="card product-item mb-4 add-height waited">
                <a class="add-to-favorite" href="#">
                  <svg>
                    <use xlink:href="../assets/images/sprite.svg#icon-favorite"></use>
                  </svg>
                </a>
                <a href="#">
                  <div class="product-img">
                    <img :src="good.image_url" :alt="good.label">
                  </div>
                  <span>{{ good.title }}</span>
                </a>
                <p class="current-price mb-0 text-dark">{{ good.price }} ₴</p>
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
      catalogs: [],     // it contains the products which will be displayed on the main page
      categories: [],   // contains all the categories in the left sidebar
      anticipatedGoods: {
        largeProduct: {},
        normalProducts: []
      },  // goods in "the most anticipated goods" section
      promotionalOffers: {
        largeProduct: {},
        normalProducts: []
      },
      baseURL: "https://rozetka-web.azurewebsites.net"  //base url for loading images
    }
  },

  methods: {
    async getCategories() {
      const response = await fetch('https://rozetka-web.azurewebsites.net/api/v1/portals')
      const formatedResponse = await response.json()
      this.categories = formatedResponse.values
    },
    async getCatalogs() {
      const response = await fetch('https://rozetka-web.azurewebsites.net/api/v1/products')
      const formatedResponse = await response.json()

      // before displaying a catalog/product, call the api to get image_url
      formatedResponse.values.forEach(async (element, index) => {
        let url = await this.getProductImageUrl(element.productId)
        element.image_url = url
        this.catalogs.push(element)   // push products to "catalogs" array only after they have image_url

        // as there are not many products in database, duplicate the products in anticipatedGoods section
        if (index === 0){
          this.anticipatedGoods.largeProduct = element
          this.promotionalOffers.largeProduct = element
        }
        else{
          this.anticipatedGoods.normalProducts.push(element)
          this.promotionalOffers.normalProducts.push(element)
          this.promotionalOffers.normalProducts.push(element)
        }
      });
    },
    async getProductImageUrl(productId) {
      // this function gets the image related to a product
      const response = await fetch(`https://rozetka-web.azurewebsites.net/api/v1/products/{productId}/images/`)
      const formatedResponse = await response.json()
      const images = formatedResponse.values
      // loop throgh all the images and get the first image whose productId matches
      for(let i = 0; i < images.length; i++){
        if(images[i].productId === productId) return this.baseURL + images[i].url
      }
      return null
    }
  },

  async created () {
    this.getCategories()
    this.getCatalogs()
  }

}
</script>
