<html>

<head>
    <meta charset="UTF-8">
    <title> Roman to Decimal Converter </title>
    <style>
        body {
            font-family: Helvetica;
            background-color: #bfacb5;
        }

        #page {
            width: 900px;
            height: 100vh;
            margin: auto;
            background-color: white;
            align-items: center;
            position: relative;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 3rem;
            position: absolute;
            top: 25%;
        }

        section {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        h2 {
            font-size: 20pt;
        }

        button {
            width: 30%;
            border: 2px solid #202020;
            border-radius: 2cm;
            padding: 10px;
            cursor: pointer;
            margin: 12px;
            align-self: center;
        }
        input {
            padding: 12px;
            width: 100%;
            font-size: 15px;
        }
        #demo {
            font-size: 20px;
        }
        footer {
            display: flex;
            position: absolute;
            bottom: 0;
            right: 0;
        }
    </style>
</head>

<script>

    function RomToDec(roman) {
        roman = document.getElementById("roman").value;
        var Roman = ['I', 'V', 'X', 'L', 'C', 'D', 'M'];
        var Decimal = [1, 5, 10, 50, 100, 500, 1000];
        var answer = 0;
        roman = roman.toUpperCase();
        roman = roman.split('');
        var length = roman.length;

        for (var i = 0; i < length; i++) {
            if (Decimal[Roman.indexOf(roman[i])] < Decimal[Roman.indexOf(roman[i + 1])]) {
                answer += Decimal[Roman.indexOf(roman[i + 1])] - Decimal[Roman.indexOf(roman[i])];
                i++;
            } else { answer += Decimal[Roman.indexOf(roman[i])] }
        }
        return answer
    }

    function myFunction() {
        document.getElementById("demo").innerHTML = RomToDec(roman);
    }
</script>

<body>
    <div id="page">
        <section>
            <div class="content">
                <h2> Roman to Decimal Number </h2>

                <p> Please Enter Your <strong><em> Roman </em></strong> Number Below </p>

                <input type="text" id="roman" placeholder="Roman Number e.g. MCDXII"> <button onclick="myFunction()">
                    Convert </button>

                <p id="demo"> <em>Answer Prints Here</em> </p>
            </div>
        </section>

        <footer>
            <p> Kennedy O. </p>
        </footer>
    </div>
</body>

</html>
