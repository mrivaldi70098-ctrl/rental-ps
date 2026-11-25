# rental-ps
```html
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RENTAL PS PRO MAX</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;600;700;800&family=Poppins:wght@300;400;500;600;700&family=Rajdhani:wght@500;600;700&display=swap" rel="stylesheet">
<style>
:root {
 --bg:#090e1b;
 --panel:#151e32;
 --accent:#895cf6;
 --text:#fff;
 --line:#303c56;
 --green:#20c98a;
 --red:#e65065;
 --yellow:#eeb74d;
}
* {box-sizing:border-box;font-family:'Poppins',sans-serif}
h1,h2 {font-family:'Orbitron',sans-serif;letter-spacing:.5px}
h3,button,.timer {font-family:'Rajdhani',sans-serif}
button {font-size:16px;letter-spacing:.3px;transition:transform .18s ease,filter .18s ease}
button:hover {transform:translateY(-2px);filter:brightness(1.12)}
body {
 margin:0;
 background:var(--bg);
 color:var(--text);
}
button {
 border:0;
 border-radius:8px;
 padding:10px 14px;
 background:var(--accent);
 color:white;
 cursor:pointer;
 font-weight:bold;
 margin:3px;
}
button:disabled {opacity:.4;cursor:not-allowed}
input,select {
 width:100%;
 padding:11px;
 margin:7px 0 14px;
 border-radius:7px;
 border:1px solid var(--line);
 background:#0c1426;
 color:white;
}
.hidden {display:none!important}
#login {
 min-height:100vh;
 display:grid;
 place-items:center;
 padding:20px;
}
.loginbox {
 background:var(--panel);
 padding:30px;
 border-radius:15px;
 width:100%;
 max-width:400px;
}
#app {display:none}
header {
 min-height:190px;
 padding:25px;
 display:flex;
 align-items:center;
 gap:18px;
 background:
 linear-gradient(#0009,#000b),
 url("https\://images.unsplash.com/photo-1593305841991-05c297ba4575?w=1400")
 center/cover;
}
header h1 {color:#c7aaff;margin:0}
header img {width:65px;height:65px;object-fit:contain}
nav {
 display:flex;
 gap:7px;
 flex-wrap:wrap;
 background:var(--panel);
 padding:12px;
}
main {
 max-width:1400px;
 margin:auto;
 padding:20px;
}
.page {display:none}
.page.active {display:block}
.grid {
 display:grid;
 grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
 gap:14px;
}
.stats {
 display:grid;
 grid-template-columns:repeat(auto-fit,minmax(160px,1fr));
 gap:12px;
 margin-bottom:20px;
}
.card {
 background:var(--panel);
 padding:18px;
 border:1px solid var(--line);
 border-radius:12px;
}
.metric {
 font-size:26px;
 font-weight:bold;
 color:#c5aaff;
 margin-top:8px;
}
.green {color:var(--green)}
.red {color:var(--red)}
.yellow {color:var(--yellow)}
.timer {
 font-size:25px;
 color:#c5aaff;
 margin:15px 0;
 font-weight:bold;
}
.tv-status {
 display:flex;
 justify-content:space-between;
 align-items:center;
 margin:12px 0;
}
.dot {
 width:11px;
 height:11px;
 border-radius:50%;
 display:inline-block;
 margin-right:6px;
}
.on {background:var(--green)}
.off {background:var(--red)}
.disconnected {background:#888}
.tablewrap {overflow-x:auto}
table {
 width:100%;
 min-width:650px;
 border-collapse:collapse;
}
th,td {
 padding:12px;
 text-align:left;
 border-bottom:1px solid var(--line);
}
.receipt {
 background:white;
 color:black;
 max-width:360px;
 padding:20px;
 font-family:monospace;
}
.tv-card {border:1px solid #514078;box-shadow:0 8px 24px #0004}
.remote-box {margin:16px 0;padding:16px;border:1px solid #514078;border-radius:14px;background:linear-gradient(145deg,#111a2c,#202944)}
.remote-title {font-family:'Orbitron',sans-serif;font-size:13px;color:#c7aaff;letter-spacing:1.5px;margin-bottom:12px}
.volume-display {display:flex;align-items:center;justify-content:space-between;padding:12px;border-radius:9px;background:#090e1b;margin-bottom:10px}
.volume-display strong {font-family:'Orbitron',sans-serif;color:#20c98a;font-size:20px}
.volume-buttons {display:grid;grid-template-columns:1fr 1fr;gap:8px}
.volume-buttons button {margin:0;padding:12px}
.volume-down {background:#52627d}
.volume-up {background:#20a879}
.mute-button {width:100%;margin:9px 0 0;background:#895cf6}
@media(max-width:650px) {
 header {min-height:140px;padding:15px}
 header h1 {font-size:24px}
 main {padding:12px}
 nav button {flex:1}
}
@media print {
 body * {visibility:hidden}
 #printArea,#printArea * {visibility:visible}
 #printArea {
  position:absolute;
  top:0;
  left:0;
  display:block!important;
 }
}
</style>
</head>
<body>
<!-- LOGIN -->
<div id="login">
 <div class="loginbox">
  <h1>🎮 RENTAL PS PRO MAX</h1>
  <p>Login Admin / Karyawan</p>
  <label>Username</label>
  <input id="username" value="admin">
  <label>Password</label>
  <input id="password" type="password">
  <button onclick="login()" style="width:100%">LOGIN</button>
  <p id="loginError" class="red"></p>
  <small>
   Admin: admin / admin123<br>
   Kasir: kasir / kasir123
  </small>
 </div>
</div>
<!-- APLIKASI -->
<div id="app">
<header id="cover">
 <img id="logo" class="hidden">
 <div>
  <h1 id="brand">RENTAL PS PRO MAX</h1>
  <p>PLAY • GAME • ENJOY</p>
 </div>
</header>
<div style="padding:12px;background:#111a2c">
 <span id="userInfo"></span>
 <button onclick="logout()" style="float:right">LOGOUT</button>
</div>
<nav>
 <button onclick="page('dashboard')">Dashboard</button>
 <button onclick="page('machines')">Mesin PS</button>
 <button onclick="page('television')">Kontrol TV</button>
 <button onclick="page('booking')">Booking</button>
 <button onclick="page('customers')">Pelanggan</button>
 <button onclick="page('reports')">Laporan</button>
 <button onclick="page('settings')">Pengaturan</button>
</nav>
<main>
<!-- DASHBOARD -->
<section id="dashboard" class="page active">
<h2>Dashboard Rental</h2>
<div class="stats" id="stats"></div>
<h2>Status Mesin</h2>
<div class="grid" id="dashboardMachines"></div>
<h2 style="margin-top:25px">Status TV</h2>
<div class="grid" id="dashboardTV"></div>
</section>
<!-- MESIN PS -->
<section id="machines" class="page">
<h2>Manajemen PlayStation</h2>
<div class="grid" id="machineGrid"></div>
</section>
<!-- KONTROL TV -->
<section id="television" class="page">
<h2>Kontrol Televisi</h2>
<div class="card">
 <h3>Mode Kontrol</h3>
 <select id="tvMode" onchange="saveSettings()">
  <option value="simulation">Simulasi (uji coba)</option>
  <option value="bridge">Perangkat nyata (API Bridge)</option>
 </select>
 <label>Alamat API Bridge</label>
 <input id="bridgeUrl" placeholder="http\://192.168.1.10:3000">
 <p style="color:#aaa;font-size:13px">
 Mode simulasi hanya mengubah tampilan status.
 Mode perangkat nyata membutuhkan server penghubung
 dan perangkat TV yang kompatibel.
 </p>
 <button onclick="saveSettings()">SIMPAN MODE</button>
</div>
<h3 style="margin-top:22px">Daftar Televisi</h3>
<div class="grid" id="tvGrid"></div>
</section>
<!-- BOOKING -->
<section id="booking" class="page">
<h2>Booking Rental PS</h2>
<div class="card">
<label>Nama pelanggan</label>
<input id="bookName">
<label>Nomor telepon</label>
<input id="bookPhone">
<label>Mesin PS</label>
<select id="bookMachine">
    ></select>
<label>Tanggal dan waktu</label>
<input type="datetime-local" id="bookDate">
<button onclick="addBooking()">SIMPAN BOOKING</button>
</div>
<h3>Daftar Booking</h3>
<div id="bookingList"></div>
</section>
<!-- PELANGGAN -->
<section id="customers" class="page">
<h2>Database Pelanggan</h2>
<div class="card">
<label>Nama</label>
<input id="customerName">
<label>Nomor telepon</label>
<input id="customerPhone">
<button onclick="addCustomer()">TAMBAH PELANGGAN</button>
</div>
<div id="customerList" style="margin-top:15px"></div>
</section>
<!-- LAPORAN -->
<section id="reports" class="page">
<h2>Laporan Pendapatan</h2>
<select id="reportFilter" onchange="renderReports()">
 <option value="day">Harian</option>
 <option value="week">Mingguan</option>
 <option value="month">Bulanan</option>
 <option value="all">Semua</option>
</select>
<button onclick="exportCSV()">EKSPOR EXCEL</button>
<button onclick="backup()">BACKUP DATA</button>
<button onclick="restore()">RESTORE DATA</button>
<input id="restoreFile" type="file" accept=".json" class="hidden">
<div id="reportStats" class="stats"></div>
<div class="card tablewrap">
<table>
<thead>
<tr>
<th>Tanggal</th>
<th>Pelanggan</th>
<th>Mesin</th>
<th>Paket</th>
<th>Durasi</th>
<th>Total</th>
<th>Struk</th>
</tr>
</thead>
<tbody id="salesList"></tbody>
</table>
</div>
</section>
<!-- PENGATURAN -->
<section id="settings" class="page">
<h2>Pengaturan Rental</h2>
<div class="card">
<h3>Identitas dan Tema</h3>
<label>Nama rental</label>
<input id="shopName">
<label>Deskripsi</label>
<input id="shopSubtitle">
<label>Warna tema</label>
<input id="themeColor" type="color">
<label>Ganti cover</label>
<input id="coverFile" type="file" accept="image/*">
<label>Ganti logo</label>
<input id="logoFile" type="file" accept="image/*">
<button onclick="saveAppearance()">SIMPAN TAMPILAN</button>
</div>
<div class="card" style="margin-top:15px">
<h3>Tambah Mesin PS</h3>
<label>Jenis</label>
<select id="newType">
<option>PS2</option>
<option>PS3</option>
<option>PS4</option>
<option>PS5</option>
</select>
<label>Nama mesin</label>
<input id="newMachineName" placeholder="PS5-01">
<label>Harga per jam</label>
<input id="newPrice" type="number" value="15000">
<button onclick="addMachine()">TAMBAH MESIN</button>
<div id="priceList"></div>
</div>
<div class="card" style="margin-top:15px">
<h3>Tambah Televisi</h3>
<label>Nama TV</label>
<input id="newTVName" placeholder="TV-01">
<label>Hubungkan dengan mesin PS</label>
<select id="newTVMachine"></select>
<label>ID perangkat pada bridge</label>
<input id="newTVDevice" placeholder="tv_01">
<button onclick="addTV()">TAMBAH TV</button>
</div>
<div class="card" style="margin-top:15px">
<h3>Akun Karyawan</h3>
<label>Username</label>
<input id="staffUser">
<label>Password</label>
<input id="staffPass" type="password">
<button onclick="addStaff()">TAMBAH KARYAWAN</button>
<div id="staffList"></div>
</div>
</section>
</main>
</div>
<div id="printArea" class="hidden"></div>
<script>
// DATABASE
function read(key,def) {
 try {
  return JSON.parse(localStorage.getItem("rpm\_"+key)) ?? def;
 } catch {
  return def;
 }
}
let settings=read("settings",{
 name:"RENTAL PS PRO MAX",
 subtitle:"PLAY GAME ENJOY",
 color:"#895cf6",
 cover:"",
 logo:"",
 tvMode:"simulation",
 bridgeUrl:""
});
let users=read("users",[
 {u:"admin",p:"admin123",role:"Admin"},
 {u:"kasir",p:"kasir123",role:"Karyawan"}
]);
let machines=read("machines",[
 {id:1,name:"PS2-01",type:"PS2",price:5000,status:"free",session:null},
 {id:2,name:"PS3-01",type:"PS3",price:7000,status:"free",session:null},
 {id:3,name:"PS4-01",type:"PS4",price:10000,status:"free",session:null},
 {id:4,name:"PS5-01",type:"PS5",price:15000,status:"free",session:null}
]);
let televisions=read("televisions",[
 {id:1,name:"TV-01",machine:1,device:"tv_01",status:"off"},
 {id:2,name:"TV-02",machine:2,device:"tv_02",status:"off"},
 {id:3,name:"TV-03",machine:3,device:"tv_03",status:"off"},
 {id:4,name:"TV-04",machine:4,device:"tv_04",status:"off"}
]);
let bookings=read("bookings",[]);
let customers=read("customers",[]);
let sales=read("sales",[]);
let currentUser=null;
// SIMPAN
function save() {
 for(let key of [
 "settings","users","machines",
 "televisions","bookings","customers","sales"
 ]) {
  localStorage.setItem(
   "rpm\_"+key,
   JSON.stringify(eval(key))
  );
 }
}
// LOGIN
function login() {
 let u=document.getElementById("username").value;
 let p=document.getElementById("password").value;
 let user=users.find(x=>x.u===u&&x.p===p);
 if(!user) {
  loginError.textContent="Username atau password salah";
  return;
 }
 currentUser=user;
 document.getElementById("login").style.display="none";
 document.getElementById("app").style.display="block";
 userInfo.textContent="Login: "+user.u+" ("+user.role+")";
 if(user.role!=="Admin") {
  document.querySelectorAll("#settings input, #settings select, #settings button")
  .forEach(x=>x.disabled=true);
 }
 applyAppearance();
 renderAll();
}
function logout() {
 location.reload();
}
// NAVIGASI
function page(id) {
 document.querySelectorAll(".page").forEach(x=>x.classList.remove("active"));
 document.getElementById(id).classList.add("active");
 renderAll();
}
// FORMAT
function money(n) {
 return "Rp "+Math.round(n).toLocaleString("id-ID");
}
function clock(ms) {
 let s=Math.max(0,Math.floor(ms/1000));
 let h=Math.floor(s/3600);
 let m=Math.floor(s%3600/60);
 let sec=s%60;
 return [h,m,sec].map(x=>String(x).padStart(2,"0")).join(":");
}
function escapeHTML(v) {
 return String(v??"").replace(/[&<>"']/g,c=>({
  "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"
 })[c]);
}
// PAKET
const packages=[
 {name:"1 Jam",hours:1},
 {name:"2 Jam",hours:2},
 {name:"3 Jam",hours:3},
 {name:"Paket Malam",hours:8}
];
// MULAI RENTAL
function startRental(id) {
 let m=machines.find(x=>x.id===id);
 if(!m||m.status!=="free")return;
 let name=prompt("Nama pelanggan:");
 if(name===null)return;
 name=name.trim()||"Pelanggan umum";
 let phone=prompt("Nomor telepon:")||"";
 let choice=prompt(
  "PILIH PAKET:\n1. 1 Jam\n2. 2 Jam\n3. 3 Jam\n4. Paket Malam"
 );
 let pack=packages[Number(choice)-1];
 if(!pack)return alert("Paket tidak valid");
 m.status="busy";
 let start=Date.now();
 m.session={
  name,phone,
  package:pack.name,
  start,
  end:start+pack.hours*3600000,
  price:m.price,
  notified:false
 };
 let customer=customers.find(x=>x.phone&&x.phone===phone);
 if(!customer) {
  customers.push({name,phone,visits:1});
 } else {
  customer.name=name;
  customer.visits++;
 }
 // Nyalakan TV terkait melalui fungsi kontrol
 let tv=televisions.find(x=>x.machine===id);
 if(tv) controlTV(tv.id,"on");
 save();
 renderAll();
}
// AKHIRI RENTAL
function stopRental(id) {
 let m=machines.find(x=>x.id===id);
 if(!m?.session)return;
 let s=m.session;
 let elapsed=Date.now()-s.start;
 let total=Math.ceil(elapsed/3600000*s.price);
 if(!confirm(
  "Akhiri rental?\nDurasi: "+clock(elapsed)+
  "\nTotal: "+money(total)
 ))return;
 let sale={
  id:Date.now(),
  date:new Date().toISOString(),
  customer:s.name,
  phone:s.phone,
  machine:m.name,
  type:m.type,
  package:s.package,
  duration:clock(elapsed),
  total,
  operator:currentUser.u
 };
 sales.unshift(sale);
 m.status="free";
 m.session=null;
 // Matikan TV terkait setelah rental selesai
 let tv=televisions.find(x=>x.machine===id);
 if(tv) controlTV(tv.id,"off");
 save();
 renderAll();
 showReceipt(sale);
}
// TIMER
function checkTimers() {
 machines.forEach(m=>{
 let s=m.session;
 if(!s)return;
 let remaining=s.end-Date.now();
 if(remaining<=0&&!s.notified) {
  s.notified=true;
  save();
  if("Notification" in window &&
  Notification.permission==="granted") {
   new Notification("Waktu Rental Habis",{
    body:m.name+" - "+s.name
   });
  } else {
   alert("WAKTU RENTAL HABIS: "+m.name);
  }
 }
 });
}
// MESIN
function renderMachines() {
 let html=machines.map(m=>{
 let s=m.session;
 return `
 <div class="card">
 <h3>${escapeHTML(m.name)}</h3>
 <p>${m.type}</p>
 <p>Tarif: ${money(m.price)}/jam</p>
 <p class="${m.status==="free"?"green":"yellow"}">
 ${m.status==="free"?"TERSEDIA":"DIGUNAKAN"}
 </p>
 ${
 s?`
 <div class="timer" id="timer${m.id}">
 ${clock(s.end-Date.now())}
 </div>
 <p>${escapeHTML(s.name)}</p>
 <p>${s.package}</p>
 <button onclick="stopRental(${m.id})">AKHIRI RENTAL</button>
 `:`
 <button onclick="startRental(${m.id})">MULAI RENTAL</button>
 `
 }
 </div>
 `;
 }).join("");
 machineGrid.innerHTML=html;
 dashboardMachines.innerHTML=html;
 bookMachine.innerHTML=machines.map(m=>
 `<option value="${m.id}">${escapeHTML(m.name)}</option>`
 ).join("");
 newTVMachine.innerHTML=machines.map(m=>
 `<option value="${m.id}">${escapeHTML(m.name)}</option>`
 ).join("");
}
// KONTROL TV
async function controlTV(id,action) {
 let tv=televisions.find(x=>x.id===id);
 if(!tv)return;
 // MODE SIMULASI
 if(settings.tvMode==="simulation") {
  tv.status=action;
  save();
  renderTV();
  alert("Mode simulasi: "+tv.name+
   " berhasil diubah menjadi "+action.toUpperCase());
  return;
 }
 // MODE PERANGKAT NYATA
 // API Bridge harus dibuat dan dikonfigurasi terpisah.
 if(!settings.bridgeUrl) {
  return alert("Alamat API Bridge belum diatur.");
 }
 try {
  let response=await fetch(
   settings.bridgeUrl.replace(/\/$/,"")+"/api/tv/power",
   {
    method:"POST",
    headers:{"Content-Type":"application/json"},
    body:JSON.stringify({
     deviceId:tv.device,
     action:action
    })
   }
  );
  if(!response.ok)throw new Error("Perangkat menolak perintah");
  let result=await response.json();
  if(result.success!==true)
   throw new Error(result.message||"Perintah gagal");
  tv.status=action;
  save();
  renderTV();
  alert("Perintah berhasil dikirim ke "+tv.name);
 } catch(err) {
  alert("Kontrol TV gagal: "+err.message+
  "\nPeriksa koneksi, alamat bridge, dan perangkat TV.");
 }
}
function renderTV() {
 let html=televisions.map(tv=>{
  let machine=machines.find(m=>m.id===tv.machine);
  let volume=Number.isFinite(Number(tv.volume))?Number(tv.volume):20;
  let muted=!!tv.muted;
  return `
  <div class="card tv-card">
   <h3>📺 ${escapeHTML(tv.name)}</h3>
   <p>Terhubung: ${machine?escapeHTML(machine.name):"Tidak ada"}</p>
   <div class="tv-status">
    <span>
     <span class="dot ${tv.status==="on"?"on":tv.status==="off"?"off":"disconnected"}"></span>
     ${tv.status==="on"?"MENYALA":tv.status==="off"?"MATI":"TERPUTUS"}
    </span>
   </div>
   <p class="muted">ID: ${escapeHTML(tv.device)}</p>
   <div class="remote-box">
    <div class="remote-title">REMOTE TV</div>
    <div class="volume-display">
     <span>🔊 Volume</span>
     <strong>${muted?"MUTE":volume+"%"}</strong>
    </div>
    <div class="volume-buttons">
     <button class="volume-down" onclick="volumeTV(${tv.id},'down')">− VOL</button>
     <button class="volume-up" onclick="volumeTV(${tv.id},'up')">+ VOL</button>
    </div>
    <button class="mute-button" onclick="volumeTV(${tv.id},'mute')">${muted?"UNMUTE":"MUTE"}</button>
   </div>
   <button onclick="controlTV(${tv.id},'on')">NYALAKAN TV</button>
   <button style="background:#bd4054" onclick="controlTV(${tv.id},'off')">MATIKAN TV</button>
  </div>
  `;
 }).join("");
 tvGrid.innerHTML=html;
 dashboardTV.innerHTML=html;
}
async function volumeTV(id,action) {
 let tv=televisions.find(x=>x.id===id);
 if(!tv)return;
 const oldVolume=Number.isFinite(Number(tv.volume))?Number(tv.volume):20;
 const oldMuted=!!tv.muted;
 if(action==="up") {
  tv.volume=Math.min(100,oldVolume+5);
  tv.muted=false;
 } else if(action==="down") {
  tv.volume=Math.max(0,oldVolume-5);
 } else if(action==="mute") {
  tv.muted=!oldMuted;
 } else {
  return;
 }
 // Mode simulasi hanya mengubah tampilan aplikasi.
 if(settings.tvMode==="simulation") {
  save();
  renderTV();
  return;
 }
 if(!settings.bridgeUrl) {
  tv.volume=oldVolume;
  tv.muted=oldMuted;
  renderTV();
  return alert("Alamat API Bridge belum diatur.");
 }
 try {
  const response=await fetch(
   settings.bridgeUrl.replace(/\/$/,"")+"/api/tv/volume",
   {
    method:"POST",
    headers:{"Content-Type":"application/json"},
    body:JSON.stringify({
     deviceId:tv.device,
     action:action,
     volume:tv.volume,
     muted:tv.muted
    })
   }
  );
  if(!response.ok)throw new Error("Perangkat menolak perintah");
  const result=await response.json();
  if(result.success!==true)throw new Error(result.message||"Perintah gagal");
  save();
  renderTV();
 } catch(err) {
  tv.volume=oldVolume;
  tv.muted=oldMuted;
  renderTV();
  alert("Kontrol volume gagal: "+err.message+
   "\\nPastikan API Bridge mendukung endpoint /api/tv/volume.");
 }
}
// TAMBAH TV
function addTV() {
 let name=newTVName.value.trim();
 let machine=Number(newTVMachine.value);
 let device=newTVDevice.value.trim();
 if(!name||!device)return alert("Isi nama TV dan ID perangkat");
 if(televisions.some(t=>t.machine===machine))
 return alert("Mesin tersebut sudah memiliki TV");
 televisions.push({
  id:Date.now(),
  name,
  machine,
  device,
  status:"off"
 });
 newTVName.value="";
 newTVDevice.value="";
 save();
 renderAll();
}
// BOOKING
function addBooking() {
 let name=bookName.value.trim();
 let phone=bookPhone.value.trim();
 let machine=Number(bookMachine.value);
 let date=new Date(bookDate.value);
 if(!name||!bookDate.value)
 return alert("Lengkapi data booking");
 if(date<Date.now())
 return alert("Tanggal booking harus di masa depan");
 if(bookings.some(b=>
 b.machine===machine&&
 b.status==="Menunggu"&&
 Math.abs(new Date(b.date)-date)<3600000
 ))return alert("Mesin sudah dibooking pada waktu tersebut");
 bookings.unshift({
  id:Date.now(),
  name,phone,machine,
  date:date.toISOString(),
  status:"Menunggu"
 });
 save();
 renderBookings();
}
function renderBookings() {
 bookingList.innerHTML=bookings.map(b=>`
 <div class="card" style="margin:10px 0">
 <b>${escapeHTML(b.name)}</b>
 <p>${new Date(b.date).toLocaleString("id-ID")}</p>
 <p>Mesin: ${b.machine}</p>
 <p>Status: ${b.status}</p>
 <button onclick="cancelBooking(${b.id})">BATALKAN</button>
 </div>
 `).join("");
}
function cancelBooking(id) {
 let b=bookings.find(x=>x.id===id);
 b.status="Dibatalkan";
 save();
 renderBookings();
}
// PELANGGAN
function addCustomer() {
 let name=customerName.value.trim();
 let phone=customerPhone.value.trim();
 if(!name)return alert("Nama wajib diisi");
 customers.push({name,phone,visits:0});
 save();
 renderCustomers();
 customerName.value="";
 customerPhone.value="";
}
function renderCustomers() {
 customerList.innerHTML=customers.map(c=>`
 <div class="card" style="margin:10px 0">
 <b>${escapeHTML(c.name)}</b>
 <p>${escapeHTML(c.phone)}</p>
 Kunjungan: ${c.visits||0}
 </div>
 `).join("");
}
// LAPORAN
function renderReports() {
 let range=reportFilter.value;
 let now=new Date();
 let list=sales.filter(s=>{
 let d=new Date(s.date);
 if(range==="day")
 return d.toDateString()===now.toDateString();
 if(range==="week")
 return now-d<=7*86400000&&d<=now;
 if(range==="month")
 return d.getMonth()===now.getMonth()&&
 d.getFullYear()===now.getFullYear();
 return true;
 });
 let total=list.reduce((a,b)=>a+b.total,0);
 reportStats.innerHTML=`
 <div class="card">
 Transaksi
 <div class="metric">${list.length}</div>
 </div>
 <div class="card">
 Pendapatan
 <div class="metric">${money(total)}</div>
 </div>
 `;
 salesList.innerHTML=list.map(s=>`
 <tr>
 <td>${new Date(s.date).toLocaleString("id-ID")}</td>
 <td>${escapeHTML(s.customer)}</td>
 <td>${escapeHTML(s.machine)}</td>
 <td>${escapeHTML(s.package)}</td>
 <td>${s.duration}</td>
 <td>${money(s.total)}</td>
 <td><button onclick="showReceipt(${s.id})">CETAK</button></td>
 </tr>
 `).join("");
}
// STRUK
function showReceipt(id) {
 let s=sales.find(x=>x.id===id);
 if(s)makeReceipt(s);
}
function makeReceipt(s) {
 printArea.innerHTML=`
 <div class="receipt">
 <h2 style="text-align:center">
 ${escapeHTML(settings.name)}
 </h2>
 <p style="text-align:center">STRUK RENTAL PS</p>
 <hr>
 <p>No: ${s.id}</p>
 <p>Tanggal: ${new Date(s.date).toLocaleString("id-ID")}</p>
 <p>Pelanggan: ${escapeHTML(s.customer)}</p>
 <p>Mesin: ${escapeHTML(s.machine)}</p>
 <p>Paket: ${escapeHTML(s.package)}</p>
 <p>Durasi: ${s.duration}</p>
 <hr>
 <h3>TOTAL: ${money(s.total)}</h3>
 <p>Operator: ${escapeHTML(s.operator)}</p>
 <hr>
 <p style="text-align:center">TERIMA KASIH!</p>
 <button onclick="window.print()">CETAK STRUK</button>
 </div>
 `;
 printArea.classList.remove("hidden");
}
function showReceiptBySale(s) {
 makeReceipt(s);
}
// PENGATURAN
function addMachine() {
 let name=newMachineName.value.trim();
 if(!name)return alert("Nama mesin wajib diisi");
 machines.push({
  id:Date.now(),
  name,
  type:newType.value,
  price:Number(newPrice.value),
  status:"free",
  session:null
 });
 save();
 renderAll();
 newMachineName.value="";
}
function renderPrices() {
 priceList.innerHTML=machines.map(m=>`
 <div class="card" style="margin:10px 0">
 <b>${escapeHTML(m.name)}</b>
 <input id="price${m.id}" type="number" value="${m.price}">
 <button onclick="updatePrice(${m.id})">UBAH HARGA</button>
 </div>
 `).join("");
}
function updatePrice(id) {
 let m=machines.find(x=>x.id===id);
 m.price=Math.max(0,Number(document.getElementById("price"+id).value));
 save();
 renderAll();
}
function addStaff() {
 if(currentUser?.role!=="Admin")
 return alert("Hanya admin yang dapat menambah karyawan");
 let u=staffUser.value.trim();
 let p=staffPass.value;
 if(!u||!p)return alert("Lengkapi akun");
 if(users.some(x=>x.u===u))
 return alert("Username sudah digunakan");
 users.push({u,p,role:"Karyawan"});
 save();
 renderStaff();
 staffUser.value="";
 staffPass.value="";
}
function renderStaff() {
 staffList.innerHTML=users.map(u=>
 `<p>${escapeHTML(u.u)} - ${u.role}</p>`
 ).join("");
}
// COVER DAN LOGO
function readImage(file) {
 return new Promise((resolve,reject)=>{
  let r=new FileReader();
  r.onload=()=>resolve(r.result);
  r.onerror=reject;
  r.readAsDataURL(file);
 });
}
async function saveAppearance() {
 if(currentUser?.role!=="Admin")
 return alert("Hanya admin yang dapat mengubah tampilan");
 settings.name=shopName.value.trim()||settings.name;
 settings.subtitle=shopSubtitle.value;
 settings.color=themeColor.value;
 let c=coverFile.files[0];
 let l=logoFile.files[0];
 if(c)settings.cover=await readImage(c);
 if(l)settings.logo=await readImage(l);
 save();
 applyAppearance();
 alert("Tampilan berhasil diperbarui");
}
function applyAppearance() {
 document.documentElement.style.setProperty("--accent",settings.color);
 brand.textContent=settings.name;
 if(settings.cover) {
  cover.style.backgroundImage=
  `linear-gradient(#0009,#000b),url("${settings.cover}")`;
 }
 if(settings.logo) {
  logo.src=settings.logo;
  logo.classList.remove("hidden");
 }
 shopName.value=settings.name;
 shopSubtitle.value=settings.subtitle;
 themeColor.value=settings.color;
 tvMode.value=settings.tvMode;
 bridgeUrl.value=settings.bridgeUrl;
}
// MODE KONTROL TV
function saveSettings() {
 if(currentUser?.role!=="Admin")
 return alert("Hanya admin yang dapat mengubah pengaturan");
 settings.tvMode=tvMode.value;
 settings.bridgeUrl=bridgeUrl.value.trim();
 save();
 alert("Pengaturan kontrol TV disimpan");
}
// TAMBAH KARYAWAN DAN MESIN
// BACKUP
function backup() {
 let data={
 settings,users,machines,
 televisions,bookings,customers,sales
 };
 download(
  JSON.stringify(data,null,2),
  "backup-rental-ps.json",
  "application/json"
 );
}
function restore() {
 restoreFile.click();
}
restoreFile.addEventListener("change",function() {
 let file=this.files[0];
 if(!file)return;
 let reader=new FileReader();
 reader.onload=()=>{
 try {
  let d=JSON.parse(reader.result);
  if(!d.settings||!d.machines||!d.televisions)
  throw Error("File backup tidak valid");
  settings=d.settings;
  users=d.users;
  machines=d.machines;
  televisions=d.televisions;
  bookings=d.bookings||[];
  customers=d.customers||[];
  sales=d.sales||[];
  save();
  applyAppearance();
  renderAll();
  alert("Backup berhasil dipulihkan");
 } catch(e) {
  alert("Backup tidak valid");
 }
 };
 reader.readAsText(file);
});
// EXPORT CSV
function exportCSV() {
 let rows=[
 ["Tanggal","Pelanggan","Telepon","Mesin","Paket","Durasi","Total"],
 ...sales.map(s=>[
  s.date,s.customer,s.phone,s.machine,
  s.package,s.duration,s.total
 ])
 ];
 let csv=rows.map(r=>
 r.map(v=>'"'+String(v??"").replaceAll('"','""')+'"').join(';')
 ).join("\r\n");
 download("\ufeff"+csv,"laporan-rental-ps.csv","text/csv");
}
function download(data,name,type) {
 let a=document.createElement("a");
 let url=URL.createObjectURL(
  new Blob([data],{type})
 );
 a.href=url;
 a.download=name;
 a.click();
 URL.revokeObjectURL(url);
}
// DASHBOARD
function renderDashboard() {
 let used=machines.filter(m=>m.status==="busy").length;
 let today=sales.filter(s=>
 new Date(s.date).toDateString()===new Date().toDateString()
 );
 let income=today.reduce((a,b)=>a+b.total,0);
 stats.innerHTML=`
 <div class="card">Total Mesin<div class="metric">${machines.length}</div></div>
 <div class="card">PS Digunakan<div class="metric">${used}</div></div>
 <div class="card">PS Tersedia<div class="metric">${machines.length-used}</div></div>
 <div class="card">Pendapatan Hari Ini<div class="metric">${money(income)}</div></div>
 <div class="card">Jumlah TV<div class="metric">${televisions.length}</div></div>
 <div class="card">TV Menyala<div class="metric">${televisions.filter(t=>t.status==="on").length}</div></div>
 `;
}
// RENDER SEMUA
function renderAll() {
 renderDashboard();
 renderMachines();
 renderTV();
 renderBookings();
 renderCustomers();
 renderReports();
 renderPrices();
 renderStaff();
}
// TIMER DAN NOTIFIKASI
setInterval(()=>{
 if(!currentUser)return;
 machines.forEach(m=>{
 if(!m.session)return;
 let el=document.getElementById("timer"+m.id);
 if(el)el.textContent=clock(m.session.end-Date.now());
 });
 checkTimers();
},1000);
if("Notification" in window&&Notification.permission==="default") {
 Notification.requestPermission();
}
applyAppearance();
</script>
</body>
</html>
