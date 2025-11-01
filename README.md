<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ayrton Senna</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Roboto:wght@300;400;500&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Roboto', sans-serif;
      background-color: #edf1f4;
      color: #1f1f1f;
      line-height: 1.6;
    }

    /* Hero Section */
    .hero {
      height: 200px;
      background: linear-gradient(120deg, #e9f7f6, #b0d0ff, #e9f7f6);
      background-size: 300% 300%;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      position: relative;
      box-shadow: 0 3px 6px rgba(0, 0, 0, 0.05);
      transition: background 2s ease;
    }

    .hero:hover {
      background: linear-gradient(120deg, #4da6ff, #f7eaaa, #4da6ff);
      background-size: 300% 300%;
      animation: gradientShift 6s ease-in-out infinite alternate;
    }

    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      100% { background-position: 100% 50%; }
    }

    .hero h1 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 3rem;
      color: #1f3b5d;
      letter-spacing: 3px;
      text-shadow: 0 0 8px rgba(31, 59, 93, 0.15);
      opacity: 0;
      animation: fadeIn 2s ease forwards;
      transition: background 0.8s ease, color 0.8s ease;
    }

    .hero h1:hover {
      background: linear-gradient(90deg, #007f00, #f7d000);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      text-shadow: 0 0 10px rgba(247, 208, 0, 0.4);
    }

    @keyframes fadeIn {
      0% { opacity: 0; transform: translateY(15px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    /* Main Content */
    .content {
      max-width: 900px;
      margin: 60px auto;
      padding: 0 20px;
      display: flex;
      flex-direction: column;
      gap: 35px;
    }

    .card {
      background: #ffffff;
      padding: 25px 30px;
      border-radius: 12px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .card:hover {
      transform: translateY(-3px);
      box-shadow: 0 3px 12px rgba(0, 0, 0, 0.08);
    }

    .card h2 {
      font-size: 1.5rem;
      margin-bottom: 15px;
      color: #1f3b5d;
    }

    .card p, .card li {
      margin-bottom: 10px;
    }

    ul {
      padding-left: 20px;
    }
  </style>
</head>
<body>

  <section class="hero">
    <h1>AYRTON SENNA</h1>
  </section>

  <section class="content">
    <div class="card">
      <h2>Cuộc đời</h2>
      <p>Tên đầy đủ: Ayrton Senna da Silva</p>
      <p>Ngày sinh: 21/3/1960 — Quê quán: São Paulo, Brazil</p>
      <p>Bắt đầu lái kart từ năm 4 tuổi, vô địch Karting Brazil khi 17 tuổi. Năm 1981 sang châu Âu thi đấu Formula Ford, nhanh chóng gây tiếng vang.</p>
    </div>

    <div class="card">
      <h2>Thành tựu</h2>
      <ul>
        <li>Ra mắt F1 năm 1984 (Toleman)</li>
        <li>3 lần vô địch thế giới: 1988, 1990, 1991</li>
        <li>41 chiến thắng Grand Prix, 65 pole positions</li>
        <li>Biệt danh: “Vua của mưa” – Rain Master</li>
      </ul>
    </div>

    <div class="card">
      <h2>Sở thích & tính cách</h2>
      <p>Đam mê tốc độ, nhưng ngoài đường đua rất khiêm tốn, sâu sắc. Tin vào Chúa và xem đua xe là sứ mệnh tâm linh. Yêu thiên nhiên, thể thao và sống giản dị.</p>
    </div>

    <div class="card">
      <h2>Câu nói nổi tiếng</h2>
      <ul>
        <li>“If you no longer go for a gap that exists, you’re no longer a racing driver.”</li>
        <li>“Being second is to be the first of the ones who lose.”</li>
        <li>“I have no idols. I admire work, dedication and competence.”</li>
      </ul>
    </div>
  </section>

</body>
</html>
