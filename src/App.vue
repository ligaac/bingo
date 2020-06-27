<template>
  <div id="app">
    <h1>Bingo</h1>
    <section class="bingo-grid">
      <bingo-item 
        v-for="item of bingo"
        :key="item.id"
        :id="item.id"
        :label="item.label"
        :marked="item.marked"
        @mark="mark(item.id)"
      ></bingo-item>
    </section>
  </div>
</template>

<script>
import BingoItem from './components/BingoItem'

export default {
  name: 'App',
  components: {
    BingoItem
  },
  data() {
    return {
      bingo: [
        { label: 'la multi ani liga ac', id: 1, marked: false },
        { label: 'Nopți nedormite', id: 2, marked: false },
        { label: 'Upara', id: 3, marked: false },
        { label: 'Cineva se emoționează', id: 4, marked: false },
        { label: 'Ședințe până dimineața', id: 5, marked: false },
        { label: 'liga ac este o familie', id: 6, marked: false },
        { label: 'nu m-am gândit ce sa zic', id: 7, marked: false },
        { label: 'să ne vedem la un ceai', id: 8, marked: false },
        { label: 'la multi ani liga ac', id: 9, marked: false },
      ]
    }
  },
  methods: {
    mark(id) {
      this.bingo.forEach(item => {
        if(item.id === id) item.marked = true
      })
    }
  }
}
</script>

<style>
.bingo-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  column-gap: 1em;
}
</style>
