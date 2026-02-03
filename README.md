<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Team To-Do App</title>

<style>
     {
        box-sizing: border-box;
        font-family: 'Segoe UI', sans-serif;
    }

    body {
        background: linear-gradient(135deg, #667eea, #764ba2);
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .container {
        background: #fff;
        width: 350px;
        padding: 20px;
        border-radius: 12px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }

    h1 {
        text-align: center;
        margin-bottom: 15px;
        color: #333;
    }

    .input-box {
        display: flex;
        gap: 10px;
    }

    input {
        flex: 1;
        padding: 8px;
        border-radius: 6px;
        border: 1px solid #ccc;
        outline: none;
    }

    button {
        background: #667eea;
        color: white;
        border: none;
        padding: 8px 12px;
        border-radius: 6px;
        cursor: pointer;
    }

    button:hover {
        background: #5a67d8;
    }

    ul {
        list-style: none;
        padding: 0;
        margin-top: 15px;
    }

    li {
        background: #f4f4f4;
        padding: 8px;
        margin-bottom: 8px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        border-radius: 6px;
    }

    li.completed {
        text-decoration: line-through;
        color: gray;
    }

    .delete {
        background: red;
        border: none;
        color: white;
        border-radius: 4px;
        padding: 4px 6px;
        cursor: pointer;
    }
</style>
</head>

<body>

<div class="container">
    <h1>📝 Team To-Do List</h1>

    <div class="input-box">
        <input type="text" id="taskInput" placeholder="Enter task...">
        <button onclick="addTask()">Add</button>
    </div>

    <ul id="taskList"></ul>
</div>

<script>
function addTask() {
    let input = document.getElementById("taskInput");
    let taskText = input.value.trim();

    if (taskText === "") {
        alert("Please enter a task");
        return;
    }

    let li = document.createElement("li");
    li.innerHTML = `
        <span onclick="toggleTask(this)">${taskText}</span>
        <button class="delete" onclick="deleteTask(this)">X</button>
    ;

    document.getElementById("taskList").appendChild(li);
    input.value = "";
}

function deleteTask(btn) {
    btn.parentElement.remove();
}

function toggleTask(task) {
    task.parentElement.classList.toggle("completed");
}
</script>

</body>
</html>

