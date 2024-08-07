<!DOCTYPE html>
<html>
<head>
  <title>People Data Collection</title>
  <style>
    /* Add some basic styling to make the form look decent */
    form {
      width: 50%;
      margin: 40px auto;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    label {
      display: block;
      margin-bottom: 10px;
    }
    input[type="text"], input[type="email"] {
      width: 100%;
      height: 40px;
      margin-bottom: 20px;
      padding: 10px;
      border: 1px solid #ccc;
    }
    input[type="file"] {
      width: 100%;
      height: 40px;
      margin-bottom: 20px;
      padding: 10px;
      border: 1px solid #ccc;
    }
    input[type="submit"] {
      width: 100%;
      height: 40px;
      background-color: #4CAF50;
      color: #fff;
      padding: 10px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>People Data Collection</h1>
  <form id="people-form" enctype="multipart/form-data">
    <label for="firstName">First Name:</label>
    <input type="text" id="firstName" name="firstName" required>

    <label for="lastName">Last Name:</label>
    <input type="text" id="lastName" name="lastName" required>

    <label for="fatherName">Father's Name:</label>
    <input type="text" id="fatherName" name="fatherName" required>

    <label for="collegeUniversity">College/University:</label>
    <input type="text" id="collegeUniversity" name="collegeUniversity" required>

    <label for="degree">Degree:</label>
    <input type="text" id="degree" name="degree" required>

    <label for="branch">Branch:</label>
    <input type="text" id="branch" name="branch" required>

    <label for="passingYear">Passing Year:</label>
    <input type="text" id="passingYear" name="passingYear" required>

    <label for="aadharNumber">Aadhar Number:</label>
    <input type="text" id="aadharNumber" name="aadharNumber" required>

    <label for="collegeIdNumber">College Id Number:</label>
    <input type="text" id="collegeIdNumber" name="collegeIdNumber" required>

    <label for="collegeEmailId">College email Id:</label>
    <input type="email" id="collegeEmailId" name="collegeEmailId" required>

    <label for="resume">Upload Your Resume:</label>
    <input type="file" id="resume" name="resume" required>

    <input type="submit" value="Submit">
  </form>

  <script>
    // Add event listener to form submission
    document.getElementById('people-form').addEventListener('submit', (e) => {
      e.preventDefault();
      const formData = new FormData(e.target);
      fetch('/submit', {
        method: 'POST',
        body: formData,
      })
      .then((response) => response.json())
      .then((data) => console.log(data))
      .catch((error) => console.error(error));
    });
  </script>
</body>
</html>
