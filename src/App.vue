<template>
  <div id="app" class="container mx-auto">
    <div class="py-16">
      <h1 class="text-4xl font-bold text-red-600">Bingo Aniversare Liga AC!</h1>
      <p>Reguli: Trimite screenshot pe <a class="font-bold underline" href="https://www.facebook.com/groups/ligaac/">grupul de Facebook</a> când ai marcat 3 în linie/diagonală.</p>
    </div>
    <section class="grid grid-cols-3 col-gap-4 row-gap-4">
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
        { label: 'La multi ani Liga AC!', id: 1, marked: false },
        { label: 'Nopți nedormite', id: 2, marked: false },
        { label: 'Upară', id: 3, marked: false },
        { label: 'Cineva se emoționează', id: 4, marked: false },
        { label: 'Ședințe până dimineața', id: 5, marked: false },
        { label: 'Liga AC este o familie!', id: 6, marked: false },
        { label: 'Nu m-am gândit ce sa zic...', id: 7, marked: false },
        { label: 'Să ne vedem la ceai!', id: 8, marked: false },
        { label: 'Se face mișto de Ciobo', id: 9, marked: false },
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
