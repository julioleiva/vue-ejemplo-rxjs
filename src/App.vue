<template>
  <div id="app">
    <div class="jumbotron">
     <p> <span class="label label-success">Contador: {{ count }}</span></p>
    </div>
  </div>
</template>

<script>
  import { Observable } from 'rxjs/Observable'
  import 'rxjs/add/observable/interval'
  import 'rxjs/add/operator/filter'

  export default {
    name: 'app',
    subscriptions () {
        return {
            count: Observable.interval(1000)
                .filter((value) => value % 2 == 0)
        }
      },

  }
</script>

<style>

</style>
