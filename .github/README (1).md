تمام HTML files (Login, Dashboard, Team, Profile) کو ایک ساتھ رکھ کر ایک ready-to-upload GitHub repository کے لیے تیار کیا گیا ہے۔


---

index.html (Login Page)

<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<title>Government – Login</title>
<style>
body{margin:0;font-family:Arial;background:#f4fff8}
.box{max-width:320px;margin:80px auto;background:#fff;padding:25px;border-radius:15px;box-shadow:0 2px 8px rgba(0,0,0,0.1);text-align:center}
h2{color:#27ae60;}
input{width:100%;padding:10px;margin:10px 0;border-radius:8px;border:1px solid #ccc}
button{width:100%;padding:10px;background:#2ecc71;color:#fff;border:none;border-radius:8px;font-size:16px}
p{font-size:12px;color:#888;}
</style>
</head>
<body>
<div class="box">
  <h2>Government</h2>
  <input type="text" placeholder="Username">
  <input type="password" placeholder="Password">
  <a href="dashboard.html"><button>Login (Demo)</button></a>
  <p>Demo login only – No real account</p>
</div>
</body>
</html>
---

dashboard.html (Main Dashboard with Deposit/Withdraw/Ads popup)

<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<title>Government – Dashboard</title>
<style>
body{margin:0;font-family:Arial;background:#f4fff8;padding-bottom:70px;}
.header{background:#2ecc71;color:#fff;padding:12px;text-align:center;font-size:20px;font-weight:bold;}
.container{padding:15px;}
.balance{background:linear-gradient(135deg,#27ae60,#2ecc71);color:#fff;padding:20px;border-radius:15px;}
.balance h3{margin:0;font-size:15px;}
.balance h1{margin:6px 0 0;font-size:26px;}
.actions{display:flex;gap:10px;margin:15px 0;}
.action{flex:1;background:#fff;border-radius:12px;padding:12px;text-align:center;box-shadow:0 2px 6px rgba(0,0,0,0.1);font-size:13px;cursor:pointer;}
.action span{display:block;color:#27ae60;font-weight:bold;margin-top:5px;}
.info{display:flex;justify-content:space-between;font-size:13px;margin-bottom:15px;}
.cards{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;}
.card{background:#fff;border-radius:15px;padding:15px;box-shadow:0 2px 6px rgba(0,0,0,0.1);}
.card h4{margin:0;font-size:13px;color:#555;}
.card p{margin:6px 0 0;font-size:18px;font-weight:bold;color:#27ae60;}
.footer{text-align:center;font-size:11px;color:#888;margin-top:15px;}
.menu{position:fixed;bottom:0;left:0;width:100%;background:#fff;display:flex;border-top:1px solid #ddd;}
.menu a{flex:1;text-align:center;padding:10px 0;font-size:12px;color:#27ae60;text-decoration:none;}
.popup{position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.4);display:none;align-items:center;justify-content:center;}
.popup-box{background:#fff;padding:20px;border-radius:15px;width:85%;max-width:300px;text-align:center;}
.popup-box h3{margin-top:0;color:#27ae60;}
.popup-box input{width:100%;padding:10px;margin:8px 0;border-radius:8px;border:1px solid #ccc;}
.btn{background:#2ecc71;color:#fff;border:none;padding:10px;border-radius:8px;width:100%;}
.close{margin-top:8px;font-size:12px;color:#999;cursor:pointer;}
</style>
</head>
<body>
<div class="header">Government</div>
<div class="container">
  <div class="balance"><h3>Account Balance</h3><h1>PKR 12,366</h1></div>
  <div class="actions">
    <div class="action" onclick="openPopup('deposit')">💰<span>Deposit</span></div>
    <div class="action" onclick="openPopup('withdraw')">🏧<span>Withdraw</span></div>
    <div class="action" onclick="openPopup('ads')">▶️<span>Watch Ads</span></div>
  </div>
  <div class="info"><div>User: <b>demo_user</b></div><div>Ref: <b>admin</b></div></div>
  <div class="cards">
    <div class="card"><h4>Pending Tasks</h4><p>85</p></div>
    <div class="card"><h4>Total Deposit</h4><p>PKR 25,000</p></div>
    <div class="card"><h4>Total Withdraw</h4><p>PKR 379,600</p></div>
    <div class="card"><h4>Task Earnings</h4><p>PKR 0.00</p></div>
  </div>
  <div class="footer">Government Demo Platform<br>Training purpose only – No real earnings</div>
</div>
<div class="menu">
  <a href="dashboard.html">🏠<br>Home</a>
  <a href="team.html">👥<br>Team</a>
  <a href="profile.html">👤<br>Profile</a>
</div>
<div class="popup" id="popup"><div class="popup-box" id="popupContent"></div></div>
<script>
function openPopup(type){
  let content='';
  if(type==='deposit'){
    content=`<h3>Deposit (Demo)</h3><input placeholder="Enter amount"><input placeholder="Transaction ID"><button class='btn'>Submit</button><div class='close' onclick='closePopup()'>Close</div>`;
  }
  if(type==='withdraw'){
    content=`<h3>Withdraw (Demo)</h3><input placeholder="Enter amount"><input placeholder="Wallet number"><button class='btn'>Request</button><div class='close' onclick='closePopup()'>Close</div>`;
  }
  if(type==='ads'){
    content=`<h3>Watch Ads (Demo)</h3><p>Ad watching is disabled in demo mode.</p><button class='btn' onclick='closePopup()'>OK</button>`;
  }
  document.getElementById('popupContent').innerHTML=content;
  document.getElementById('popup').style.display='flex';
}
function closePopup(){document.getElementById('popup').style.display='none';}
</script>
</body>
</html>
---

team.html & profile.html بھی اسی structure کے ساتھ add کریں۔
