<template>
  <HeaderStore>
    <div>
      <ButtonLogin @click="toggleAuthForm" />
      <ButtonShopping />
    </div>
  </HeaderStore>
  <div class="body-app">
    <ListProducts v-show=showProducts>
      <CardProduct
        v-for="funko in funkos" :key="funko.id" :name="funko.name" :image="funko.image"
        :price="funko.price" :serie="funko.serie"
        @getProduct="showProduct(funko.id)"
        >
        <ButtonAddBasket/>
      </CardProduct>
    </ListProducts>
    <DetailsProduct 
      v-bind="selectedProduct"
      v-show="showSelectedProduct"
      @closeProduct="closeSelectedProduct"
    >
    <ButtonAddBasket/>
    </DetailsProduct>
    <FormAuth v-show="showFormAuth"
      @registry="toggleRegistry"
    ></FormAuth>
    <FormRegistry v-show="showRegistry"></FormRegistry>
  </div>
  <FooterStore />
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap/dist/js/bootstrap'
import ButtonLogin from './components/ButtonLogin.vue'
import ButtonShopping from './components/ButtonShopping.vue'
import ButtonAddBasket from './components/ButtonAddBasket.vue'
import HeaderStore from './components/HeaderStore.vue'
import FormAuth from './components/FormAuth.vue'
import FormRegistry from './components/FormRegistry.vue'
import ListProducts from './components/ListProducts.vue'
import FooterStore from './components/FooterStore.vue'
import CardProduct from './components/CardProduct.vue'
import DetailsProduct from './components/DetailsProduct.vue'

export default {
  name: 'App',
  components: {
    FormAuth,
    FormRegistry,
    HeaderStore,
    ListProducts,
    FooterStore,
    CardProduct,
    DetailsProduct,
    ButtonLogin,
    ButtonAddBasket,
    ButtonShopping,
},
  data() {
    return {
      funkos: [
        {
          id: 1,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw51e7faef/images/funko/upload/68236_POPAnimatino_DB_Bulma_BunnySuit_GLAM-WEB.png?sw=800&sh=800',
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 2,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw9a5fce97/images/funko/48662-1.png?sw=800&sh=800',
          name: "POP! VEGITO",
          description: "Goku and Vegeta have successfully fused, creating the most powerful warrior, in order to protect Earth and your Dragon Ball Z collection from attackers. Collect Pop! Vegito to save your set from destruction. Vinyl figure is approximately 4.5-inches tall",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 3,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw3d915c3b/images/funko/48664-1.png?sw=800&sh=800',
          name: "POP! DR. GERO",
          description: "Dr. Gero, or Android 20, is the mastermind behind the creation of Cell and the Red Ribbon Androids. In his ploy to defeat Goku, the Dragon Team, and take over Earth, Dr. Gero has taken on Pop! form to infiltrate your Dragon Ball Z collection. Vinyl figure is approximately 4.5-inches tall",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 4,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw5100835a/images/funko/32260-1.png?sw=800&sh=800',
          name: "POP! MASTER ROSHI WITH STAFF",
          description: "Every Dragon Ball Z collection needs to have Goku’s old instructor, Master Roshi. Collect this Pop! of Master Roshi with his staff to help your Dragon Ball Z collection keep up with their training. Collectible stands 3.75-inches tall.",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 5,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw51e7faef/images/funko/upload/68236_POPAnimatino_DB_Bulma_BunnySuit_GLAM-WEB.png?sw=800&sh=800',
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 6,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw9a5fce97/images/funko/48662-1.png?sw=800&sh=800',
          name: "POP! VEGITO",
          description: "Goku and Vegeta have successfully fused, creating the most powerful warrior, in order to protect Earth and your Dragon Ball Z collection from attackers. Collect Pop! Vegito to save your set from destruction. Vinyl figure is approximately 4.5-inches tall",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 7,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw3d915c3b/images/funko/48664-1.png?sw=800&sh=800',
          name: "POP! DR. GERO",
          description: "Dr. Gero, or Android 20, is the mastermind behind the creation of Cell and the Red Ribbon Androids. In his ploy to defeat Goku, the Dragon Team, and take over Earth, Dr. Gero has taken on Pop! form to infiltrate your Dragon Ball Z collection. Vinyl figure is approximately 4.5-inches tall",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 8,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw5100835a/images/funko/32260-1.png?sw=800&sh=800',
          name: "POP! MASTER ROSHI WITH STAFF",
          description: "Every Dragon Ball Z collection needs to have Goku’s old instructor, Master Roshi. Collect this Pop! of Master Roshi with his staff to help your Dragon Ball Z collection keep up with their training. Collectible stands 3.75-inches tall.",
          serie: "Dragon Ball Z",
          price: 15000
        }
      ],
      showFormAuth: false,
      showRegistry: false,
      showProducts: true,
      selectedProduct: {},
      showSelectedProduct: false,
      users: [
        {
          name: "David",
          lastName: "Gatica",
          email: "alh.gatica@gmail.com",
          pwd: "123123"
        }
      ]
    }
  },
  methods: {
    toggleAuthForm() {
      this.showFormAuth = !this.showFormAuth
      this.showProducts = false
      this.showRegistry = false
    },
    toggleRegistry(){
      this.showRegistry = !this.showRegistry
      this.showFormAuth = false
      this.showProducts = false
    },
    toggleProducts(){
      this.showProducts = !this.showProducts
    },
    showProduct(id){
      this.showProducts = false
      var index = this.funkos.findIndex(funko => funko.id === id)
      this.selectedProduct = this.funkos[index]
      this.showSelectedProduct = true
    },
    closeSelectedProduct(){
      this.showSelectedProduct = false
      this.selectedProduct = {}
      this.showProducts = true
    }

  }
}
</script>

<style>
#app {
  display: grid;
  grid-gap: 0.5rem;
  grid-template-areas:
    'header'
    'body'
    'footer';
}

.body-app {
  height: 70vh;
  grid-area: body;
  overflow: scroll;
}
</style>
