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
                                <div class="form-group">
                                    <select class="form-control">
                                        <option>Бренд</option>
                                        <option>Super</option>
                                        <option>Puper</option>
                                        <option>Cool</option>
                                        <option>Like</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <select class="form-control">
                                        <option>Размер</option>
                                        <option>29</option>
                                        <option>31</option>
                                        <option>35</option>
                                        <option>37</option>
                                        <option>42</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                  <Select
                                    v-bind:options="options"
                                  />
                                    <select class="form-control">
                                        <option>Цвет</option>
                                        <option>Синий</option>
                                        <option>Красный</option>
                                        <option>Зеленый</option>
                                        <option>Белый</option>
                                        <option>Серый</option>
                                    </select>
                                </div>
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
                <Card />>
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
      options: [
        { id: 1, title: 'Бренд' },
        { id: 2, title: 'Super' },
        { id: 3, title: 'Puper' },
        { id: 4, title: 'Cool' },
        { id: 5, title: 'Like' }
      ]
    }
  },
  components: {
    Card, Select
  }
}
</script>
