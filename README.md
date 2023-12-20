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
        <img src="https://sun4-20.userapi.com/s/v1/ig2/OGbkLIUzLzPZz151ZZK04U0dBpZ13ivrw-NHWC59ULlb6GhMmjmNlqzj-Pe734OG-ja7xSFINSm-7aBqCpLWCJaD.jpg?size=100x100&quality=95&crop=0,0,500,500&ava=1">
        <h1>Скупка желе6447457з4455а</h1>
        <button id="buy">Купиgeserть</button>
    </div>

    <form id="form">
        <label>
            <p>Введите число от 1 до 9</p>
            <input type="text" id="user_number" title="Введите число от 1 до 9" pattern="[1-9]">
        </label>



<!--        <label>-->
<!--            <p>Введите число от 1 до 9</p>-->
<!--            <input type="text" id="user_name" required placeholder="Как к Вам обращаться?" title="от 3 символов" pattern="^[A-Za-zА-Яа-яЁё\s]{3,}">-->
<!--        </label>-->
<!--        -->
<!--        <label>-->
<!--            <p>Введите число от 1 до 9</p>-->
<!--            <input type="text" id="user_number" required placeholder="Введите номер телефона" title="от 10 до 11 цифр" pattern="[0-9]{10,11}">-->
<!--        </label>-->
<!--        -->
<!--        <label>-->
<!--            <p>Введите число от 1 до 9</p>-->
<!--             <input type="text" id="user_naming" required placeholder="Название комплектующего" title="от 3 символов" pattern="^[A-Za-zА-Яа-яЁё\s]{3,}">-->
<!--            -->
<!--        </label>-->
<!--        -->
<!--        <label>-->
<!--            <p>Введите число от 1 до 9</p>-->
<!--            <input type="text" id="user_condition" required placeholder="Состояние комплектующего" title="от 3 символов" pattern="^[A-Za-zА-Яа-яЁё\s]{3,}">-->
<!--        </label>-->

<!--        <input type="text" id="user_name" required placeholder="Как к Вам обращаться?" title="от 3 символов" pattern="^[A-Za-zА-Яа-яЁё\s]{3,}">-->



<!--        <input type="text" id="user_number" required placeholder="Введите номер телефона" title="от 10 до 11 цифр" pattern="[0-9]{10,11}">-->



<!--        <input type="text" id="user_naming" required placeholder="Название комплектующего" title="от 3 символов" pattern="^[A-Za-zА-Яа-яЁё\s]{3,}">-->



<!--        <input type="text" id="user_condition" required placeholder="Состояние комплектующего" title="от 3 символов" pattern="^[A-Za-zА-Яа-яЁё\s]{3,}">-->



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
            document.getElementById("main").style.display = "none";
            document.getElementById("form").style.display = "block";
        });

        order.addEventListener("click", () => {
            document.getElementById("error").innerText = '';
            let name = document.getElementById("user_name").value;
            let number = document.getElementById("user_number").value;
            let naming = document.getElementById("user_naming").value;
            let condition = document.getElementById("user_condition").value;


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
