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

        #main {
            width: 100%;
            padding: 20px;
            text-align: center;
        }

        h1 {

            margin-top: 50px;
            margin-bottom: 10px;
        }

        img {
            width: 70px;
            margin: 30px auto;
        }

        p {
            width: 350px;
            margin: 0 auto;
        }

        button {
            margin-top: 50px;
            font-family: 'Geologica', sans-serif;
            font-weight: 0;
            font-size: 14px;
            color: #ffffff;
            background-color: #5663e4;
            padding: 10px 30px;
            border: 2px solid #ffffff;
            box-shadow: rgb(0, 0, 0) 0px 0px 0px 0px;
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
            display: none;
            text-align:center;
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
    <div id="main">
        <h1>Онлайн магазин</h1>
        <img src="https://sun9-39.userapi.com/impg/JVKAa35goFgG2KeIMpCZZHr_CLpnijExe-RoRg/UKUmxJEu-rs.jpg?size=785x589&quality=96&sign=0a8c205bcc92ef35a6cbd1cd53cac38f&c_uniq_tag=bOLNMFDxhPdUCZiD4FxoTgTaYcXS_9RKHM2EpNtinlM&type=album">
        <p>Lorem ipsum</p>
        <button id="buy">Купить</button>
    </div>
    <form id="form">
        <input type="text" placeholder="Имя" id="user_name">
        <input type="text" placeholder="Телефон" id="user_number">
        <input type="text" placeholder="Название комплектующего" id="user_naming">
        <input type="text" placeholder="Состояние комплектующего" id="user_condition">
        <div id="error"></div>
        <button id="order">Оформить</button>

    </form>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <script>
        let tg = window.Telegram.WebApp;
        let buy = document.getElementById("buy");
        let order = document.getElementById("order");
        tg.expand();

        buy.addEventListener("click", ()=> {

            document.getElementById("main").style.display = 'none';
            document.getElementById("form").style.display = 'block';

        });

        order.addEventListener('click', () => {
            let name = document.getElementById("user_name").value;
            let number = document.getElementById("user_number").value;
            let naming = document.getElementById("user_naming").value;
            let condition = document.getElementById("user_condition").value;

            if(name.length < 1) {
                document.getElementById("error").innerText = "Ошибка в имени";
                return;
            }

            if (number.length < 10) {
                document.getElementById("error").innerText = "Не хватает цифр в номере";
                return;
            }

            if (naming.length < 1) {
                document.getElementById("error").innerText = "Ошибка в названии";
                return;
                }

            if (condition.length < 1) {
                document.getElementById("error").innerText = "Ошибка в описании";
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
