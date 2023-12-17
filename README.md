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

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {

            font-family: 'Geologica', sans-serif;
            font-weight: 200;
            color: var(--tg-theme-text-color);
            background: var(--tg-theme-bg-color);
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
            border: 0;
            border-radius: 5px;
            margin-top: 50px;
            height: 60px;
            width: 200px;
            font-size: 20px;

        }
        button:hover {
            background: var(--th-theme-secondary-bg-color);
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
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
</body>
</html>
