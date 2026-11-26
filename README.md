<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Student Projects | Share &amp; Explore</title>

<style>
*{margin:0;padding:0;box-sizing:border-box}
body{
 font-family:Arial,sans-serif;
 background:#f4f6fb;
 color:#172033;
 min-height:100vh;
 display:flex;
 flex-direction:column;
}
header{
 background:linear-gradient(120deg,#111b40,#5145b9);
 color:white;padding:25px 7%;
 display:flex;justify-content:space-between;
 align-items:center;flex-wrap:wrap;gap:15px;
}
.logo{font-size:27px;font-weight:900;letter-spacing:1px;cursor:pointer}
.logo span{color:#a9b4ff}
nav{display:flex;gap:10px;flex-wrap:wrap}
button{
 border:0;padding:11px 17px;border-radius:9px;
 cursor:pointer;font-weight:bold;font-size:14px;
 transition:.2s;
}
button:hover{opacity:.85;transform:translateY(-1px)}
.navbtn{background:#ffffff20;color:white}
.primary{background:#5145d9;color:white}
.secondary{background:#e8eaff;color:#4036a5}
.danger{background:#ffe5e5;color:#c62828}
.link-btn{
 background:none;border:0;padding:0 4px;
 color:#5145d9;font-weight:bold;font-size:14px;
 text-decoration:underline;cursor:pointer;
}
.link-btn:hover{opacity:.8;transform:none}
.container{max-width:1100px;width:100%;margin:auto;padding:30px 18px;flex:1}
.hero{
 background:linear-gradient(120deg,#18244f,#6555d9);
 color:white;padding:45px 30px;border-radius:20px;
 margin-bottom:30px;
}
.hero h1{font-size:36px;margin-bottom:12px}
.hero p{color:#dce1ff;line-height:1.6}
.hero-actions{margin-top:22px;display:flex;gap:10px;flex-wrap:wrap}
.section-title{font-size:25px;margin:25px 0 18px}
.grid{
 display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));
 gap:18px;
}
.card{
 background:white;border-radius:15px;padding:23px;
 box-shadow:0 4px 18px #1720330b;
 border:1px solid #e9ebf3;
}
.year-card{cursor:pointer;transition:.2s}
.year-card:hover{transform:translateY(-5px);border-color:#6256d9}
.year-card h2{color:#4036b2;margin:12px 0}
.year-card p{color:#737b90;line-height:1.5;margin-bottom:16px}
.icon{font-size:32px}
.hidden{display:none!important}
input,textarea,select{
 width:100%;padding:13px;margin:9px 0 15px;
 border:1px solid #dce0eb;border-radius:9px;
 font-size:15px;outline:none;background:white;
}
input:focus,textarea:focus,select:focus{border-color:#6555d9}
label{font-weight:bold;font-size:14px}
.form-box{max-width:470px;margin:25px auto}
.form-box h2{margin-bottom:20px}
.semester{
 cursor:pointer;text-align:left;
 padding:20px;border:1px solid #e6e7f1;
 background:white;border-radius:12px;
}
.semester:hover{border-color:#6555d9}
.project-card{padding:0;overflow:hidden}
.project-card img{
 width:100%;height:180px;object-fit:cover;
 background:#eee;display:block;
}
.project-content{padding:18px}
.project-content h3{margin-bottom:8px}
.project-content p{color:#6e7585;line-height:1.5;white-space:pre-wrap}
.tag{
 display:inline-block;background:#ecebff;color:#5045bd;
 padding:6px 10px;border-radius:20px;
 font-size:12px;margin:9px 0;
}
.meta{font-size:12px;color:#9299a9;margin-top:12px}
.actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:14px}
.actions button{font-size:12px}
.topline{
 display:flex;justify-content:space-between;
 align-items:center;gap:10px;flex-wrap:wrap;
}
.empty{
 text-align:center;padding:45px 15px;color:#8a91a2;
 background:white;border-radius:15px;
 border:1px solid #e9ebf3;
}
footer{
 text-align:center;padding:25px;color:#888;
 margin-top:40px;border-top:1px solid #e5e7ef;
}
.message{color:#c0392b;font-size:13px;margin:5px 0 12px;min-height:18px}
.toast{
 position:fixed;bottom:24px;right:24px;z-index:1000;
 background:#172033;color:white;padding:13px 20px;
 border-radius:10px;font-size:14px;font-weight:bold;
 box-shadow:0 8px 24px rgba(23,32,51,.25);
 transition:opacity .25s,transform .25s;
}
.toast.success{background:#1b7f4b}
.modal-backdrop{
 position:fixed;inset:0;z-index:999;
 background:rgba(17,27,64,.5);
 display:flex;align-items:center;justify-content:center;padding:18px;
}
.modal-box{
 background:white;border-radius:15px;padding:24px;
 max-width:380px;width:100%;
 box-shadow:0 12px 32px rgba(17,27,64,.25);
}
.modal-box h3{margin-bottom:10px;color:#172033}
.modal-box p{color:#5e667a;font-size:14px;line-height:1.5;margin-bottom:20px}
.modal-actions{display:flex;justify-content:flex-end;gap:10px}
@media(max-width:600px){
 .hero h1{font-size:27px}
 header{padding:20px}
 .logo{font-size:22px}
}
</style>
</head>

<body>

<header>
 <div class="logo" onclick="showPage('home')">STUDENT <span>PROJECTS.</span></div>
 <nav id="navigation">
  <button type="button" class="navbtn" onclick="showPage('home')">Home</button>
  <button type="button" class="navbtn" onclick="explore()">Explore Projects</button>
  <button type="button" class="navbtn" onclick="openAuth('login')" id="loginNav">Login</button>
  <button type="button" class="navbtn hidden" onclick="myProjects()" id="myNav">My Projects</button>
  <button type="button" class="navbtn hidden" onclick="logout()" id="logoutNav">Logout</button>
 </nav>
</header>

<main class="container">

<!-- HOME -->
<section id="home">
 <div class="hero">
  <h1>Welcome to Student Projects</h1>
  <p>Discover, Upload and Explore Student Projects.<br>
  A platform where students share their creativity and ideas.</p>
  <div class="hero-actions">
   <button type="button" class="primary" onclick="explore()">Explore Projects</button>
   <button type="button" class="navbtn" onclick="startUpload()">Upload Your Project</button>
  </div>
 </div>

 <h2 class="section-title">Upload Projects</h2>
 <div class="grid">
  <div class="card year-card" onclick="openYear(2)">
   <div class="icon">📘</div>
   <h2>Second Year</h2>
   <p>Explore and upload projects from Third and Fourth Semester.</p>
   <button type="button" class="primary" onclick="event.stopPropagation();openYear(2)">Open Second Year →</button>
  </div>

  <div class="card year-card" onclick="openYear(3)">
   <div class="icon">📗</div>
   <h2>Third Year</h2>
   <p>Explore and upload projects from Fifth and Sixth Semester.</p>
   <button type="button" class="primary" onclick="event.stopPropagation();openYear(3)">Open Third Year →</button>
  </div>
 </div>
</section>

<!-- AUTH -->
<section id="auth" class="hidden">
 <div class="card form-box">
  <h2 id="authTitle">Create Account</h2>

  <div id="nameField">
   <label for="name">Your Name</label>
   <input id="name" placeholder="Enter your name">
  </div>

  <label for="password">Password</label>
  <input id="password" type="password" placeholder="Enter password">

  <div id="confirmField">
   <label for="confirm">Confirm Password</label>
   <input id="confirm" type="password" placeholder="Confirm password">
  </div>

  <p class="message" id="authError"></p>
  <button type="button" class="primary" style="width:100%" onclick="submitAuth()" id="authSubmit">Create Account</button>

  <p style="margin-top:18px;text-align:center;font-size:14px">
   <span id="switchText">Already have an account?</span>
   <button type="button" class="link-btn" onclick="switchAuth()" id="switchLink">Login</button>
  </p>
 </div>
</section>

<!-- YEAR -->
<section id="yearPage" class="hidden">
 <button type="button" class="secondary" onclick="showPage('home')">← Back</button>
 <h2 class="section-title" id="yearTitle">Second Year</h2>
 <p style="color:#777;margin-bottom:20px">Select your semester to continue.</p>
 <div class="grid" id="semesterGrid"></div>
</section>

<!-- UPLOAD -->
<section id="uploadPage" class="hidden">
 <button type="button" class="secondary" onclick="openYear(selectedYear)">← Back</button>
 <div class="card form-box" style="max-width:600px">
  <h2>Upload Your Project</h2>
  <p id="uploadSemester" style="color:#6555d9;margin-bottom:18px"></p>

  <label for="projectName">Project Name</label>
  <input id="projectName" placeholder="Enter project name">

  <label for="projectImage">Project Image</label>
  <input type="file" id="projectImage" accept="image/*">

  <label for="description">Project Description</label>
  <textarea id="description" rows="5" placeholder="Explain your project..."></textarea>

  <p class="message" id="uploadError"></p>
  <button type="button" class="primary" style="width:100%" onclick="uploadProject()">Upload Project</button>
 </div>
</section>

<!-- EXPLORE -->
<section id="explorePage" class="hidden">
 <div class="topline">
  <h2 class="section-title">Explore Projects</h2>
  <button type="button" class="secondary" onclick="showPage('home')">Home</button>
 </div>

 <input id="search" placeholder="🔍 Search projects..." oninput="renderProjects()">

 <div class="grid" id="projectGrid"></div>
 <div id="emptyExplore" class="empty hidden">
  <h2>📂 No Projects Found</h2>
  <p style="margin-top:8px">Be the first student to upload a project!</p>
 </div>
</section>

<!-- MY PROJECTS -->
<section id="myPage" class="hidden">
 <div class="topline">
  <h2 class="section-title">My Projects</h2>
  <button type="button" class="secondary" onclick="showPage('home')">Home</button>
 </div>
 <div class="grid" id="myGrid"></div>
 <div id="emptyMine" class="empty hidden">You haven't uploaded any projects yet.</div>
</section>

</main>

<footer>
 <b>STUDENT PROJECTS</b>
 <p style="margin-top:8px">Share Your Projects. Inspire Others.</p>
</footer>

<div id="toast" class="toast hidden" role="status" aria-live="polite"></div>

<div id="confirmModal" class="modal-backdrop hidden" role="dialog" aria-modal="true" aria-labelledby="confirmTitle">
 <div class="modal-box">
  <h3 id="confirmTitle">Delete Project</h3>
  <p id="confirmMessage">Are you sure you want to delete this project?</p>
  <div class="modal-actions">
   <button type="button" class="secondary" onclick="closeConfirm()">Cancel</button>
   <button type="button" class="danger" id="confirmOkBtn">Delete</button>
  </div>
 </div>
</div>

<script>
const $ = id => document.getElementById(id);

const memoryStore = {
 sp_current: "",
 sp_users: "{}",
 sp_projects: "[]"
};

function readStore(key, fallback){
 try{
  const val = localStorage.getItem(key);
  return val !== null ? val : fallback;
 }catch(e){
  return Object.prototype.hasOwnProperty.call(memoryStore, key) ? memoryStore[key] : fallback;
 }
}

function writeStore(key, value){
 memoryStore[key] = value;
 try{
  localStorage.setItem(key, value);
 }catch(e){
  // Fallback to in-memory store when storage is unavailable
 }
}

function removeStore(key){
 memoryStore[key] = "";
 try{
  localStorage.removeItem(key);
 }catch(e){
  // Fallback to in-memory store
 }
}

let currentUser = readStore("sp_current", "");
let authMode = "signup";
let selectedYear = 2;
let selectedSemester = 3;
let toastTimer = null;
let pendingDeleteId = null;

function showToast(msg, type = "success"){
 const el = $("toast");
 el.textContent = msg;
 el.className = "toast " + type;
 if(toastTimer) clearTimeout(toastTimer);
 toastTimer = setTimeout(()=>{
  el.classList.add("hidden");
 }, 3000);
}

function getUsers(){
 try{
  return JSON.parse(readStore("sp_users", "{}"));
 }catch(e){
  return {};
 }
}
function getProjects(){
 try{
  return JSON.parse(readStore("sp_projects", "[]"));
 }catch(e){
  return [];
 }
}
function saveProjects(data){
 writeStore("sp_projects", JSON.stringify(data));
}

function showPage(page){
 ["home","auth","yearPage","uploadPage","explorePage","myPage"]
 .forEach(id=>$(id).classList.add("hidden"));

 const map={
  home:"home",login:"auth",year:"yearPage",
  upload:"uploadPage",explore:"explorePage",my:"myPage"
 };
 $(map[page]).classList.remove("hidden");
 window.scrollTo(0,0);
 updateNav();
}

function updateNav(){
 $("loginNav").classList.toggle("hidden",!!currentUser);
 $("myNav").classList.toggle("hidden",!currentUser);
 $("logoutNav").classList.toggle("hidden",!currentUser);
}

function setAuthMode(mode){
 authMode = mode;
 $("authTitle").textContent = authMode==="signup"?"Create Account":"Student Login";
 $("authSubmit").textContent = authMode==="signup"?"Create Account":"Login";
 $("confirmField").classList.toggle("hidden",authMode==="login");
 $("switchText").textContent = authMode==="signup"?"Already have an account?":"Don't have an account?";
 $("switchLink").textContent = authMode==="signup"?"Login":"Create Account";
 $("authError").textContent = "";
}

function openAuth(mode = "login"){
 setAuthMode(mode);
 showPage("login");
}

function switchAuth(){
 setAuthMode(authMode==="signup"?"login":"signup");
}

function submitAuth(){
 let users=getUsers();
 let password=$("password").value.trim();

 if(authMode==="signup"){
  let name=$("name").value.trim();
  let confirm=$("confirm").value.trim();
  if(!name || !password || !confirm){
   return $("authError").textContent="Please fill all fields.";
  }
  if(password.length<6){
   return $("authError").textContent="Password must be at least 6 characters.";
  }
  if(password!==confirm){
   return $("authError").textContent="Passwords do not match.";
  }
  let key=name.toLowerCase();
  if(users[key]){
   return $("authError").textContent="This name is already registered.";
  }
  users[key]={name,password};
  writeStore("sp_users",JSON.stringify(users));
  currentUser=key;
 }else{
  let name=$("name").value.trim().toLowerCase();
  if(!name || !password){
   return $("authError").textContent="Please enter your name and password.";
  }
  if(!users[name] || users[name].password!==password){
   return $("authError").textContent="Incorrect name or password.";
  }
  currentUser=name;
 }
 writeStore("sp_current",currentUser);
 $("password").value="";
 $("confirm").value="";
 $("name").value="";
 showToast("Welcome, " + getUsers()[currentUser].name + "!");
 showPage("home");
}

function logout(){
 currentUser="";
 removeStore("sp_current");
 showToast("Logged out successfully.");
 showPage("home");
}

function startUpload(){
 if(!currentUser){
  openAuth("login");
  return;
 }
 openYear(2);
}

function openYear(year){
 selectedYear=year;
 $("yearTitle").textContent=year===2?"Second Year":"Third Year";
 let semesters=year===2?[3,4]:[5,6];

 $("semesterGrid").innerHTML=semesters.map(s=>`
  <button type="button" class="semester" onclick="openSemester(${s})">
   <h2>📚 ${s===3?"Third":s===4?"Fourth":s===5?"Fifth":"Sixth"} Semester</h2>
   <p style="color:#888;margin-top:8px">View and upload projects →</p>
  </button>
 `).join("");
 showPage("year");
}

function openSemester(semester){
 selectedSemester=semester;
 if(!currentUser){
  openAuth("login");
  return;
 }
 $("uploadSemester").textContent=
  (selectedYear===2?"Second Year":"Third Year")+
  " | "+semester+" Semester";
 $("uploadError").textContent="";
 showPage("upload");
}

function uploadProject(){
 if(!currentUser)return openAuth("login");

 let name=$("projectName").value.trim();
 let description=$("description").value.trim();
 let file=$("projectImage").files[0];

 if(!name || !description || !file){
  return $("uploadError").textContent="Please fill all fields and select a photo.";
 }
 if(!file.type.startsWith("image/")){
  return $("uploadError").textContent="Please select an image file.";
 }
 if(file.size>1.5*1024*1024){
  return $("uploadError").textContent="Image must be smaller than 1.5 MB.";
 }

 let reader=new FileReader();
 reader.onload=function(){
  try{
   let projects=getProjects();
   projects.unshift({
    id:Date.now(),
    name,
    description,
    image:reader.result,
    year:selectedYear,
    semester:selectedSemester,
    author:getUsers()[currentUser].name,
    owner:currentUser,
    date:new Date().toLocaleDateString()
   });
   saveProjects(projects);
   $("projectName").value="";
   $("description").value="";
   $("projectImage").value="";
   showToast("Project uploaded successfully!");
   explore();
  }catch(e){
   $("uploadError").textContent="Storage full. Try a smaller image or delete old projects.";
  }
 };
 reader.readAsDataURL(file);
}

function explore(){
 $("search").value="";
 renderProjects();
 showPage("explore");
}

function makeProjectCard(p,showDelete=false){
 let card=document.createElement("div");
 card.className="card project-card";

 let img=document.createElement("img");
 img.src=p.image;
 img.alt=p.name + " project image";
 card.appendChild(img);

 let content=document.createElement("div");
 content.className="project-content";

 let h=document.createElement("h3");
 h.textContent=p.name;
 content.appendChild(h);

 let tag=document.createElement("span");
 tag.className="tag";
 tag.textContent=(p.year===2?"Second Year":"Third Year")+" • "+p.semester+" Semester";
 content.appendChild(tag);

 let desc=document.createElement("p");
 desc.textContent=p.description;
 content.appendChild(desc);

 let meta=document.createElement("div");
 meta.className="meta";
 meta.textContent="Uploaded by "+p.author+" • "+p.date;
 content.appendChild(meta);

 if(showDelete && p.owner===currentUser){
  let actions=document.createElement("div");
  actions.className="actions";
  let del=document.createElement("button");
  del.type="button";
  del.className="danger";
  del.textContent="Delete Project";
  del.onclick=()=>requestDeleteProject(p.id);
  actions.appendChild(del);
  content.appendChild(actions);
 }
 card.appendChild(content);
 return card;
}

function renderProjects(){
 let q=$("search").value.toLowerCase();
 let projects=getProjects().filter(p=>
  p.name.toLowerCase().includes(q) ||
  p.description.toLowerCase().includes(q) ||
  p.author.toLowerCase().includes(q)
 );
 $("projectGrid").replaceChildren();
 projects.forEach(p=>$("projectGrid").appendChild(makeProjectCard(p)));
 $("emptyExplore").classList.toggle("hidden",projects.length!==0);
}

function myProjects(){
 if(!currentUser)return openAuth("login");
 let mine=getProjects().filter(p=>p.owner===currentUser);
 $("myGrid").replaceChildren();
 mine.forEach(p=>$("myGrid").appendChild(makeProjectCard(p,true)));
 $("emptyMine").classList.toggle("hidden",mine.length!==0);
 showPage("my");
}

function requestDeleteProject(id){
 pendingDeleteId = id;
 $("confirmModal").classList.remove("hidden");
}

function closeConfirm(){
 pendingDeleteId = null;
 $("confirmModal").classList.add("hidden");
}

$("confirmOkBtn").addEventListener("click", function(){
 if(pendingDeleteId !== null){
  saveProjects(getProjects().filter(p=>p.id!==pendingDeleteId));
  closeConfirm();
  showToast("Project deleted.");
  myProjects();
 }
});

if(currentUser && !getUsers()[currentUser]){
 currentUser="";
 removeStore("sp_current");
}
updateNav();
showPage("home");
</script>

</body>
</html>
