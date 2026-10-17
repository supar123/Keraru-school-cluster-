<!DOCTYPE html>
<html lang="om">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Qaraaruu Cluster School Management System</title>

<style>
*{box-sizing:border-box}
body{
 margin:0;
 font-family:Arial,sans-serif;
 background:#f1f8f4;
 color:#183b2b;
}
button,input,select,textarea{font:inherit}

.login{
 min-height:100vh;
 display:flex;
 align-items:center;
 justify-content:center;
 padding:20px;
 background:linear-gradient(135deg,#045b32,#18a65d);
}
.login-box{
 width:100%;
 max-width:430px;
 background:white;
 padding:30px;
 border-radius:20px;
 box-shadow:0 10px 35px #0005;
 text-align:center;
}
.login-box .logo{font-size:55px}
.login-box h1{color:#08763d;margin:8px 0}
.login-box p{color:#666}
.form{
 width:100%;
 padding:12px;
 margin:6px 0;
 border:1px solid #ccc;
 border-radius:9px;
}
.btn{
 width:100%;
 border:0;
 border-radius:9px;
 padding:13px;
 margin-top:8px;
 background:#08763d;
 color:#fff;
 font-weight:bold;
 cursor:pointer;
}
.btn:hover{background:#045b32}

#app{display:none}

header{
 position:fixed;
 top:0;
 left:0;
 right:0;
 height:65px;
 background:#08763d;
 color:white;
 z-index:20;
 display:flex;
 align-items:center;
 gap:15px;
 padding:0 18px;
}
header h2{
 font-size:18px;
 flex:1;
}
.menu{
 font-size:28px;
 cursor:pointer;
}

.sidebar{
 position:fixed;
 top:65px;
 left:0;
 bottom:0;
 width:270px;
 background:#064b2c;
 color:white;
 padding:12px;
 overflow:auto;
 z-index:15;
}
.sidebar h3{
 color:#bcebd0;
 font-size:13px;
 margin:10px;
}
.sidebar button{
 width:100%;
 border:0;
 background:transparent;
 color:white;
 text-align:left;
 padding:12px;
 margin:2px 0;
 border-radius:8px;
 cursor:pointer;
}
.sidebar button:hover{background:#08763d}

.main{
 margin-left:270px;
 padding:90px 25px 30px;
}
.page{display:none}
.page.active{display:block}

.title{
 color:#08763d;
 margin-bottom:18px;
}

.cards{
 display:grid;
 grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
 gap:15px;
 margin-bottom:20px;
}
.card{
 background:white;
 padding:20px;
 border-radius:14px;
 box-shadow:0 3px 12px #0001;
 border-left:5px solid #08763d;
}
.card h4{color:#666;margin:0 0 8px}
.card strong{font-size:30px;color:#08763d}

.box{
 background:white;
 padding:20px;
 margin-bottom:20px;
 border-radius:14px;
 box-shadow:0 3px 12px #0001;
}

table{
 width:100%;
 border-collapse:collapse;
 margin-top:15px;
}
th,td{
 padding:10px;
 border-bottom:1px solid #ddd;
 text-align:left;
}
th{
 background:#e3f5e9;
 color:#075e35;
}

.add{
 border:0;
 background:#08763d;
 color:white;
 padding:10px 15px;
 border-radius:8px;
 cursor:pointer;
 margin-top:7px;
}

.badge{
 display:inline-block;
 padding:5px 9px;
 border-radius:20px;
 background:#e5f6eb;
 color:#08763d;
 font-size:12px;
}

@media(max-width:750px){
 .sidebar{
   left:-280px;
   transition:.25s;
 }
 .sidebar.open{left:0}
 .main{margin-left:0;padding:85px 12px 25px}
 header h2{font-size:14px}
 .cards{grid-template-columns:repeat(2,1fr)}
 .card{padding:14px}
 .card strong{font-size:23px}
 table{font-size:12px}
 th,td{padding:7px}
}
</style>
</head>

<body>

<!-- ================= LOGIN ================= -->

<div class="login" id="loginPage">
<div class="login-box">

<div class="logo">🏫</div>

<h1>Qaraaruu Cluster</h1>
<p>School Management System</p>

<select class="form" id="role">
<option>Admin / Supervisor</option>
<option>Dura Bu'aa Mana Barumsaa</option>
<option>Barsiisaa</option>
</select>

<input class="form" id="username" placeholder="Username">

<input class="form" id="password" type="password"
placeholder="Password">

<button class="btn" onclick="login()">SEENI / LOGIN</button>

<p style="font-size:13px">
Username: <b>admin</b><br>
Password: <b>1234</b>
</p>

</div>
</div>


<!-- ================= APP ================= -->

<div id="app">

<header>
<div class="menu" onclick="toggleMenu()">☰</div>
<h2>🏫 Qaraaruu Cluster School Management System</h2>
<div id="currentRole">Admin</div>
</header>


<!-- ================= SIDEBAR ================= -->

<div class="sidebar" id="sidebar">

<h3>MAIN MENU</h3><button onclick="show('dashboard')">🏠 Dashboard</button>

<button onclick="show('schools')">
🏫 Manneen Barnootaa
</button>

<button onclick="show('leaders')">
👨‍💼 Dura Bu'oota Manneen Barnootaa
</button>

<button onclick="show('phones')">
📞 Lakkoofsa Bilbilaa
</button>

<button onclick="show('plans')">
📝 Karooraalee Mana Barumsaa
</button>

<button onclick="show('monthly')">
📊 Gabaasa Ji'aa
</button>

<button onclick="show('teachers')">
👨‍🏫 Ragaa Barsiisaa Waliigalaa
</button>

<button onclick="show('students')">
👨‍🎓 Ragaa Cuunfaa Barattootaa
</button>

<button onclick="show('attendance')">
📋 Hordoffii Argamaa
</button>

<button onclick="show('assessment')">
📝 Madaallii / Qabxii
</button>

<button onclick="show('grades')">
📚 Kutaalee 1–8
</button>

<button onclick="show('reports')">
📈 Gabaasa Kilaastaraa
</button>

<button onclick="show('settings')">
⚙️ Qindaa'ina
</button>

<button onclick="logout()">🚪 Ba'i</button>

</div>


<!-- ================= MAIN ================= -->

<main class="main">


<!-- DASHBOARD -->

<section id="dashboard" class="page active">

<h1 class="title">🏠 Dashboard</h1>

<div class="cards">

<div class="card">
<h4>Manneen Barnootaa</h4>
<strong id="schoolCount">0</strong>
</div>

<div class="card">
<h4>Dura Bu'oota</h4>
<strong id="leaderCount">0</strong>
</div>

<div class="card">
<h4>Barsiisota</h4>
<strong id="teacherCount">0</strong>
</div>

<div class="card">
<h4>Barattoota</h4>
<strong id="studentCount">0</strong>
</div>

<div class="card">
<h4>Kutaalee</h4>
<strong>8</strong>
</div>

<div class="card">
<h4>Present Har'a</h4>
<strong id="presentCount">0</strong>
</div>

</div>

<div class="box">

<h2>📢 Beeksisa Kilaastaraa</h2>

<p style="margin-top:12px">
Qulqullina barnootaa, hordoffii barsiisotaa,
karoora mana barumsaa fi milkaa'ina barattootaa
tokkummaan haa cimsinu.
</p>

</div>
</section>


<!-- SCHOOLS -->

<section id="schools" class="page">

<h1 class="title">🏫 Manneen Barnootaa Kilaastaraa</h1>

<div class="box">

<input class="form" id="schoolName"
placeholder="Maqaa Mana Barumsaa">

<input class="form" id="schoolLeader"
placeholder="Maqaa Dura Bu'aa">

<input class="form" id="schoolPhone"
placeholder="Lakkoofsa Bilbilaa">

<button class="add" onclick="addSchool()">
+ Mana Barumsaa Dabali
</button>

<table>
<thead>
<tr>
<th>#</th>
<th>Mana Barumsaa</th>
<th>Dura Bu'aa</th>
<th>Bilbila</th>
</tr>
</thead>
<tbody id="schoolTable"></tbody>
</table>

</div>
</section>


<!-- LEADERS -->

<section id="leaders" class="page">

<h1 class="title">
👨‍💼 Dura Bu'oota Manneen Barnootaa
</h1>

<div class="box">

<input class="form" id="leaderName"
placeholder="Maqaa Dura Bu'aa">

<input class="form" id="leaderSchool"
placeholder="Maqaa Mana Barumsaa">

<input class="form" id="leaderPhone"
placeholder="Lakkoofsa Bilbilaa">

<button class="add" onclick="addLeader()">
+ Dura Bu'aa Dabali
</button>

<table>
<thead>
<tr>
<th>#</th>
<th>Maqaa</th>
<th>Mana Barumsaa</th>
<th>Bilbila</th>
</tr>
</thead>
<tbody id="leaderTable"></tbody>
</table>

</div>
</section>


<!-- PHONES -->

<section id="phones" class="page">

<h1 class="title">📞 Lakkoofsa Bilbilaa</h1>

<div class="box">

<table>
<thead>
<tr>
<th>#</th>
<th>Maqaa</th>
<th>Gahee</th>
<th>Mana Barumsaa</th>
<th>Bilbila</th>
</tr>
</thead>

<tbody id="phoneTable"></tbody>

</table>

</div>
</section>


<!-- SCHOOL PLANS -->

<section id="plans" class="page">

<h1 class="title">📝 Karooraalee Mana Barumsaa</h1>

<div class="box">

<select class="form" id="planSchool">
<option>Mana Barumsaa Filadhu</option>
</select>

<select class="form">
<option>Karoora Waggaa</option>
<option>Karoora Ji'aa</option>
<option>Karoora Torbee</option>
</select>

<textarea class="form"
style="height:140px"
placeholder="Karoora mana barumsaa asitti galchi..."></textarea>

<button class="add">
💾 Karoora Olkaa'i
</button>

</div>
</section>


<!-- MONTHLY REPORT -->

<section id="monthly" class="page">

<h1 class="title">📊 Gabaasa Ji'aa</h1>

<div class="box"><select class="form">
<option>Ji'a 1</option>
<option>Ji'a 2</option>
<option>Ji'a 3</option>
<option>Ji'a 4</option>
<option>Ji'a 5</option>
<option>Ji'a 6</option>
<option>Ji'a 7</option>
<option>Ji'a 8</option>
<option>Ji'a 9</option>
<option>Ji'a 10</option>
<option>Ji'a 11</option>
<option>Ji'a 12</option>
</select>

<table>
<thead>
<tr>
<th>Mana Barumsaa</th>
<th>Barattoota</th>
<th>Barsiisota</th>
<th>Argama</th>
<th>Gabaasa</th>
</tr>
</thead>

<tbody>
<tr>
<td>Fakkeenya Mana Barumsaa</td>
<td>0</td>
<td>0</td>
<td><span class="badge">0%</span></td>
<td>Qophaa'e</td>
</tr>
</tbody>
</table>

<br>

<button class="add" onclick="window.print()">
🖨️ Gabaasa Ji'aa Maxxansi
</button>

</div>
</section>


<!-- TEACHERS -->

<section id="teachers" class="page">

<h1 class="title">
👨‍🏫 Ragaa Barsiisaa Waliigalaa
</h1>

<div class="box">

<input class="form" id="teacherName"
placeholder="Maqaa Guutuu">

<input class="form" id="teacherCode"
placeholder="Teacher Code / ID">

<input class="form" id="teacherSubject"
placeholder="Gosa Barnootaa">

<input class="form" id="teacherQualification"
placeholder="Qualification">

<input class="form" id="teacherPhone"
placeholder="Lakkoofsa Bilbilaa">

<input class="form" id="teacherSchool"
placeholder="Mana Barumsaa">

<button class="add" onclick="addTeacher()">
+ Barsiisaa Galchi
</button>

<table>
<thead>
<tr>
<th>#</th>
<th>Maqaa</th>
<th>Code</th>
<th>Barnoota</th>
<th>Qualification</th>
<th>Bilbila</th>
<th>Mana Barumsaa</th>
</tr>
</thead>

<tbody id="teacherTable"></tbody>

</table>

</div>
</section>


<!-- STUDENTS -->

<section id="students" class="page">

<h1 class="title">
👨‍🎓 Ragaa Cuunfaa Barattootaa
</h1>

<div class="box">

<input class="form" id="studentName"
placeholder="Maqaa Barataa">

<select class="form" id="studentGrade">
<option value="">Kutaa Filadhu</option>
<option>Kutaa 1</option>
<option>Kutaa 2</option>
<option>Kutaa 3</option>
<option>Kutaa 4</option>
<option>Kutaa 5</option>
<option>Kutaa 6</option>
<option>Kutaa 7</option>
<option>Kutaa 8</option>
</select>

<select class="form" id="studentGender">
<option value="">Saala</option>
<option>Dhiira</option>
<option>Dubara</option>
</select>

<input class="form" id="studentSchool"
placeholder="Mana Barumsaa">

<button class="add" onclick="addStudent()">
+ Barataa Galchi
</button>

<table>
<thead>
<tr>
<th>#</th>
<th>Maqaa</th>
<th>Kutaa</th>
<th>Saala</th>
<th>Mana Barumsaa</th>
</tr>
</thead>

<tbody id="studentTable"></tbody>

</table>

</div>
</section>


<!-- ATTENDANCE -->

<section id="attendance" class="page">

<h1 class="title">📋 Hordoffii Argamaa</h1>

<div class="box">

<table>
<thead>
<tr>
<th>Barataa</th>
<th>Kutaa</th>
<th>Mana Barumsaa</th>
<th>Haala</th>
</tr>
</thead>

<tbody id="attendanceTable">

<tr>
<td>Barataa Fakkeenya</td>
<td>8</td>
<td>Barihee</td>
<td>
<select onchange="attendanceChange(this)">
<option>Present</option>
<option>Absent</option>
</select>
</td>
</tr>

</tbody>
</table>

</div>
</section>


<!-- ASSESSMENT -->

<section id="assessment" class="page">

<h1 class="title">📝 Madaallii / Qabxii</h1>

<div class="box">

<table>
<thead>
<tr>
<th>Barataa</th>
<th>Gosa Barnootaa</th>
<th>Kutaa</th>
<th>Qabxii</th>
</tr>
</thead>

<tbody>

<tr>
<td>Barataa Fakkeenya</td>
<td>Afaan Oromoo</td>
<td>8</td>
<td>
<input class="form" type="number" min="0" max="100">
</td>
</tr>

<tr>
<td>Barataa Fakkeenya</td>
<td>Herrega</td>
<td>8</td>
<td>
<input class="form" type="number" min="0" max="100">
</td>
</tr>

</tbody>
</table>

</div>
</section>


<!-- GRADES -->

<section id="grades" class="page">

<h1 class="title">📚 Kutaalee 1–8</h1>

<div class="cards">

<div class="card">Kutaa 1<br><strong>1</strong></div>
<div class="card">Kutaa 2<br><strong>2</strong></div>
<div class="card">Kutaa 3<br><strong>3</st<select class="form">
<option>Ji'a 1</option>
<option>Ji'a 2</option>
<option>Ji'a 3</option>
<option>Ji'a 4</option>
<option>Ji'a 5</option>
<option>Ji'a 6</option>
<option>Ji'a 7</option>
<option>Ji'a 8</option>
<option>Ji'a 9</option>
<option>Ji'a 10</option>
<option>Ji'a 11</option>
<option>Ji'a 12</option>
</select>

<table>
<thead>
<tr>
<th>Mana Barumsaa</th>
<th>Barattoota</th>
<th>Barsiisota</th>
<th>Argama</th>
<th>Gabaasa</th>
</tr>
</thead>

<tbody>
<tr>
<td>Fakkeenya Mana Barumsaa</td>
<td>0</td>
<td>0</td>
<td><span class="badge">0%</span></td>
<td>Qophaa'e</td>
</tr>
</tbody>
</table>

<br>

<button class="add" onclick="window.print()">
🖨️ Gabaasa Ji'aa Maxxansi
</button>

</div>
</section>


<!-- TEACHERS -->

<section id="teachers" class="page">

<h1 class="title">
👨‍🏫 Ragaa Barsiisaa Waliigalaa
</h1>

<div class="box">

<input class="form" id="teacherName"
placeholder="Maqaa Guutuu">

<input class="form" id="teacherCode"
placeholder="Teacher Code / ID">

<input class="form" id="teacherSubject"
placeholder="Gosa Barnootaa">

<input class="form" id="teacherQualification"
placeholder="Qualification">

<input class="form" id="teacherPhone"
placeholder="Lakkoofsa Bilbilaa">

<input class="form" id="teacherSchool"
placeholder="Mana Barumsaa">

<button class="add" onclick="addTeacher()">
+ Barsiisaa Galchi
</button>

<table>
<thead>
<tr>
<th>#</th>
<th>Maqaa</th>
<th>Code</th>
<th>Barnoota</th>
<th>Qualification</th>
<th>Bilbila</th>
<th>Mana Barumsaa</th>
</tr>
</thead>

<tbody id="teacherTable"></tbody>

</table>

</div>
</section>


<!-- STUDENTS -->

<section id="students" class="page">

<h1 class="title">
👨‍🎓 Ragaa Cuunfaa Barattootaa
</h1>

<div class="box">

<input class="form" id="studentName"
placeholder="Maqaa Barataa">

<select class="form" id="studentGrade">
<option value="">Kutaa Filadhu</option>
<option>Kutaa 1</option>
<option>Kutaa 2</option>
<option>Kutaa 3</option>
<option>Kutaa 4</option>
<option>Kutaa 5</option>
<option>Kutaa 6</option>
<option>Kutaa 7</option>
<option>Kutaa 8</option>
</select>

<select class="form" id="studentGender">
<option value="">Saala</option>
<option>Dhiira</option>
<option>Dubara</option>
</select>

<input class="form" id="studentSchool"
placeholder="Mana Barumsaa">

<button class="add" onclick="addStudent()">
+ Barataa Galchi
</button>

<table>
<thead>
<tr>
<th>#</th>
<th>Maqaa</th>
<th>Kutaa</th>
<th>Saala</th>
<th>Mana Barumsaa</th>
</tr>
</thead>

<tbody id="studentTable"></tbody>

</table>

</div>
</section>


<!-- ATTENDANCE -->

<section id="attendance" class="page">

<h1 class="title">📋 Hordoffii Argamaa</h1>

<div class="box">

<table>
<thead>
<tr>
<th>Barataa</th>
<th>Kutaa</th>
<th>Mana Barumsaa</th>
<th>Haala</th>
</tr>
</thead>

<tbody id="attendanceTable">

<tr>
<td>Barataa Fakkeenya</td>
<td>8</td>
<td>Barihee</td>
<td>
<select onchange="attendanceChange(this)">
<option>Present</option>
<option>Absent</option>
</select>
</td>
</tr>

</tbody>
</table>

</div>
</section>


<!-- ASSESSMENT -->

<section id="assessment" class="page">

<h1 class="title">📝 Madaallii / Qabxii</h1>

<div class="box">

<table>
<thead>
<tr>
<th>Barataa</th>
<th>Gosa Barnootaa</th>
<th>Kutaa</th>
<th>Qabxii</th>
</tr>
</thead>

<tbody>

<tr>
<td>Barataa Fakkeenya</td>
<td>Afaan Oromoo</td>
<td>8</td>
<td>
<input class="form" type="number" min="0" max="100">
</td>
</tr>

<tr>
<td>Barataa Fakkeenya</td>
<td>Herrega</td>
<td>8</td>
<td>
<input class="form" type="number" min="0" max="100">
</td>
</tr>

</tbody>
</table>

</div>
</section>


<!-- GRADES -->

<section id="grades" class="page">

<h1 class="title">📚 Kutaalee 1–8</h1>

<div class="cards">

<div class="card">Kutaa 1<br><strong>1</strong></div>
<div class="card">Kutaa 2<br><strong>2</strong></div>
<div class="card">Kutaa 3<br><strong>3</strong></d<div class="card">Kutaa 4<br><strong>4</strong></div>
<div class="card">Kutaa 5<br><strong>5</strong></div>
<div class="card">Kutaa 6<br><strong>6</strong></div>
<div class="card">Kutaa 7<br><strong>7</strong></div>
<div class="card">Kutaa 8<br><strong>8</strong></div>

</div>
</section>


<!-- REPORTS -->

<section id="reports" class="page">

<h1 class="title">📈 Gabaasa Kilaastaraa</h1>

<div class="cards">

<div class="card">
<h4>Manneen Barnootaa</h4>
<strong id="rSchools">0</strong>
</div>

<div class="card">
<h4>Barsiisota</h4>
<strong id="rTeachers">0</strong>
</div>

<div class="card">
<h4>Barattoota</h4>
<strong id="rStudents">0</strong>
</div>

<div class="card">
<h4>Dura Bu'oota</h4>
<strong id="rLeaders">0</strong>
</div>

</div>

<div class="box">

<h3>Cuunfaa Kilaastaraa</h3>

<table>
<tr>
<th>Ragaa</th>
<th>Baay'ina</th>
</tr>
<tr>
<td>Manneen Barnootaa</td>
<td id="rr1">0</td>
</tr>
<tr>
<td>Barsiisota</td>
<td id="rr2">0</td>
</tr>
<tr>
<td>Barattoota</td>
<td id="rr3">0</td>
</tr>
<tr>
<td>Dura Bu'oota</td>
<td id="rr4">0</td>
</tr>
</table>

<br>

<button class="add" onclick="window.print()">
🖨️ Gabaasa Maxxansi
</button>

</div>
</section>


<!-- SETTINGS -->

<section id="settings" class="page">

<h1 class="title">⚙️ Qindaa'ina</h1>

<div class="box">

<h2>Qaraaruu Cluster School Management System</h2>

<p style="margin-top:15px">
Sirna bulchiinsa mana barumsaa kilaastaraa:
manneen barnootaa, dura bu'oota, barsiisota,
barattoota, karooraalee fi gabaasa hordofuuf.
</p>

<br>

<b>Software Developer:</b>
<p>Ahmed Mume</p>

</div>
</section>


</main>
</div>


<script>

/* DATA */

let schools=[];
let leaders=[];
let teachers=[];
let students=[];
let present=0;


/* LOGIN */

function login(){

let u=document.getElementById("username").value.trim();
let p=document.getElementById("password").value.trim();
let role=document.getElementById("role").value;

if(u==="admin" && p==="1234"){

document.getElementById("loginPage").style.display="none";
document.getElementById("app").style.display="block";
document.getElementById("currentRole").innerText=role;

}else{
alert("Username ykn Password sirrii miti!");
}

}

function logout(){
location.reload();
}


/* NAVIGATION */

function show(id){

document.querySelectorAll(".page")
.forEach(x=>x.classList.remove("active"));

document.getElementById(id)
.classList.add("active");

document.getElementById("sidebar")
.classList.remove("open");

}

function toggleMenu(){
document.getElementById("sidebar")
.classList.toggle("open");
}


/* SCHOOL */

function addSchool(){

let name=document.getElementById("schoolName").value;
let leader=document.getElementById("schoolLeader").value;
let phone=document.getElementById("schoolPhone").value;

if(!name){
alert("Maqaa mana barumsaa galchi!");
return;
}

schools.push({name,leader,phone});

renderSchools();

document.getElementById("schoolName").value="";
document.getElementById("schoolLeader").value="";
document.getElementById("schoolPhone").value="";

}


function renderSchools(){

let t=document.getElementById("schoolTable");
t.innerHTML="";

schools.forEach((x,i)=>{
t.innerHTML+=
<tr>
<td>${i+1}</td>
<td>${x.name}</td>
<td>${x.leader}</td>
<td>${x.phone}</td>
</tr>;
});

document.getElementById("schoolCount").innerText=schools.length;
document.getElementById("rSchools").innerText=schools.length;
document.getElementById("rr1").innerText=schools.length;

}


/* LEADERS */

function addLeader(){

let name=document.getElementById("leaderName").value;
let school=document.getElementById("leaderSchool").value;
let phone=document.getElementById("leaderPhone").value;

if(!name){
alert("Maqaa dura bu'aa galchi!");
return;
}

leaders.push({name,school,phone});

let t=document.getElementById("leaderTable");
t.innerHTML="";

leaders.forEach((x,i)=>{
t.innerHTML+=
<tr>
<td>${i+1}</td>
<td>${x.name}</td>
<td>${x.school}</td>
<td>${x.phone}</td>
</tr>;
});iv>rong></div>document.getElementById("leaderCount").innerText=leaders.length;
document.getElementById("rLeaders").innerText=leaders.length;
document.getElementById("rr4").innerText=leaders.length;

renderPhones();

}


/* PHONE DIRECTORY */

function renderPhones(){

let t=document.getElementById("phoneTable");
t.innerHTML="";

leaders.forEach((x,i)=>{
t.innerHTML+=
<tr>
<td>${i+1}</td>
<td>${x.name}</td>
<td>Dura Bu'aa</td>
<td>${x.school}</td>
<td>${x.phone}</td>
</tr>;
});

teachers.forEach((x,i)=>{
t.innerHTML+=
<tr>
<td>${leaders.length+i+1}</td>
<td>${x.name}</td>
<td>Barsiisaa</td>
<td>${x.school}</td>
<td>${x.phone}</td>
</tr>;
});

}


/* TEACHERS */

function addTeacher(){

let name=document.getElementById("teacherName").value;
let code=document.getElementById("teacherCode").value;
let subject=document.getElementById("teacherSubject").value;
let qualification=document.getElementById("teacherQualification").value;
let phone=document.getElementById("teacherPhone").value;
let school=document.getElementById("teacherSchool").value;

if(!name){
alert("Maqaa barsiisaa galchi!");
return;
}

teachers.push({
name,code,subject,qualification,phone,school
});

let t=document.getElementById("teacherTable");
t.innerHTML="";

teachers.forEach((x,i)=>{
t.innerHTML+=
<tr>
<td>${i+1}</td>
<td>${x.name}</td>
<td>${x.code}</td>
<td>${x.subject}</td>
<td>${x.qualification}</td>
<td>${x.phone}</td>
<td>${x.school}</td>
</tr>;
});

document.getElementById("teacherCount").innerText=teachers.length;
document.getElementById("rTeachers").innerText=teachers.length;
document.getElementById("rr2").innerText=teachers.length;

renderPhones();

}


/* STUDENTS */

function addStudent(){

let name=document.getElementById("studentName").value;
let grade=document.getElementById("studentGrade").value;
let gender=document.getElementById("studentGender").value;
let school=document.getElementById("studentSchool").value;

if(!name || !grade){
alert("Maqaa fi kutaa guuti!");
return;
}

students.push({name,grade,gender,school});

let t=document.getElementById("studentTable");
t.innerHTML="";

students.forEach((x,i)=>{
t.innerHTML+=
<tr>
<td>${i+1}</td>
<td>${x.name}</td>
<td>${x.grade}</td>
<td>${x.gender}</td>
<td>${x.school}</td>
</tr>;
});

document.getElementById("studentCount").innerText=students.length;
document.getElementById("rStudents").innerText=students.length;
document.getElementById("rr3").innerText=students.length;

}


/* ATTENDANCE */

function attendanceChange(select){

if(select.value==="Present") present++;
else present--;

if(present<0) present=0;

document.getElementById("presentCount").innerText=present;

}

</script>

</body>
</html>
