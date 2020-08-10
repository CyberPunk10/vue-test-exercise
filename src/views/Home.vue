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
                  />
                  <Select
                    v-bind:optionsSize="optionsSize"
                  />
                  <Select
                    v-bind:optionsColors="optionsColors"
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
          <Card />
        </div>
        <div class="col-6 pl-2">
          <Card />
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
      optionsColors: [
        { id: 1, title: 'Цвет' },
        { id: 2, title: 'Синий' },
        { id: 3, title: 'Красный' },
        { id: 4, title: 'Зеленый' },
        { id: 5, title: 'Белый' },
        { id: 6, title: 'Серый' }
      ]
    }
  },
  components: {
    Card, Select
  }
}
</script>
