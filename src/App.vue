<script>
import TodoList from './components/Todo/TodoList.vue';
import TodoList2 from './components/Todo/TodoList2.vue';

const routes = {
    '/': TodoList,
    '/todo2': TodoList2
}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
        currentView() {
            return routes[this.currentPath.slice(1) || '/'] || NotFound
        }
    },
    mounted() {
        window.addEventListener('hashchange', () => {
		    this.currentPath = window.location.hash
		})
    }
}
</script>

<template>
    <div class="navbar">
        <a href="#/">TodoList1</a>
        <a href="#/todo2">TodoList2</a>
    </div>
    <component :is="currentView" />
</template>

<style scoped>
    .navbar {
        background-color: rgb(63, 63, 63);
        opacity: 0.5;
        display: flex;
        justify-content: space-evenly;
        align-items: center;

    }

    a {
        color: rgb(180, 180, 180);
        font-size: 25px;
        text-decoration: none;
        transition: font-size 0.25s;
    }

    a:hover {
        color: rgb(255, 255, 255);
        font-size: 27px;
    }
</style>