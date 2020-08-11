<template>
  <div class="home">
    <div class="container-fluid">
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
                    v-model="filterBrand"
                  />
                  <Select
                    v-bind:optionsSize="optionsSize"
                    v-model="filterSize"
                  />
                  <Select
                    v-bind:optionsColors="optionsColor"
                    v-model="filterColor"
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
        { id: 1, title: 'Бренд', value: 'brand' },
        { id: 2, title: 'Super', value: 'super' },
        { id: 3, title: 'Puper', value: 'puper' },
        { id: 4, title: 'Cool', value: 'cool' },
        { id: 5, title: 'Like', value: 'like' }
      ],
      optionsSize: [
        { id: 1, title: 'Размер', value: 'size' },
        { id: 2, title: '29', value: '29' },
        { id: 3, title: '31', value: '31' },
        { id: 4, title: '35', value: '35' },
        { id: 5, title: '37', value: '37' },
        { id: 6, title: '42', value: '42' }
      ],
      optionsColor: [
        { id: 1, title: 'Цвет', value: 'color' },
        { id: 2, title: 'Синий', value: 'blue' },
        { id: 3, title: 'Красный', value: 'red' },
        { id: 4, title: 'Зеленый', value: 'green' },
        { id: 5, title: 'Белый', value: 'white' },
        { id: 6, title: 'Серый', value: 'gray' }
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
      filterBrand: 'brand',
      filterSize: 'size',
      filterColor: 'color'
    }
  },
  components: {
    Card, Select
  },
  methods: {
    filteredBrands () {
      // if (this.filter === 'brand') {
      //   return this.products
      // } else if (this.filter === 'super') {
      //   return this.products.filter(t => t.brand === 'super')
      // } else if (this.filter === 'puper') {
      //   return this.products.filter(t => t.brand === 'puper')
      // } else if (this.filter === 'cool') {
      //   return this.products.filter(t => t.brand === 'cool')
      // } else if (this.filter === 'like') {
      //   return this.products.filter(t => t.brand === 'like')
      // } else {
      //   return this.products
      // }
      return this.filterBrand
    },
    filteredSize () {
      // if (this.filter === 'size') {
      //   return this.products
      // } else if (this.filter === '29') {
      //   return this.products.filter(t => t.size === '29')
      // } else if (this.filter === '31') {
      //   return this.products.filter(t => t.size === '31')
      // } else if (this.filter === '35') {
      //   return this.products.filter(t => t.size === '35')
      // } else if (this.filter === '37') {
      //   return this.products.filter(t => t.size !== '37')
      // } else if (this.filter === '42') {
      //   return this.products.filter(t => t.size !== '42')
      // } else {
      //   return this.products
      // }
      return this.filterSize
    },
    filteredColor () {
      // if (this.filter === 'color') {
      //   return this.products
      // } else if (this.filter === 'blue') {
      //   return this.products.filter(t => t.color === 'синий')
      // } else if (this.filter === 'red') {
      //   return this.products.filter(t => t.color === 'красный')
      // } else if (this.filter === 'green') {
      //   return this.products.filter(t => t.color === 'зеленый')
      // } else if (this.filter === 'white') {
      //   return this.products.filter(t => t.color !== 'белый')
      // } else if (this.filter === 'gray') {
      //   return this.products.filter(t => t.color !== 'серый')
      // } else {
      //   return this.products
      // }
      return this.filterColor
    }
  },
  computed: {
    filtered () {
      // const selectBrand = this.filteredBrands()
      // const selectSize = this.filteredSize()
      // const selectColor = this.filteredColor()

      // let prod = this.products.filter(t => t.brand === 'super')
      // prod = prod.filter(t => t.size === '29')
      // prod = prod.filter(t => t.color === 'зелёный')

      if (this.filterBrand === 'brand') {
        return this.products.filter(t => t.brand === 'super' && t.size === +'31' && t.color === 'красный')
      }
      if (this.filterBrand === 'super') {
        return this.products.filter(t => t.brand === 'super' && t.size === +'31' && t.color === 'красный')
      }
      if (this.filterBrand === 'puper') {
        return this.products.filter(t => t.brand === 'super' && t.size === +'31' && t.color === 'красный')
      }
      if (this.filterBrand === 'cool') {
        return this.products.filter(t => t.brand === 'super' && t.size === +'31' && t.color === 'красный')
      }
      if (this.filterBrand === 'like') {
        return this.products.filter(t => t.brand === 'super' && t.size === +'31' && t.color === 'красный')
      }
      return this.products.filter(t => t.brand === 'super' && t.size === +'31' && t.color === 'красный')
      // products.filter(t => t.brand === 'super' && t.size === +'31' && t.color === 'красный')
      // return this.products.filter(t => t.brand === 'super').filter(t => t.size === '29')
    }
  }
}
</script>
