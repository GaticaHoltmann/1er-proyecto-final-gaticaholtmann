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
        v-for="(funko, index) in funkos" :key="index" :name="funko.name" :image="funko.image"
        :price="funko.price" :serie="funko.serie"
        ></CardProduct>
    </ListProducts>
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
import HeaderStore from './components/HeaderStore.vue'
import FormAuth from './components/FormAuth.vue'
import FormRegistry from './components/FormRegistry.vue'
import ListProducts from './components/ListProducts.vue'
import FooterStore from './components/FooterStore.vue'
import CardProduct from './components/CardProduct.vue'

export default {
  name: 'App',
  components: {
    FormAuth,
    FormRegistry,
    HeaderStore,
    ListProducts,
    FooterStore,
    CardProduct,
    ButtonLogin,
    ButtonShopping
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
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 3,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw3d915c3b/images/funko/48664-1.png?sw=800&sh=800',
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 4,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw5100835a/images/funko/32260-1.png?sw=800&sh=800',
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
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
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 7,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw3d915c3b/images/funko/48664-1.png?sw=800&sh=800',
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
          serie: "Dragon Ball Z",
          price: 15000
        },
        {
          id: 8,
          image: 'https://funko.com/dw/image/v2/BGTS_PRD/on/demandware.static/-/Sites-funko-master-catalog/default/dw5100835a/images/funko/32260-1.png?sw=800&sh=800',
          name: "POP! BULMA IN BUNNY OUTFIT",
          description: "Genius scientist, Bulma, has donned a bunny costume, resulting in hilarity and shenanigans. Complete your Dragon Ball Z collection with this exclusive Pop! Bulma in bunny outfit. Vinyl figure is approximately 5.35-inches tall. ",
          serie: "Dragon Ball Z",
          price: 15000
        }
      ],
      showFormAuth: false,
      showRegistry: false,
      showProducts: true,
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
