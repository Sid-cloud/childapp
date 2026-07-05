# childapp
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>DPDP Consent Prototype</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
background:#f4f7fb;
}

.container{
max-width:420px;
margin:40px auto;
background:white;
border-radius:12px;
box-shadow:0 8px 25px rgba(0,0,0,.15);
overflow:hidden;
}

.header{
background:#1976d2;
color:white;
padding:20px;
font-size:22px;
font-weight:bold;
text-align:center;
}

.screen{
display:none;
padding:25px;
}

.active{
display:block;
}

h2{
margin-bottom:15px;
}

p{
color:#555;
margin-bottom:20px;
line-height:1.5;
}

input{
width:100%;
padding:12px;
margin-top:10px;
margin-bottom:20px;
font-size:16px;
}

button{
width:100%;
padding:14px;
background:#1976d2;
border:none;
color:white;
font-size:16px;
border-radius:8px;
cursor:pointer;
margin-top:10px;
}

button:hover{
background:#125ea7;
}

.card{
padding:15px;
border:1px solid #ddd;
margin-bottom:15px;
border-radius:8px;
}

.switch{
display:flex;
justify-content:space-between;
align-items:center;
margin:15px 0;
}

input[type=checkbox]{
width:auto;
transform:scale(1.3);
}

.success{
text-align:center;
font-size:20px;
color:green;
margin:25px 0;
}

.list{
padding-left:20px;
margin-bottom:20px;
}

.tag{
display:inline-block;
background:#e8f3ff;
padding:6px 10px;
border-radius:20px;
margin:4px;
font-size:13px;
}

</style>

</head>
<body>

<div class="container">

<div class="header">
Vedantu Privacy Prototype
</div>

<!-- SCREEN 1 -->

<div class="screen active" id="s1">

<h2>Create Child Profile</h2>

<p>
India's DPDP Act requires verifiable parental consent before processing children's personal data.
</p>

<label>Child Name</label>
<input placeholder="Enter Name">

<label>Child Age</label>
<input id="age" type="number" placeholder="Enter Age">

<button onclick="next1()">Continue</button>

</div>

<!-- SCREEN 2 -->

<div class="screen" id="s2">

<h2>Parent Verification</h2>

<p>

Verify parent identity before activating the child profile.

</p>

<div class="card">

<input placeholder="Parent Mobile Number">

<button onclick="alert('OTP Sent')">
Send OTP
</button>

</div>

<div class="card">

<button onclick="alert('DigiLocker Connected')">
Verify using DigiLocker
</button>

</div>

<button onclick="showScreen(3)">
Verification Complete
</button>

</div>

<!-- SCREEN 3 -->

<div class="screen" id="s3">

<h2>Consent by Purpose</h2>

<p>

Choose what data Vedantu may use.

</p>

<div class="switch">
Learning Personalization
<input type="checkbox" checked>
</div>

<div class="switch">
Progress Analytics
<input type="checkbox">
</div>

<div class="switch">
Notifications
<input type="checkbox">
</div>

<div class="switch">
Marketing
<input type="checkbox">
</div>

<button onclick="showScreen(4)">
Save Consent
</button>

</div>

<!-- SCREEN 4 -->

<div class="screen" id="s4">

<h2>Child Home</h2>

<p>

Privacy-first recommendations.

</p>

<span class="tag">Math</span>
<span class="tag">Science</span>
<span class="tag">Olympiad</span>
<span class="tag">Class 8</span>

<div class="card">

<b>Privacy Status</b>

<ul class="list">

<li>No behavioural profiling</li>

<li>No targeted advertising</li>

<li>Contextual recommendations only</li>

</ul>

</div>

<button onclick="showScreen(5)">
Parent Dashboard
</button>

</div>

<!-- SCREEN 5 -->

<div class="screen" id="s5">

<h2>Parent Privacy Dashboard</h2>

<div class="card">

<b>Consent Status</b>

<p>Verified Parent</p>

</div>

<div class="card">

<button onclick="alert('Consent Revoked')">

Revoke Consent

</button>

<button onclick="alert('Downloading Data')">

Download Child Data

</button>

<button onclick="alert('Profile Deleted')">

Delete Child Profile

</button>

</div>

<div class="success">

✓ DPDP Compliance Complete

</div>

</div>

</div>

<script>

function showScreen(num){

document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active"));

document.getElementById("s"+num).classList.add("active");

}

function next1(){

let age=document.getElementById("age").value;

if(age===""){

alert("Please enter age");

return;

}

if(age<18){

showScreen(2);

}else{

showScreen(4);

}

}

</script>

</body>
</html>
