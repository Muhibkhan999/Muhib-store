<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CV Registration Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 80%;
            max-width: 800px;
        }
        h2 {
            margin-bottom: 20px;
            color: #333;
        }
        .section {
            margin-bottom: 20px;
        }
        .section-title {
            margin-bottom: 10px;
            font-weight: bold;
            color: #333;
        }
        label {
            display: block;
            margin: 10px 0 5px;
            color: #555;
        }
        input[type="text"], input[type="email"], input[type="password"], input[type="submit"], textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }
        input[type="submit"] {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background-color: #45a049;
        }
        .view-only {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 3px;
            background-color: #f9f9f9;
        }
        .button-container {
            text-align: center;
        }
        .button-container button {
            padding: 10px 20px;
            margin: 10px;
            border: none;
            border-radius: 3px;
            background-color: #4CAF50;
            color: white;
            cursor: pointer;
        }
        .button-container button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container" id="form-container">
        <h2>CV Registration Form</h2>
        <form id="cv-form">
            <div class="section">
                <div class="section-title">Personal Information</div>
                <label for="fname">First Name</label>
                <input type="text" id="fname" name="fname" required>

                <label for="lname">Last Name</label>
                <input type="text" id="lname" name="lname" required>

                <label for="email">Email</label>
                <input type="email" id="email" name="email" required>

                <label for="phone">Phone Number</label>
                <input type="text" id="phone" name="phone" required>
            </div>

            <div class="section">
                <div class="section-title">Education</div>
                <label for="education">Education Details</label>
                <textarea id="education" name="education" rows="4" required></textarea>
            </div>

            <div class="section">
                <div class="section-title">Work Experience</div>
                <label for="experience">Work Experience Details</label>
                <textarea id="experience" name="experience" rows="4" required></textarea>
            </div>

            <div class="section">
                <div class="section-title">Skills</div>
                <label for="skills">Skills</label>
                <textarea id="skills" name="skills" rows="4" required></textarea>
            </div>

            <input type="submit" value="Register">
        </form>
    </div>

    <div class="container" id="details-container" style="display: none;">
        <h2>CV Details</h2>
        <div class="section">
            <div class="section-title">Personal Information</div>
            <div class="view-only" id="view-fname"></div>
            <div class="view-only" id="view-lname"></div>
            <div class="view-only" id="view-email"></div>
            <div class="view-only" id="view-phone"></div>
        </div>

        <div class="section">
            <div class="section-title">Education</div>
            <div class="view-only" id="view-education"></div>
        </div>

        <div class="section">
            <div class="section-title">Work Experience</div>
            <div class="view-only" id="view-experience"></div>
        </div>

        <div class="section">
            <div class="section-title">Skills</div>
            <div class="view-only" id="view-skills"></div>
        </div>

        <div class="button-container">
            <button onclick="goHome()">Go Home</button>
            <button onclick="showMap()">Map</button>
        </div>
    </div>

    <div class="container" id="map-container" style="display: none;">
        <h2>Google Map</h2>
        <div class="button-container">
            <button onclick="goHome()">Go Home</button>
        </div>
        <iframe 
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d243648.97872959364!2d-74.01101629999999!3d40.7127753!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c24fa5d33f083b%3A0x93986f73d4ef4f39!2sNew+York%2C+NY%2C+USA!5e0!3m2!1sen!2s!4v1494239733173" 
            width="100%" height="450" frameborder="0" style="border:0" allowfullscreen aria-hidden="false" tabindex="0">
        </iframe>
    </div>

    <script>
        document.getElementById('cv-form').addEventListener('submit', function(event) {
            event.preventDefault();
            document.getElementById('form-container').style.display = 'none';
            document.getElementById('details-container').style.display = 'block';

            document.getElementById('view-fname').innerText = 'First Name: ' + document.getElementById('fname').value;
            document.getElementById('view-lname').innerText = 'Last Name: ' + document.getElementById('lname').value;
            document.getElementById('view-email').innerText = 'Email: ' + document.getElementById('email').value;
            document.getElementById('view-phone').innerText = 'Phone Number: ' + document.getElementById('phone').value;
            document.getElementById('view-education').innerText = 'Education Details: ' + document.getElementById('education').value;
            document.getElementById('view-experience').innerText = 'Work Experience Details: ' + document.getElementById('experience').value;
            document.getElementById('view-skills').innerText = 'Skills: ' + document.getElementById('skills').value;
        });

        function goHome() {
            document.getElementById('form-container').style.display = 'block';
            document.getElementById('details-container').style.display = 'none';
            document.getElementById('map-container').style.display = 'none';
            document.getElementById('cv-form').reset();
        }

        function showMap() {
            document.getElementById('details-container').style.display = 'none';
            document.getElementById('map-container').style.display = 'block';
        }
        
    </script>
</body>
</html>
