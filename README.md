<html>
<head>
    <style>
        button {
            position: relative;
            background-color: #4CAF50;
            border: none;
            font-size: 28px;
            color: #FFFFFF;
            padding: 20px;
            width: 200px;
            text-align: center;
            -webkit-transition-duration: 0.4s;
            /* Safari */
            transition-duration: 0.4s;
            text-decoration: none;
            overflow: hidden;
            cursor: pointer;
        }
        
        button:after {
            content: "";
            background: #90EE90;
            display: block;
            position: absolute;
            padding-top: 300%;
            padding-left: 350%;
            margin-left: -20px!important;
            margin-top: -120%;
            opacity: 0;
            transition: all 0.8s
        }
        
        button:active:after {
            padding: 0;
            margin: 0;
            opacity: 1;
            transition: 0s
        }
    </style>
</head>

<body bgcolor="#DAF7A6">
    <center>
        <p><strong>Click the button to get your coordinates.</strong></p>

        <button onclick="getLocation()">Try It</button>
    </center>


    <p id="demo"></p>

    <script>
        var x = document.getElementById("demo");

        function getLocation() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(showPosition);
            } else {
                x.innerHTML = "Geolocation is not supported by this browser.";
            }
        }

        function showPosition(position) {
            x.innerHTML = "Latitude: " + position.coords.latitude +
                "<br>Longitude: " +
