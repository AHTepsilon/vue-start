<script>
  import ToDoList from "./components/ToDoList.vue"

  export default 
  {
    components: { ToDoList }
  }
</script>

<template>
  <header class="header">
    <h2>To Do List</h2>
  </header>

  <main>
    <ToDoList />
  </main>
</template>

<style scoped lang="scss">

$colorS: #034146;
$textColorHeader: #FFFFFF;

header {
  line-height: 1.5;
  background: $colorS;
  color: $textColorHeader;
  width: 100%;
  text-align: center;
  justify-content: center;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
