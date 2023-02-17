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
        box-shadow: inset 0 0 0 0 #bebebe;
        color: #b4b4b4;
        margin: 0 -.25rem;
        padding: 0 .25rem;
        transition: color .5s ease-in-out, box-shadow .3s ease-in-out;
        text-decoration: none;
        font-size: 25px;
    }

    a:hover {
        box-shadow: inset 0 0 0 20px #bebebe;
        color: white;
    }
</style>