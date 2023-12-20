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
