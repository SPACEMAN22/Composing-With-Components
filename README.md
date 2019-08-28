# Composing-With-Components
HTML

<html>
    <head>
        <link rel="stylesheet" href="index.css">
        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    </head>
    <body>
    
        <div id="app">
            <ol>
                <todo-item
                    v-for="item in game"
                    v-bind:todo="item"
                    v-bind:key="item.id">
               </todo-item>
            </ol>
        </div>
        
        <script src="index.js"></script>
    </body>
</html>

JavaScript/Vue

Vue.component('todo-item', {
    props: ['todo'],
    template: '<li>{{ todo.text }}</li>'
})

var app = new Vue({
    el: '#app',
    data: {
      game: [
        { id: 0, text: 'Sword' },
        { id: 1, text: 'Shield' },
        { id: 2, text: 'Magic Staff' }
      ]
    }
})
