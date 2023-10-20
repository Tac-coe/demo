data entry
<html>
<head>
    <title>Data Entry Form</title>
</head>
<body>
    <form id="dataForm">
        <label for="psName">PS NAME:</label>
        <input type="text" id="psName" name="psName"><br>

        <label for="io">I.O:</label>
        <input type="text" id="io" name="io"><br>

        <label for="phoneNumber">PHONE NUMBER:</label>
        <input type="text" id="phoneNumber" name="phoneNumber"><br>

        <label for="location">LOCATION:</label>
        <input type="text" id="location" name="location"><br>

        <label for="amount">AMOUNT:</label>
        <input type="text" id="amount" name="amount"><br>

        <label for="seizedVehicles">SEIZED VEHICLES:</label>
        <input type="text" id="seizedVehicles" name="seizedVehicles"><br>

        <input type="submit" value="Submit">
    </form>

    <script>
        document.getElementById("dataForm").addEventListener("submit", function(event) {
            event.preventDefault();
            var formData = new FormData(event.target);
            var url = "YOUR_WEB_APP_URL"; // Replace with your web app URL

            fetch(url, {
                method: "POST",
                body: formData
            })
            .then(function(response) {
                return response.text();
            })
            .then(function(data) {
                alert(data);
            });
        });
    </script>
</body>
</html>
