
<html>
<head>
    <title>ST Shade Conversion</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }
        img {
            width: 500px; /* Increased logo size */
            margin-bottom: 10px;
        }
        h1 {
            font-size: 24px;
        }
        h3 {
            font-size: 16px;
            color: gray;
        }
        input {
            margin: 5px;
            padding: 5px;
        }
        button {
            padding: 8px 12px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        p {
            font-weight: bold;
            margin-top: 15px;
        }
    </style>
</head>
<body>

    <!-- Corrected Company Logo Reference -->
    <img src="OPI.jpg" alt="Company Logo" onerror="this.onerror=null; this.src='default-logo.png';">

    <!-- Main Title and Subtitle -->
    <h1>ST Shade Conversion</h1>
    <h3>Please input all shades provided on the prescription.</h3>

    <!-- Shade Input Form -->
    <label>Incisal Shade (RX): <input type="text" id="incisal"></label><br>
    <label>Body/Mid Shade: <input type="text" id="body"></label><br>
    <label>Gingival Shade: <input type="text" id="gingival"></label><br>
    <button onclick="displayShade()">Submit</button>

    <!-- Output Section -->
    <p>Selected Shade: <span id="output"></span></p>

    <script>
        // ST Milling Shade Conversion (Vita Classic, 3D Master, Chromascope, Bleach)
        const shadeConversion = {
            // Vita Classic
            "A1": "A1", "A2": "A1", "A3": "A2", "A3.5": "A3", "A4": "A3.5",
            "B1": "B1", "B2": "B1", "B3": "B2", "B4": "B3",
            "C1": "C1", "C2": "C1", "C3": "C2", "C4": "C3",
            "D2": "B2", "D3": "A3", "D4": "A3",

            // Vita 3D Master
            "OM1": "OM1", "OM2": "OM2", "OM3": "OM3",
            "1M1": "B1", "1M2": "A1", "2L1.5": "A1", "2L2.5": "A2", "2M1": "A1", "2M2": "A1",
            "2M3": "A2", "2R1.5": "A1", "2R2.5": "A2", "3L1.5": "B2", "3L2.5": "A3",
            "3M1": "C1", "3M2": "B2", "3M3": "A3", "3R1.5": "B2", "3R2.5": "A3",
            "4L1.5": "C2", "4L2.5": "A3", "4M1": "B2", "4M2": "A3", "4M3": "A3.5",
            "4R1.5": "B2", "4R2.5": "A3.5", "5M1": "C2", "5M2": "A3.5", "5M3": "A3.5",

            // Bleach Shades
            "BL1": "OM1", "BL2": "OM1", "BL3": "OM2", "BL4": "OM3",

            // Chromascope
            "01/110": "A1", "1A/120": "A1", "2A/130": "A1", "1C/140": "A1",
            "2B/210": "A2", "1D/220": "A2", "1E/230": "A3", "2C/240": "A3",
            "3A/310": "B2", "5B/320": "B2", "2E/330": "B3", "3E/340": "A3.5",
            "4A/410": "B2", "6B/440": "B2", "4B/430": "C1", "6C/440": "C1",
            "6D/510": "C2", "4C/520": "C2", "3C/530": "A3.5", "4D/540": "A3.5"
        };

        function displayShade() {
            // Get input values
            let incisalShade = document.getElementById("incisal").value.trim().toUpperCase();
            let bodyShade = document.getElementById("body").value.trim().toUpperCase();
            let gingivalShade = document.getElementById("gingival").value.trim().toUpperCase();

            console.log("Input Incisal Shade:", incisalShade);
            console.log("Input Body Shade:", bodyShade);
            console.log("Input Gingival Shade:", gingivalShade);

            // Convert RX shades to Puck shades
            let convertedIncisal = shadeConversion[incisalShade] || (incisalShade !== "" ? incisalShade : "");
            let convertedBody = shadeConversion[bodyShade] || (bodyShade !== "" ? bodyShade : "");
            let convertedGingival = shadeConversion[gingivalShade] || (gingivalShade !== "" ? gingivalShade : "");

            console.log("Converted Incisal Shade:", convertedIncisal);
            console.log("Converted Body Shade:", convertedBody);
            console.log("Converted Gingival Shade:", convertedGingival);

            // Final shade logic:
            let finalShade;
            if (convertedIncisal !== "") {
                finalShade = convertedIncisal;  // Use converted incisal shade if available
            } else if (convertedBody !== "") {
                finalShade = convertedBody;  // If no incisal, use converted mid/body shade
            } else if (convertedGingival !== "") {
                finalShade = convertedGingival;  // If no incisal/mid, use converted gingival shade
            } else {
                finalShade = "No shade entered";  // If all are empty
            }

            console.log("Final Selected Shade:", finalShade);

            // Display the selected shade
            document.getElementById("output").innerText = finalShade;
        }
    </script>

</body>
</html>
