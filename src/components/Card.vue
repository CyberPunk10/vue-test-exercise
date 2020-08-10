<template>
  <div class="card text-center border-0 shadow-sm mb-3 bg-white rounded-lg">
    <img class="card-img-top"
        src="https://media.istockphoto.com/photos/red-womans-sports-jacket-picture-id520887025">
    <div class="card-body p-1 m-1">
        <h5 class="card-title mb-0">Название</h5>
        <div class="card-text">
            <div>
                <small class="card-text text-muted">
                    Категория
                </small>
            </div>
            <div>
                <del>5 900</del>
                <strong>3 790 ₽</strong>
            </div>
            <div class="alert alert-dark p-0 m-0" role="alert">
                <div>
                    <small>
                        <strong>Бренд</strong> Super
                    </small>
                </div>
                <div>
                    <small>
                        <strong>Размер</strong> 34
                    </small>
                </div>
                <div>
                    <small>
                        <strong>Цвет</strong> красный
                    </small>
                </div>
            </div>
        </div>
        <a href="#" class="btn btn-primary stretched-link m-1">Купить</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'card'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
