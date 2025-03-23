<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>حساب العمر</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 20px;
            background-color: #f9f9f9;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            margin: auto;
        }
        input {
            padding: 10px;
            width: 90%;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            padding: 10px 20px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>حاسبة العمر</h1>
        <label for="birthdate">أدخل تاريخ ميلادك:</label>
        <input type="date" id="birthdate">
        <button onclick="calculateAge()">احسب</button>
        <p id="result"></p>
    </div>

    <script>
        function calculateAge() {
            const birthdate = document.getElementById('birthdate').value;
            if (birthdate) {
                const birthDate = new Date(birthdate);
                const today = new Date();
                let age = today.getFullYear() - birthDate.getFullYear();
                const monthDiff = today.getMonth() - birthDate.getMonth();

                if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birthDate.getDate())) {
                    age--;
                }

                document.getElementById('result').textContent = `عمرك هو ${age} سنة.`;
            } else {
                document.getElementById('result').textContent = 'يرجى إدخال تاريخ الميلاد.';
            }
        }
    </script>
</body>
</html>
