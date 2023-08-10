# Css-Eva
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    body {
        overflow: hidden;
    }
    .eva {
        width: 250px;
        height: 400px;
        margin-left: 500px;
    }
    .head-container {
        width: 200px;
        height: 125px;
        margin: auto;
        animation: moveHeadEva 3s ease infinite alternate;
        position: relative;
        z-index: 5;

    }
    .head {
        background-color: white;
        background-image: 
            radial-gradient(100% 250% ellipse at 0% 50%, #fff 25%, transparent 35%),
            radial-gradient(circle at 0% 0%, white, #aaa);
        width: 150px;
        height: 110px;
        margin: auto;
        border-radius: 50% 50% 35% 35%;
        display: flex;
        justify-content: center;
        align-items: center;
        transform: translate(0, 5px);
        box-shadow: 0 0 35px rgba(0, 0, 0, 0.3);
    }
    .face {
        background: linear-gradient(to bottom, #353535, #111);
        width: 115px;
        height: 70px;
        border-radius: 50% 50% 46% 46% / 60% 60% 37% 37%;
        border: 2px solid black;
        transform: translate(0, -4px);
        display: flex;
        justify-content: space-evenly;
        overflow: hidden;
        box-shadow: 0 0 5px rgba(0, 0, 0, 0.8);
    } 
    .face .eye {
        width: 38px;
        height: 20px;
        transform: translate(0, 28px) rotate(20deg);
        border-radius: 50%;
        box-shadow: 0 0 3px 2px #00b2e5;
        background: repeating-linear-gradient(29deg, #00b2e5 10%, #252eb3 17%);
    }
    .right.eye {
        transform: translate(0,28px) rotate(-20deg);
    }
    .left.eye {
        transform: translate(0,28px) rotate(20deg);
    }
    .face::after{
        content: "";
        display: block;
        background-color: #111;
        position: absolute;
        width: 100px;
        height: 100px;
        border-radius: 50%;
        transform: translate(25px, 0);
        z-index: -1;
    }
    .body-container {
        display: flex;
        justify-content: center;
        animation: moveBody 3s ease infinite alternate;
    }
    .right-container {
        perspective: 200px;
    }
    
    .body {
        background-color: white;
        background-image: 
        radial-gradient(ellipse 250% 250% at 80% 120%, #ccc 15%, transparent 25%),
        radial-gradient(100% 250% ellipse at 0% 50%, #fff 25%, transparent 35%),
        linear-gradient(to right, #fff, #ccc);
        width: 150px;
        height: 200px;
        border-radius: 25% 25% 50% 50% / 16% 16% 60% 60%;
        box-shadow:
            0 0 35px rgba(0, 0, 0, 0.3),
            2px 2px 15px rgba(0, 0, 0, 0.12);
        position: relative;
        z-index: 1;
    }
    .panel {
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        width: 45px;
        height: 15px;
        transform: translate(25px, 10px);
    }
    .dot {
        --color: #7392a3;
        width: 5px;
        height: 5px;
        border-radius: 50%;
        background: var(--color);
        box-shadow: 0 0 4px 1px var(--color);
        opacity: 0;
    }
    .dot.dot-1 {
        animation: dotAppears 10s linear 8s  infinite;
    }
    
    .dot.dot-2 {
        animation: dotAppears 10s linear 9s infinite;
    }
    
    .dot.dot-3 {
        animation: dotAppears 10s linear 10s infinite;
    }
    .bigdot {
        --color: #6bbc6c;
        width: 15px;
        height: 15px;
        border-radius: 50%;
        background: var(--color);
        box-shadow: 0 0 4px 1px var(--color);
        animation: bigdot 1s linear 11s infinite;
        opacity: 0;
    }
    .scaner {
        background-image: linear-gradient(rgb(11, 86, 248), transparent);
        opacity: 0;
        position: absolute;
        top: 35px;
        width: 100%;
        height: 250px;
        z-index: 10;
        clip-path: polygon(50% 0, 100% 100%, 0 100%);
        transform-origin: 50% 0;
        animation: moveScaner 4s linear alternate 2 backwards;
        

    }
    
    .body::before {
        content: "";
        display: block;
        width: 130px;
        height: 20px;
        background-color: #bbb;
        background-image: radial-gradient(circle, #999, #bbb);
        margin: auto;
        border-radius: 50%;
        filter: blur(4px);
    }

    .shadow {
        width: 100px;
        height: 10px;
        background-color: #aaa;
        border-radius: 50%;
        filter: blur(2px);
        margin: auto;
        animation: moveshadow 3s infinite alternate;

    }
    @keyframes moveScaner {
        0% {
            transform: skew(50deg);
            opacity: 0.3;
        }
        100% {
            transform: skew(-50deg);
            opacity: 0.3;
        }
    }
    @keyframes dotAppears {
        0%, 100% {
            opacity: 1;
        }
    }
    @keyframes bigdot {
        11%, 100% {
            opacity: 1;
        }
    }
    @keyframes moveshadow {
        0% {
            transform: translate(0, 15px) scaleX(1);
            background-color: #ddd;
        }
        100% {
            transform: translate(0, 15px) scaleX(0.8);
            background-color: #ccc;
        }

    }
    @keyframes moveBody {
        0% {
            transform: translate(0, -10px);
        }

        100% {
            transform: translate(0, 0);
        }
    }
    @keyframes moveHeadEva {
        0% {
            transform: translate(0, 0);
        }
        100% {
            transform: translate(0, 15px);
        }
    }
    .arm {
        background-color: blue;
        width: 25px;
        height: 145px;
        border-radius: 40% 40% 75% 75%;
    }
    .left.arm {
        transform: translate(10px, 25px);
        box-shadow: 4px 0 0 #bbb;
        background-image: linear-gradient(to left, #fff 60%, #ccc 90%);
        position: relative;
        z-index: 2;

    }
    .right.arm {
        transform: translate(-10px, 25px) rotateY(184deg) skewX(-2deg);
        box-shadow: -4px 0 0 #bbb;
        background-image: linear-gradient(to right, #fff 40%, #ccc 80%);
    }
</style>
<body>
    <div class="eva">
        <div class="head-container">
            <div class="head">
                <div class="face">
                <div class="left eye"></div>
                <div class="right eye"></div>
                </div>
            </div>
        </div>
        <div class="body-container">
            <div class="left arm"></div>
            <div class="body">
                <div class="panel">
                    <div class="dot dot-1"></div>
                    <div class="dot dot-2"></div>
                    <div class="dot dot-3"></div>
                    <div class="bigdot"></div>
                </div>
            </div>
            <div class="right-container">
                <div class="right arm"></div>
            </div>
            <div class="scaner"></div>
        </div>
        <div class="shadow"></div>
    </div>
    <div class="planta">
        <div>hhh</div>
        
    </div>
</body>
</html>
