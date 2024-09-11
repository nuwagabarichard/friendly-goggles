# friendly-goggles
<!DOCTYPE html>
<html lang="en">
<head>
 
    <title>To-Do List</title>
   <style>
    body {
    font-family: Arial, sans-serif;
    background-color: green;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.app-container {
    background-color: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    width: 300px;
}

h1 {
    text-align: center;
    color: red;
}

.input-container {
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}

input[type="text"] {
    width: 80%;
    padding: 10px;
    border: 1px solid pink;
    border-radius: 5px;
    font-size: 16px;
}

button {
    padding: 10px;
    background-color:skyblue;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    background-color: yellow;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    padding: 10px;
    background-color: blue;
    border: 1px solid pink;
    border-radius: 5px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

li.completed {
    text-decoration: line-through;
    color:blue;
}

button.delete-btn {
    background-color: green;
}

button.delete-btn:hover {
    background-color: red;
}   
       
   </style>
</head>
<body>
    <div class="app-container">
        <h1>To-Do List</h1>
        <div class="input-container">
            <input type="text" id="task-input" placeholder="Add a new task...">
            <button id="add-task-btn">Add</button>
        </div>
        <ul id="task-list"></ul>
    </div>

    <script>
        const taskInput = document.getElementById('task-input');
const addTaskBtn = document.getElementById('add-task-btn');
const taskList = document.getElementById('task-list');


function addTask() {
    const taskText = taskInput.value;

    if (taskText === '') return; 

    
    const li = document.createElement('li');
    li.textContent = taskText;

    
    const deleteBtn = document.createElement('button');
    deleteBtn.textContent = 'Delete';

    
    deleteBtn.onclick = function() {
        li.remove();
    };

    
    li.onclick = function() {
        li.classList.toggle('completed');
    };

    
    li.appendChild(deleteBtn);
    taskList.appendChild(li);

    
    taskInput.value = '';
}


addTaskBtn.onclick = addTask;


taskInput.onkeypress = function(e) {
    if (e.key === 'Enter') addTask();
};
        
        
        
    </script>
</body>
</html>
