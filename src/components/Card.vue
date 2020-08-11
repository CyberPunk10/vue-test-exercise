<template>
  <div>
    <div class="card text-center border-0 shadow-sm mb-3 bg-white rounded-lg"
         v-for="product in products" :key="product.id"
    >
      <img class="card-img-top" v-bind:src="product.img">
      <div class="card-body p-1 m-1">
          <h5 class="card-title mb-0">{{ product.name }}</h5>
          <div class="card-text">
            <div>
              <small class="card-text text-muted">
                {{ product.category }}
              </small>
            </div>
            <div>
              <del>{{ product.oldPrice }}</del>
              <strong>{{ product.price }} ₽</strong>
            </div>
            <div class="alert alert-dark p-0 m-0" role="alert">
              <div>
                <small>
                  <strong>Бренд</strong> {{ product.brand }}
                </small>
              </div>
              <div>
                <small>
                  <strong>Размер</strong> {{ product.size }}
                </small>
              </div>
              <div>
                <small>
                  <strong>Цвет</strong> {{ product.color }}
                </small>
              </div>
            </div>
          </div>
          <a href="#" class="btn btn-primary stretched-link m-1">Купить</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'card',
  props: [
    'products'
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">

</style>
