<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Management</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            flex-direction: column;
        }
        table {
            width: 60%;
            border-collapse: collapse;
            background-color: #ffffff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            overflow: hidden;
        }
        th, td {
            border: 1px solid black;
            padding: 12px;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        tr:nth-child(odd) {
            background-color: #e6f7ff;
        }
        button {
            background-color: rgb(0, 166, 255);
            color: white;
            border: none;
            padding: 5px;
            cursor: pointer;
            border-radius: 4px;
        }
        button:hover {
            background-color: darkred;
        }
    </style>
</head>
<body>

    <h2>Student Management System</h2>
    <table id="studentTable">
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
                <th>Course</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody id="studentBody">
        </tbody>
    </table>

    <script>
        let students = [
            { name: "Avanish", age: 15, course: "Computer Science" },
            { name: "Devi", age: 10, course: "Mathematics" },
            { name: "Sandeep", age: 2, course: "Physics" }
        ];

        function displayStudents() {
            let tableBody = document.getElementById("studentBody");
            tableBody.innerHTML = ""; 
            
            for (let i = 0; i < students.length; i++) {
                let row = document.createElement("tr");
                row.innerHTML = `
                    <td>${students[i].name}</td>
                    <td>${students[i].age}</td>
                    <td>${students[i].course}</td>
                    <td><button onclick="removeStudent(${i})">Remove</button></td>
                `;
                tableBody.appendChild(row);
            }
        }

        function removeStudent(index) {
            students.splice(index, 1);
            displayStudents();
        }

        displayStudents(); 
    </script>

</body>
</html>
