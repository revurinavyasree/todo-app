<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My To-Do App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
    }

    input {
      padding: 8px;
      width: 200px;
    }

    button {
      padding: 8px 12px;
    }

    ul {
      margin-top: 20px;
      padding-left: 0;
    }

    li {
      list-style: none;
      margin: 5px 0;
      cursor: pointer;
    }

    li.done {
      text-decoration: line-through;
      color: gray;
    }
  </style>
</head>
<body>
  <h2>My To-Do List</h2>
  <input type="text" id="taskInput" placeholder="Add a new task">
  <button id="addBtn">Add</button>

  <ul id="taskList"></ul>

  <script>
    const input = document.getElementById('taskInput');
    const addBtn = document.getElementById('addBtn');
    const list = document.getElementById('taskList');

    addBtn.addEventListener('click', () => {
      const task = input.value.trim();
      if (task === '') return;

      const li = document.createElement('li');
      li.textContent = task;

      li.addEventListener('click', () => {
        li.classList.toggle('done');
      });

      list.appendChild(li);
      input.value = '';
    });
  </script>
</body>
</html>
