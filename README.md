<!doctype html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>NoXeon</title>

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Geologica&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Geologica:wght@800&display=swap');


        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {

            font-family: 'Geologica', sans-serif;
            font-weight: 200;
            color: #ffffff;
            background: #5663e4;
        }



        h1 {
            margin-top: 50px;
            margin-bottom: 10px;
        }

        img {
            width: 100px;
            margin: 10px ;
        }

        p {
            width: 350px;
            margin: 0 auto;
        }

        button {
            margin-top: 100px;
            font-family: 'Geologica', sans-serif;
            font-weight: 0;
            font-size: 14px;
            color: #ffffff;
            background-color: #5663e4;
            padding: 10px 30px;
            border: 2px solid #ffffff;
            box-shadow: rgb(0, 0, 0);
            border-radius: 50px;
            transition : 1000ms;
            flex-direction: row;
            align-items: center;
            cursor: pointer;

        }
        button:hover {
            transition : 1000ms;
            padding: 10px 50px;
            transform : translateY(-0px);
            background-color: #ffffff;
            color: #5663e4;
            border: solid 2px #5663e4;
        }

        #form {
            width: 100%;
            padding: 20px;
            text-align: center;
        }

        input {
            width: 90%;
            outline: none;
            margin: 10px 5%;
            padding: 15px 10px;
            font-size: 14px;
            border: 2px solid #ffffff;
            border-radius: 15px;
        }
        input:focus {
            border-color: #ffffff;
        }


    </style>
</head>
<body>




    <form id="form">

        <label for="name">ИeFer325geмя:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="message">Сообщение:</label>
        <textarea id="message" name="message" required></textarea>

        <button id="radr">Отправить</button>
    </form>

    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <script>

        let tg = window.Telegram.WebApp;
        let buy = document.getElementById("buy");
        let order = document.getElementById("radr");
        tg.expand();


        order.addEventListener("click", () => {
            let name = document.getElementById("text").value;
            let number = document.getElementById("email").value;
            let condition = document.getElementById("message").value;
            document.getElementById("error").innerText = '';

            if (name.length < 1) {
                document.getElementById("error").innerText = 'Ошибка в имени';
                return;
            }

            if (number.length < 10) {
                document.getElementById("error").innerText = 'Не хватает цифр в номере';
                return;
            }



            if (condition.length < 1) {
                document.getElementById("error").innerText = 'Ошибка в описании';
                return;
            }

            let data = {
                name: name,
                number: number,
                naming: naming,
                condition: condition

            }
            tg.sendData(JSON.stringify(data));

            tg.close();
        });

    </script>
</body>
</html>
