<template>
  <div>
    <!-- Content start-->
      <div class="container-fluid">
        <h2>{{ category.title }}</h2>
        <div class="row">
          <!-- Content-->
          <div class="col-12">
            <!-- Slider-->
            <div class="wrap-slider">
              <VueSlickCarousel :arrows="true" >
                <template #prevArrow>
                  <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                      <path fill="black" d="M15.41,16.58L10.83,12L15.41,7.41L14,6L8,12L14,18L15.41,16.58Z" />
                  </svg>
                </template>
                <img src="~/assets/images/banner.png" alt="banner-image">
                <img src="~/assets/images/banner.png" alt="banner-image">
                <img src="~/assets/images/banner.png" alt="banner-image">
                <template #nextArrow>
                  <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                    <path fill="black" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                  </svg>
                </template>
              </VueSlickCarousel>
            </div>
            <!-- <div class="wrap-slider">
              <div class="index-slider"><img src="images/banner.png" alt="banner-image"><img src="images/banner.png" alt="banner-image"><img src="images/banner.png" alt="banner-image"></div>
            </div> -->
          </div>
          <div class="col-12">
            <!-- Company logos-->
            <ul class="company-logos d-flex justify-content-between align-items-center ml-0 p-0">
              <li><img src="~assets/images/logos/ant-design_apple-filled.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/simple-icons_asus.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/cib_hp.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/simple-icons_acer.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/Lenovo_logo_2015.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/cib_samsung.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/cib_dell.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/Canon_wordmark.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/TPLINK_Logo_2.png" alt="logo company"></li>
              <li><img src="~assets/images/logos/Logitech_logo.png" alt="logo company"></li>
            </ul>
          </div>
          <div class="col-12">
            <div class="category-wrap">
              <div class="card product-item" v-for="product in products" :key="product.productId">
                <a class="d-block h-100" href="#">
                  <div class="product-img">
                    <img :src="product.image_url" alt="product-image">
                  </div>
                  <span class="text-center">{{ product.title }}</span>
                </a>
              </div>
            </div>
          </div>
          <div class="col-12 mt-5 popular-products">
            <h4>Популярні товари</h4>
            <div class="row">
              <div class="col-xxl-2 col-lg-4 col-md-4 col-sm-6 col-12" v-for="product in popularProducts" :key="product.id">
                <div class="card product-item add-height mb-2">
                    <a class="add-to-favorite" href="#">
                      <svg>
                        <use xlink:href="'~assets/images/icons/icon-favorite.svg'"></use>
                        <use xlink:href="../../assets/images/icons/icon-favorite.svg"></use>
                      </svg>
                    </a>
                    <a href="#">
                      <div class="product-img">
                        <img :src="product.image_url" alt="product-image">
                      </div>
                      <span>{{ product.title }}</span>
                    </a>
                    <div class="d-flex align-items-center mb-3">
                      <ul class="m-0 p-0 product-rating rating-4 d-flex align-items-center">
                        <li>
                          <svg>
                            <use xlink:href="'~assets/images/icons/icon-rating.svg'"></use>
                          </svg>
                        </li>
                        <li>
                          <svg>
                            <use xlink:href="'~assets/images/icons/icon-rating.svg'"></use>
                          </svg>
                        </li>
                        <li>
                          <svg>
                            <use xlink:href="'~assets/images/icons/icon-rating.svg'"></use>
                          </svg>
                        </li>
                        <li>
                          <svg>
                            <use xlink:href="'~assets/images/icons/icon-rating.svg'"></use>
                          </svg>
                        </li>
                        <li>
                          <svg>
                            <use xlink:href="'~assets/images/icons/icon-rating.svg'"></use>
                          </svg>
                        </li>
                      </ul><a class="ms-2" href="#">5 відгуків</a>
                    </div>
                    <p class="text-decoration-line-through price-before mb-2" v-if="product.before_price">{{ product.before_price }} ₴</p>
                    <p class="current-price mb-0">{{ product.price }} ₴</p>
                    <p class="availability mb-0">Є в наявності</p><a class="add-to-cart" href="#">
                      <svg>
                        <use xlink:href="@/assets/images/icon-mic.svg"></use>
                      </svg></a>
                  </div>
                </div>
            </div>
          </div>
          <div class="col-12 mt-5">
            <h4>Переглянуті товари</h4>
            <div class="row">
              <div class="col-xxl-2 col-lg-4 col-md-4 col-sm-6 col-12" v-for="product in viewedProducts" :key="product.id">
                <div class="card product-item add-height mb-2"><a class="add-to-favorite" href="#">
                    <svg>
                      <!-- <use xlink:href="@/assets/images/sprite.svg#icon-favorite"></use> -->
                      <img src="@/assets/images/icon-mic.svg" />
                    </svg></a><a href="#">
                    <div class="product-img"><img :src="product.image_url" alt="product-image"></div><span>{{ product.title }}</span></a>
                  <div class="d-flex align-items-center mb-3">
                    <ul class="m-0 p-0 product-rating rating-5 d-flex align-items-center">
                      <li>
                        <svg>
                          <use xlink:href="'images/sprite.svg#icon-rating'"></use>
                        </svg>
                      </li>
                      <li>
                        <svg>
                          <use xlink:href="'images/sprite.svg#icon-rating'"></use>
                        </svg>
                      </li>
                      <li>
                        <svg>
                          <use xlink:href="'images/sprite.svg#icon-rating'"></use>
                        </svg>
                      </li>
                      <li>
                        <svg>
                          <use xlink:href="'images/sprite.svg#icon-rating'"></use>
                        </svg>
                      </li>
                      <li>
                        <svg>
                          <use xlink:href="'images/sprite.svg#icon-rating'"></use>
                        </svg>
                      </li>
                    </ul><a class="ms-2" href="#">327 відгуків</a>
                  </div>
                   <p class="text-decoration-line-through price-before mb-2" v-if="product.before_price">{{ product.before_price }} ₴</p>
                  <p class="current-price mb-0">{{ product.price }} ₴</p>
                  <p class="availability mb-0">Є в наявності</p><a class="add-to-cart" href="#">
                    <svg>
                      <use xlink:href="'images/sprite.svg#icon-basket'"></use>
                    </svg></a>
                </div>
              </div>
            </div>
          </div>
          <div class="col-12 mt-5">
            <div class="row">
              <div class="col-lg-3 col-md-3 mb-md-0 mb-3"><img src="https://via.placeholder.com/450"></div>
              <div class="col-lg-3 col-md-3 mb-md-0 mb-3"><img src="https://via.placeholder.com/450"></div>
              <div class="col-lg-3 col-md-3 mb-md-0 mb-3"><img src="https://via.placeholder.com/450"></div>
              <div class="col-lg-3 col-md-3 mb-md-0 mb-3"><img src="https://via.placeholder.com/450"></div>
            </div>
          </div>
          <div class="col-12 mt-5">
            <h3>Що вибрати – персональний комп'ютер або ноутбук?</h3>
            <p>{{ category.description }}</p>
            <h3>Комп'ютери та ноутбуки на ROZETKA</h3>
            <p>{{ category.description }}</p>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
  layout: 'category',
  name: 'CategoriesPage',
  components: { VueSlickCarousel },
  data(){
    return {
      id: parseInt(this.$route.params.id), //id param from the url
      categories: [],
      category: {},
      products: [],
      baseURL: "https://rozetka-web.azurewebsites.net",  //base url for loading images
      popularProducts: [],
      viewedProducts: []
    }
  },
  methods:{
    async getCategoryInfo() {
      const response = await fetch('https://rozetka-web.azurewebsites.net/api/v1/portals')
      const formatedResponse = await response.json()
      this.categories = formatedResponse.values
      console.log("request completed")

      // get the title, description of the current category
      for (let i = 0; i < this.categories.length; i++){
        if (this.categories[i].portalId === this.id){
          this.category = {...this.categories[i]}
          break
        }
      }
    },
    async getProducts() {
      const response = await fetch('https://rozetka-web.azurewebsites.net/api/v1/products')
      const formatedResponse = await response.json()

      // before displaying a catalog/product, call the api to get image_url
      formatedResponse.values.forEach(async (element, index) => {
        let url = await this.getProductImageUrl(element.productId)
        element.image_url = url
        this.products.push(element)   // push products to "catalogs" array only after they have image_url
      });

      // add 6 products to popular products
      this.popularProducts = formatedResponse.values.slice(0,6)

      // add a product to "Viewed Products" section
      this.viewedProducts.push(formatedResponse.values[0])
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
  mounted(){
    // call the api and get data related to current category
    this.getCategoryInfo()

    this.getProducts()

  }
}
</script>

<style>

</style>
