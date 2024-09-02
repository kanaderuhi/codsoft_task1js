# codsoft_task1js
 <!DOCTYPE html>
<html>
    <head>
        <title>To-Do List</title>
        <style>
            .input
            {
                font-size: 30px;
            }
            .task-checkbox {
                margin-right: 100px;
            }
            
            .task-checkbox input[type="checkbox"] {
                width: 20px;
                height: 20px;
                margin: 0;
                vertical-align: middle;
            }
            
            body {
                font-family: cursive, sans-serif;
                background-color: #aea1e6; 
                color: cadetblue;
            }
            
            #task-list {
                list-style: none;
                padding: 0;
                margin: 0;
            }
            
            #task-list li {
                padding: 10px;
                border-bottom: 1px solid #ccc;
                background-color: #fff; 
                box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); 
            }
            
            #task-list li:last-child {
                border-bottom: none;
            }
            
            .close {
                color: #red;
                cursor: pointer;
                font-size: 50px;
                font-weight: bold; 
            }
            
            #task-list li span {
                font-size: 25px; 
                color: #d02806; 
            }
            
            
        </style>
 
    </head>
    <body>
        <h1 id="title">To-Do List</h1>
         <input id="new-task" type="text" size="60px" placeholder="Enter new task">
         <button id="add-task">Add Task</button>
         <ul id="task-list"></ul>
        <script>
            let taskList = document.getElementById("task-list");
            let newTaskInput = document.getElementById("new-task");
            let addTaskButton = document.getElementById("add-task");
            

            addTaskButton.addEventListener("click", addTask);

            function addTask() {
            let newTask = newTaskInput.value.trim();
                if (newTask) {
                    let taskListItem = document.createElement("li");
                    taskListItem.textContent = newTask;
                    taskList.appendChild(taskListItem);
                    newTaskInput.value = "";
                    createCloseButton(taskListItem);
                }
            }

            function createCloseButton(taskListItem) {
                let closeButton = document.createElement("span");
                closeButton.textContent = "              ×";
                closeButton.className = "close";
                taskListItem.appendChild(closeButton);
                closeButton.addEventListener("click", deleteTask);
              }
              
              function createCheckbox(taskListItem) {
                let checkbox = document.createElement("input");
                checkbox.type = "checkbox";
                checkbox.className = "task-checkbox";
                taskListItem.appendChild(checkbox);
              }

            
            function deleteTask(event) {
            let taskListItem = event.target.parentNode;
            taskList.removeChild(taskListItem);
            }                                                                                                                   
        </script>
    </body>
</html>
