<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Giới thiệu — [Tên của bạn]</title>
  <meta name="description" content="Trang giới thiệu cá nhân — thông tin, kỹ năng và liên hệ">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg: linear-gradient(180deg, #0b1220 0%, #0f3a5a 100%);
      --card: #0b1220;
      --muted: #9aa4b2;
      --accent: #6ee7b7;
      --accent-2: #7dd3fc;
      --radius: 14px;
      font-family: 'Inter', system-ui;
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      background: var(--bg);
      color:#e6eef6;
      display:flex;
      justify-content:center;
      padding:32px 20px;
    }

    .wrap{width:100%;max-width:980px}
    header{display:flex;align-items:center;justify-content:space-between;margin-bottom:18px}

    .brand{display:flex;align-items:center;gap:12px}
    .logo{
      width:56px;height:56px;border-radius:12px;
      background:linear-gradient(135deg,var(--accent),var(--accent-2));
      display:flex;align-items:center;justify-content:center;
      font-weight:800;color:#042024;box-shadow:0 6px 18px rgba(2,6,23,0.6)
    }
    .brand h1{font-size:18px;margin:0}
    .brand p{margin:0;font-size:13px;color:var(--muted)}

    .btn{background:rgba(255,255,255,0.05);border:none;padding:8px 12px;border-radius:10px;color:#fff;cursor:pointer;font-weight:600}

    main{display:grid;grid-template-columns:1fr 360px;gap:24px}
    @media (max-width:920px){main{grid-template-columns:1fr}}

    .card{background:rgba(255,255,255,0.02);border-radius:var(--radius);padding:22px}
    .avatar{width:120px;height:120px;border-radius:18px;background:rgba(255,255,255,0.05);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:28px}

    aside{position:sticky;top:22px;height:fit-content}
    .profile-card{display:flex;flex-direction:column;gap:12px;align-items:center;text-align:center}

    footer{text-align:center;color:var(--muted);font-size:13px;margin-top:20px}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="logo">TD</div>
        <div>
          <h1>[Tên của bạn]</h1>
          <p>Web giới thiệu cá nhân</p>
        </div>
      </div>
      <button class="btn" id="themeToggle">Chế độ</button>
    </header>

    <main>
      <div>
        <section class="card">
          <div style="display:flex;gap:18px;align-items:center">
            <div class="avatar">TD</div>
            <div class="intro">
              <h2>Xin chào — tôi là [Tên của bạn]</h2>
            </div>
          </div>
        </section>
      </div>

      <aside>
        <div class="card profile-card">
          <div style="width:88px;height:88px;border-radius:12px;background:linear-gradient(180deg,var(--accent),var(--accent-2));display:flex;align-items:center;justify-content:center;font-weight:800;color:#042024">TD</div>
          <div>
            <h4>[Tên của bạn]</h4>
          </div>
        </div>
      </aside>
    </main>

    <footer>
      <div>© <span id="year"></span> [Tên của bạn]</div>
    </footer>
  </div>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
    document.getElementById('themeToggle').addEventListener('click',()=>{
      document.body.classList.toggle('light');
    });
  </script>
</body>
</html>
