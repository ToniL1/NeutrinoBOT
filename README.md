<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NeutrinoBot</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            height: 100%;
            width: 100%;
            overflow: hidden;
        }

        .container {
            position: relative;
            width: 100%;
            height: 100vh;
        }

        .responsive-image {
            position: absolute;
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: none;
        }

        .fallback-image {
            display: block;
        }

        @media (orientation: landscape) {
            .landscape-image {
                display: block;
            }
            .portrait-image,
            .fallback-image {
                display: none;
            }
        }

        @media (orientation: portrait) {
            .portrait-image {
                display: block;
            }
            .landscape-image,
            .fallback-image {
                display: none;
            }
        }

        .science-button {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            padding: 18px 40px;
            font-size: 1.4em;
            font-weight: bold;
            background: linear-gradient(145deg, #2b5876, #4e4376);
            color: #fff;
            border: 3px solid #4CAF50;
            border-radius: 15px;
            cursor: pointer;
            z-index: 1000;
            transition: all 0.3s ease;
            box-shadow: 0 8px 15px rgba(0,0,0,0.3),
                        inset 0 4px 15px rgba(255,255,255,0.3);
            text-shadow: 1px 1px 2px rgba(0,0,0,0.3);
            font-family: 'Arial', sans-serif;
        }

        .science-button::before {
            content: '⚗️';
            margin-right: 12px;
            filter: drop-shadow(0 2px 2px rgba(0,0,0,0.3));
        }

        .science-button:hover {
            transform: translateX(-50%) translateY(-3px);
            box-shadow: 0 12px 20px rgba(0,0,0,0.4),
                       inset 0 4px 20px rgba(255,255,255,0.4);
            background: linear-gradient(145deg, #3a6b8c, #5f4f8c);
        }

        .science-button:active {
            transform: translateX(-50%) translateY(1px);
            box-shadow: 0 4px 10px rgba(0,0,0,0.3),
                       inset 0 2px 10px rgba(255,255,255,0.2);
        }
    </style>
</head>
<body>
    <div class="container">
        <img src="https://media-hosting.imagekit.io//95054af62e684634/created%20by%20Antonio%20Lushi%20(3).jpg?Expires=1834868904&Key-Pair-Id=K2ZIVPTIP2VGHC&Signature=bAVZ66xlLJwLAgxBOIovAnocdEnbpCM7MZgmWjGdFbzvSxwjXitRGEaE-i3umd2VvjKQ~N2vHAGIPxm8tYAOJ~dSCR2pEToIllAexLZFDs4WNLxf2oGTjzGVC34FZg5nleYu9McHjs50jPXq6rzb3-oah1RkRQrhI~BCN9FI3A39WjprK9wa1m49B3BQ4UVwnwLCVRFpwxA8IxVvTF3q9Tg-4ZloVJEZBf6uRbMwXkXZUZSIxLLrzkDa66jgsAhm6dfu6QuXeCdmCjQ5kCQ0PoQE6G8Pihe-dU5I1U6zXpyDna6EWZLwCDeBTnMKKNM3tgdL3e2zWL0fXtYf9hWVAw__" 
             class="responsive-image landscape-image" alt="Landscape View">
        
        <img src="https://media-hosting.imagekit.io//170b9c6d57424577/NeutrinoBOT%20is%20an%20AI%20assistant%20designed%20to%20enhance%2C%20support%2C%20and%20optimize%20your%20journey%20in%20the%20AI%20in%20STEM%20Challenge%2CScience%20on%20Stage.%20Developed%20by%20Braian%20Bi%C3%A7a%2CFrenki%20Sherali%20Designed%20by%20Antonio%20Lus.jpg?Expires=1834855108&Key-Pair-Id=K2ZIVPTIP2VGHC&Signature=r1Ziy5w6fNCwzLUQMQnPSXiErJXVndhQwegvw1ifn8wqkc84iflhwrEWhRJd7eFjB5XIHrS5ULqX8TAE4qkJkKoifXPMTM5Jg4wIS6-iGBggnHmy8n5eVS2-kP2f7RnEHS0PX-640Was8auDQdaUvPSwzydCb27e54WwXDwLldI0OBT22Rb1kUgROq9lTlO5jZg3eXi~nZpQwl4g3GtaOrU-omEIC5WgXbUI0X64OTaj2KGD5VWyO7kkELyTn0VmxMFGqfzTr2q9~lLyOFty7Z0Rlu~V0WZXaSUwMbbtLsCI0e6vhguQ9q5PLthaTr0CctbiGU4MSxgG1fbQtQj9ug__" 
             class="https://media-hosting.imagekit.io//5136deb459ce4996/NeutrinoBOT%20is%20an%20AI%20assistant%20designed%20to%20enhance,%20support,%20and%20optimize%20your%20journey%20in%20the%20AI%20in%20STEM%20Challenge,Science%20on%20Stage.%20Developed%20by%20Braian%20Bi%C3%A7a,Frenki%20Sherali%20Designed%20by%20Antonio%20Lus%20(1).jpg?Expires=1834868904&Key-Pair-Id=K2ZIVPTIP2VGHC&Signature=JExoNx6R7sOLnlFbIkzLzzVvU6we2LqCk3JDL03R~HACMc52S955q3TMe~2N2PW6nPfxOQU7upr48X5jEGUdhX0e0jQkhGBDOXzh5q6t~DX8AdRXu4k-3e4WjfGOUosYIfckCu~Te7XQXRaWOR9I2IiFocRnjNtm9Xcn~eHZFpZWZXcP10wNYmQvYQvPaQ3b8HmjBS9EQ31umHeLuaiJ9W-5wyigEh47IhimjznUiFSFovO4Ru268igT2rGlh~ALhQy-JHpTkCIxoNC4neJjpyg0h-DfbzmrcDzSBR-y8JJNneFNUL47BKwwpiNX69tWE98rddemM~9uCn4ONvPGWQ__" alt="Portrait View">
        
        <img src="https://media-hosting.imagekit.io//bff7d2d141244947/created%20by%20Antonio%20Lushi%20(1).jpg?Expires=1834855108&Key-Pair-Id=K2ZIVPTIP2VGHC&Signature=FnACQJR4qGLrosHKbReA5aMTgn8gZuISoLA1k9UP7WvKWd62DDLO7uxxUYru0VYY-GYJCtkK09nSEdayAUi~8B5GmWEhkijXeaUfmtuhWwCitrX5ExdscSbg0MFWep-jH4xR3b~y1rZCqYJPgkfX9g5vm8c36~0HPcrXoSl0uotpEk2rTK7Rue5np-3NcQwkmrlhf7mXtpr3sZ7QikUAbL91SdhEfl47Hw3ik6JF4v-49kmJQ~451UUoJMhtBp5KfLeXdX6JL~-JsXLwOh3bMD3CFC4Ke3Rft2KK07~f4tjih~62NwPR1OQtUk5Wrly~LvY4VX2Xg7MXr0U4k8O-Fw__" 
             class="responsive-image fallback-image" alt="Fallback View">
        
        <button class="science-button" onclick="window.location.href='https://codepen.io/ToniL-1/full/yyLJaXQ'">
            Launch NeutrinoBot
        </button>
    </div>
</body>
</html>
