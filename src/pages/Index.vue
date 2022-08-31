<template>
  <div class="q-pa-md">
    <q-table
      :dense="$q.screen.lt.md"
      class="my-sticky-header-column-table"
      title="Treats"
      :rows="rows"
      :columns="columns"
      row-key="name"
      :pagination="initialPagination"
    />
  </div>
</template>

<script>

const columns = [
  {
    name: 'name',
    required: true,
    label: 'Postre',
    align: 'left',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { name: 'Preparing-time', align: 'center', label: 'Tiempo de preparación (minutos)', field: 'time', sortable: true },
  { name: 'Recipe-yeald', align: 'center', label: 'Rendimiento (porciones)', field: 'yield', sortable: true },
  { name: 'link', align: 'center', label: 'Enlace a la receta', field: 'link' }  
]

const rows = [
  {
    name: 'Galletas de Chocolate con Chips de Chocolate Blanco',
    time: 30,
    yield: 0,
    link: 'https://www.gourmet.cl/recetas/galletas-chocolate-chips-chocolate/',
  },
  {
    name: 'Waffles con Chips de Chocolate y Salsa Fudge',
    time: 15,
    yield: 4,
    link: 'https://www.gourmet.cl/recetas/waffles-con-chips-de-chocolate-y-salsa-fudge/',
  },
  {
    name: 'Granola',
    time: 25,
    yield: 0,
    link: 'https://www.gourmet.cl/recetas/granola/',
  },
  {
    name: 'Leche Asada Vegana',
    time: 210,
    yield: 4,
    link: 'https://www.gourmet.cl/recetas/leche-asada-vegana/',
  },
  {
    name: 'Queque de Manzana',
    time: 80,
    yield: 10,
    link: 'https://www.gourmet.cl/recetas/queque-de-manzana/',
  },
 {
    name: 'Galletas Navideñas',
    time: 40,
    yield: 20,
    link: 'https://www.gourmet.cl/recetas/galletas-navidenas/',
  },
  {
    name: 'Queque de Chocolate',
    time: 80,
    yield: 8,
    link: 'https://www.gourmet.cl/recetas/queque-de-chocolate/',
  },
 {
    name: 'Budín de Pan',
    time: 90,
    yield: 10,
    link: 'https://www.gourmet.cl/recetas/budin-de-pan/',
  },
  {
    name: 'Rollos de Canela',
    time: 150,
    yield: 12,
    link: 'https://www.gourmet.cl/recetas/rollos-de-canela/',
  },
 {
    name: 'Cupcakes de Pie de Limón Decorados',
    time: 90,
    yield: 12,
    link: 'https://www.gourmet.cl/recetas/cupcakes-pie-limon-decorados/',
  },
]

export default {
  setup () {
    return {
      initialPagination: {
        sortBy: 'desc',
        descending: false,
        page: 2,
        rowsPerPage: 5
        // rowsNumber: xx if getting data from a server
      },

      columns,
      rows
    }
  }
}
</script>
<style lang="sass">
.my-sticky-header-column-table
  /* height or max-height is important */
  max-height: 425px

  /*margin*/
  margin: auto

  /* specifying max-width so the example can
    highlight the sticky column on any browser window */
  max-width: 1200px

  td:first-child
    /* bg color is important for td; just specify one */
    background-color: #c1f4cd !important

  tr th
    position: sticky
    /* higher than z-index for td below */
    z-index: 2
    /* bg color is important; just specify one */
    background: #fff

  /* this will be the loading indicator */
  thead tr:last-child th
    /* height of all previous header rows */
    top: 48px
    /* highest z-index */
    z-index: 3
  thead tr:first-child th
    top: 0
    z-index: 1
  tr:first-child th:first-child
    /* highest z-index */
    z-index: 3

  td:first-child
    z-index: 1

  td:first-child, th:first-child
    position: sticky
    left: 0
</style>