<script>
  import Todo from './Todo.svelte';

  let lastId = 0;

  const createTodo = (text, done = false) => ({id: ++lastId, text, done});

  let todoText = '';

  let todos = [
    createTodo('learn Svelte', true),
    createTodo('build a svelte app')
  ];

  $: uncompletedCount = todos.filter(t => !t.done).length;

  $: status = `${uncompletedCount} of ${todos.length} remaining`;

  function addTodo() {
    todos = todos.concat(createTodo(todoText));
    // 입력값 초기화
    todoText = '';
  }

  function archiveCompleted() {
    // 완료되지 않은 상태의 todo만 보관.
    todos = todos.filter(t => !t.done);
  }

  function deleteTodo(todoId) {
    todos = todos.filter(t => t.id !== todoId);
  }

  function toggleDone(todo) {
    const {id} = todo;
    todos = todos.map(t => (t.id === id ? {...t, done: !t.done} : t));
  }
</script>

<div class="component-split">
  <h1>To Do List</h1>
  <div>
    {status}
    <button on:click={archiveCompleted}>Archive Completed</button>
  </div>
  <form on:submit|preventDefault>
    <input size="30" placeholder="enter new todo here" bind:value={todoText} />
    <button disabled={!todoText} on:click={addTodo}>Add</button>
  </form>
  <ul>
    {#each todos as todo}
      <Todo
        {todo}
        on:delete={() => deleteTodo(todo.id)}
        on:toggleDone={() => toggleDone(todo)}
      />
    {/each}
  </ul>
</div>

<style>
  button {
    margin-left: 10px;
  }

  ul {
    list-style: none;
    margin-left: 0;
    padding-left: 0;
  }
</style>
