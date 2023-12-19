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
            display: block;
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



    <form id="form">
        <h1>Оформление заявки</h1>
        <input type="text" placeholder="Имяrqrqd" id="user_name">
        <input type="text" placeholder="Телефон" id="user_number">
        <input type="text" placeholder="Название комплектующего" id="user_naming">
        <input type="text" placeholder="Состояние комплектующего" id="user_condition">
        <div id="error"></div>
        <button id="order">Оформить</button>

    </form>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <script>

        let tg = window.Telegram.WebApp;
        let order = document.getElementById("order");



        order.addEventListener('click', () => {
            document.getElementById("error").innerText = "";
            tg.expand();
            let name = document.getElementById("user_name").value;
            let number = document.getElementById("user_number").value;
            let naming = document.getElementById("user_naming").value;
            let condition = document.getElementById("user_condition").value;

            if (name.length < 1) {
                document.getElementById("error").innerText = "Ошибка в имени";
                return order;
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
