<template>
  <div class="home">
    <div class="container-fluid container-custom">
      <h1>Список товаров</h1>
      <div class="row">
        <div class="col-12">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Фильтры</h5>
              <div class="card-text">
                <form>
                  <Select
                    v-bind:optionsBrand="optionsBrand"
                    @push-filter-brand="replaceBrand"
                  />
                  <Select
                    v-bind:optionsSize="optionsSize"
                    @push-filter-size="replaceSize"
                  />
                  <Select
                    v-bind:optionsColor="optionsColor"
                    @push-filter-color="replaceColor"
                  />
                  <div class="text-right">
                    <a href="#" class="btn btn-sm btn-secondary">Сбросить</a>
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="alert alert-light" role="alert">
        Найдено 2 товара
      </div>
      <div class="row no-gutters">
        <div class="col-6 pr-2">
          <Card
            v-bind:products="filtered"
          />
        </div>
        <div class="col-6 pl-2">
          <Card
            v-bind:products="filtered"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from '@/components/Card.vue'
import Select from '@/components/Select.vue'

export default {
  name: 'Home',
  data () {
    return {
      optionsBrand: [
        { id: 1, title: 'Бренд' },
        { id: 2, title: 'Super' },
        { id: 3, title: 'Puper' },
        { id: 4, title: 'Cool' },
        { id: 5, title: 'Like' }
      ],
      optionsSize: [
        { id: 1, title: 'Размер' },
        { id: 2, title: '29' },
        { id: 3, title: '31' },
        { id: 4, title: '35' },
        { id: 5, title: '37' },
        { id: 6, title: '42' }
      ],
      optionsColor: [
        { id: 1, title: 'Цвет' },
        { id: 2, title: 'Синий' },
        { id: 3, title: 'Красный' },
        { id: 4, title: 'Зеленый' },
        { id: 5, title: 'Белый' },
        { id: 6, title: 'Серый' }
      ],
      products: [
        {
          id: 1,
          name: 'куртка красная',
          img: 'https://media.istockphoto.com/photos/smiling-woman-standing-with-arms-outstretched-picture-id867700828',
          category: 'куртки',
          oldPrice: 5880,
          price: 4790,
          brand: 'super',
          size: 31,
          color: 'красный'
        },
        {
          id: 2,
          name: 'куртка большая',
          img: 'https://media.istockphoto.com/photos/businesswoman-with-braided-hair-over-white-picture-id685132223',
          category: 'куртки',
          oldPrice: 5900,
          price: 3790,
          brand: 'super',
          size: 42,
          color: 'зеленый'
        },
        {
          id: 3,
          name: 'куртка модная',
          img: 'https://media.istockphoto.com/photos/male-coat-isolated-on-the-white-picture-id163208487',
          category: 'куртки',
          price: 5550,
          brand: 'puper',
          size: 29,
          color: 'красный'
        },
        {
          id: 4,
          name: 'куртка выгодная',
          img: 'https://media.istockphoto.com/photos/green-winter-clothing-picture-id628111594',
          category: 'куртки',
          oldPrice: 7900,
          price: 1990,
          brand: 'super',
          size: 29,
          color: 'зеленый'
        }
      ],
      currentFilterBrand: 'Бренд',
      currentFilterSize: 'Размер',
      currentFilterColor: 'Цвет'
    }
  },
  components: {
    Card, Select
  },
  methods: {
    replaceBrand (value) {
      this.currentFilterBrand = value
    },
    replaceSize (value) {
      this.currentFilterSize = value
    },
    replaceColor (value) {
      this.currentFilterColor = value
    }
  },
  computed: {
    filtered () {
      const brand = this.currentFilterBrand.toLowerCase()
      const size = this.currentFilterSize.toLowerCase()
      const color = this.currentFilterColor.toLowerCase()

      let resultFiltered

      if (brand !== this.optionsBrand[0].title.toLowerCase()) {
        resultFiltered = this.products.filter(t => t.brand === brand)
      } else {
        resultFiltered = this.products
      }

      if (size !== this.optionsSize[0].title.toLowerCase()) {
        resultFiltered = resultFiltered.filter(t => t.size === +size) // строку приводим к числу
      }

      if (color !== this.optionsColor[0].title.toLowerCase()) {
        resultFiltered = resultFiltered.filter(t => t.color === color)
      }

      // вполне вероятно тут можно ускорить фильтрацию, но надо это проверять на практике с большим массивом
      return resultFiltered
    }
  }
}
</script>

<style lang="sass" scoped>
  .container-custom
    max-width: 1200px
    margin-top: 2rem
</style>
