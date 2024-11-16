# Sri-Krishna-home-Tutions-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sri Krishna Home Tuitions</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
      color: #333;
    }
    header {
      background-color: #4CAF50;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    .container {
      max-width: 800px;
      margin: 20px auto;
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
    }
    label {
      display: block;
      margin: 10px 0 5px;
      font-weight: bold;
    }
    input, select, textarea {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      background-color: #4CAF50;
      color: white;
      padding: 10px 15px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
    }
    button:hover {
      background-color: #45a049;
    }
    .section-title {
      margin-top: 20px;
      font-size: 1.2em;
      font-weight: bold;
    }
    .input-group {
      margin-bottom: 20px;
      border: 1px solid #ddd;
      padding: 10px;
      border-radius: 5px;
      background: #f9f9f9;
    }
    .remove-btn {
      background-color: #e74c3c;
      color: white;
      padding: 5px 10px;
      margin-top: 10px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .remove-btn:hover {
      background-color: #c0392b;
    }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <header>
    <h1>Sri Krishna Home Tuitions</h1>
  </header>
  <div class="container">
    <h2>Tuition Management</h2>

    <!-- Section for Tutors -->
    <div id="tutors-section">
      <div class="section-title">Tutor Details</div>
      <button type="button" onclick="addTutor()">Add Tutor</button>
    </div>

    <!-- Section for Students -->
    <div id="students-section">
      <div class="section-title">Student Details</div>
      <button type="button" onclick="addStudent()">Add Student</button>
    </div>

    <button type="submit" style="margin-top: 20px;">Submit All Details</button>
  </div>

  <script>
    // Add Tutor Details
    function addTutor() {
      const tutorsSection = document.getElementById('tutors-section');
      const div = document.createElement('div');
      div.classList.add('input-group');
      div.innerHTML = `
        <label for="tutor-name">Tutor Name:</label>
        <input type="text" name="tutor-name" placeholder="Enter tutor's name" required>
        <label for="gender">Gender:</label>
        <select name="gender">
          <option value="male">Male</option>
          <option value="female">Female</option>
          <option value="other">Other</option>
        </select>
        <label for="subject">Subject:</label>
        <input type="text" name="subject" placeholder="Enter subject" required>
        <label for="experience">Experience (in years):</label>
        <input type="number" name="experience" placeholder="Enter years of experience" required>
        <label for="location">Location:</label>
        <button type="button" onclick="getLocation(this)">Select Location</button>
        <input type="text" name="location" class="hidden" placeholder="Google Maps Link">
        <button type="button" class="remove-btn" onclick="this.parentElement.remove()">Remove</button>
      `;
      tutorsSection.appendChild(div);
    }

    // Add Student Details
    function addStudent() {
      const studentsSection = document.getElementById('students-section');
      const div = document.createElement('div');
      div.classList.add('input-group');
      div.innerHTML = `
        <label for="student-class">Class:</label>
        <input type="text" name="student-class" placeholder="Enter class (e.g., 10th)" required>
        <label for="gender">Gender:</label>
        <select name="gender">
          <option value="male">Male</option>
          <option value="female">Female</option>
          <option value="other">Other</option>
        </select>
        <label for="student-subject">Subject:</label>
        <input type="text" name="student-subject" placeholder="Enter subject" required>
        <label for="syllabus">Syllabus:</label>
        <input type="text" name="syllabus" placeholder="Enter syllabus (e.g., ICSE, CBSE)" required>
        <label for="location">Location:</label>
        <button type="button" onclick="getLocation(this)">Select Location</button>
        <input type="text" name="location" class="hidden" placeholder="Google Maps Link">
        <button type="button" class="remove-btn" onclick="this.parentElement.remove()">Remove</button>
      `;
      studentsSection.appendChild(div);
    }

    // Function to Get Location from Google Maps
    function getLocation(button) {
      const url = prompt("Paste Google Maps link or location here:");
      const inputField = button.nextElementSibling;
      inputField.classList.remove("hidden");
      inputField.value = url || "Location not provided";
    }
  </script>
</body>
</html>