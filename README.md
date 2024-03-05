Name: Eli Baniba
Index Number: INT/22/01/0433
Supplementary Mid-Semester Exam Questions
Planning and designing a simple web application to validate a registration form with 
username, email, and password.
Answers
(A.i). <!DOCTYPE html>
 <html lang="en">
 <head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
(A.ii). <title>Form Validator</title>
(A.iii). <script src="script.js" defer></script>
 </head>
 <body>
(B.i). <form id="registrationForm" onsubmit="return validateForm()">
 <label for="username">Username:</label>
(B.ii). <input type="text" id="username" name="username" required>
 <label for="email">Email:</label>
(B.iii). <input type="email" id="email" name="email" required>
(B.iv). <label for="password">Password:</label>
 <input type="password" id="password" name="password" required>
(B.v). <input type="submit" value="Submit">
 </form>
 </body>
 </html>
The JavaScript Section
function validateForm() {
// (C.i) Getting relevant elements
var usernameInput = document.getElementById("username");
var emailInput = document.getElementById("email");
var passwordInput = document.getElementById("password");
// (C.ii) Validating username to be at least 3 characters long
if (usernameInput.value.length < 3) {
alert("Username must be at least three characters long.");
return false;
}
// (C.iii) Validating email using a simple pattern
var emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
if (!emailPattern.test(emailInput.value)) {
alert("Invalid email address.");
return false;
}
// (C.iv) Validating password length to be at least 6 characters long
if (passwordInput.value.length < 6) {
alert("Password must be at least six characters long.");
return false;
}
// (C.v) If all validations pass, submit the form
return true;
}
