<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BANK</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-image: url('https://arabradio.us/wp-content/uploads/2019/12/%D8%B5%D9%88%D8%B1-%D8%A7%D9%84%D9%81%D8%B6%D8%A7%D8%A1-16.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed; 
            color: white;
            transition: background-image 0.5s ease;
            padding: 20px;
        }
        .content {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            width: 90%;
            max-width: 500px;
            transition: all 0.5s ease;
            text-align: center;
        }
        input, button {
            padding: 14px;
            margin: 10px 0;
            font-size: 16px;
            width: 100%;
            box-sizing: border-box;
        }
        button {
            cursor: pointer;
            background-color: rgba(255, 255, 255, 0.2);
            border: none;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: rgba(255, 255, 255, 0.4);
        }
        #result {
            font-size: 18px;
            margin-top: 20px;
        }
        .media {
            margin-top: 20px;
            width: 100%;
            max-width: 300px;
            height: auto;
            border-radius: 10px;
            transition: all 0.5s ease;
        }
        footer {
            margin-top: auto;
            padding: 10px;
            font-size: 14px;
            opacity: 0.8;
        }
        @media (max-width: 768px) {
            .content {
                width: 100%;
            }
        }
        @media (max-width: 480px) {
            input, button {
                font-size: 14px;
                padding: 10px;
            }
            #result {
                font-size: 16px;
            }
        }
    </style>
</head>
<body>
    <title>talal_megumi</title>
    <div class="content">
        <h1>بنك الشمس</h1>
        <p>أدخل اسم الشخصية لترى الستارز والإنذارات</p>
        <input type="text" id="characterName" placeholder="اسم الشخصية">
        <button onclick="showStars()">إظهار المعلومات</button>
        <div id="result"></div>
    </div>
    <footer>
        <p>حقوق الطبع والنشر محفوظة <a href="https://www.instagram.com/talal_megumi" target="_blank">talal_megumi</a></p>
    </footer>
    <script>
        const characters = [
            { name: "فايوليت", stars: 100000000, alerts: 0, rank: "الملكة", mediaUrl: 'https://media1.tenor.com/m/TZ89Av8QBVkAAAAd/violet-evergarden-violet.gif' },
            { name: "شوتو", stars: 1500, alerts: 0, rank: "وزير", mediaUrl: 'https://64.media.tumblr.com/2ab9ce88b76275915865b615a0934a24/c5f1d2f2eb86057c-03/s1280x1920/27a5ca69c458325cc450f9f02304c39bff4deb7d.gifv' },
            { name: "توكيتو", stars: 1500, alerts: 0, rank: "رائيس الوزراء", mediaUrl: 'https://media1.tenor.com/m/VO0p4rzSGQ4AAAAd/demon-slayer-kimetsu-no-yaiba.gif' },
            { name: "ميغومي", stars: 1500, alerts: 0, rank: "مؤسس البنك", mediaUrl: 'https://media1.tenor.com/m/AtKrHqCCRsEAAAAC/megumi.gif' },
            { name: "", stars: 1500, alerts: 0, rank: "", mediaUrl: '' },
            { name: "", stars: 1500, alerts: 0, rank: "", mediaUrl: '' },
            { name: "", stars: 1500, alerts: 0, rank: "", mediaUrl: '' },
            { name: "", stars: 1500, alerts: 0, rank: "", mediaUrl: '' },
            { name: "", stars: 1500, alerts: 0, rank: "", mediaUrl: '' },
        ];
        function showStars() {
            const name = document.getElementById("characterName").value.trim();
            const resultDiv = document.getElementById("result");
            if (!name) {
                resultDiv.innerHTML = "الرجاء إدخال اسم شخصية.";
                return;
            }
            const character = characters.find(char => char.name === name);
            if (!character) {
                resultDiv.innerHTML = "الشخصية غير موجودة.";
                resultDiv.innerHTML += <img class="media" src="https://th.bing.com/th/id/R.68646d97c953d504c1057cf5417434c2?rik=nHi%2f7nEbJ7i1RQ&pid=ImgRaw&r=0" />;
                return;
            }
            resultDiv.innerHTML = `
                <p>الرتبة: ${character.rank}</p>;
                <p>الستارز: ${character.stars}</p>;
                <p>الإنذارات: ${character.alerts}</p>;
                <img class="media" src="${character.mediaUrl}" alt="${character.name}" />`;
        }
    </script>
</body>
</html>
