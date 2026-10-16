
<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>فوتبال من | HAMED AKBARI</title>

<style>
*{box-sizing:border-box}
body{
  margin:0;background:#0b1220;color:white;
  font-family:Arial,sans-serif;direction:rtl
}
header{
  background:linear-gradient(135deg,#00a86b,#064e3b);
  padding:25px 15px;text-align:center
}
.logo{
  width:150px;height:150px;margin:auto;
  border:4px solid #ffd700;border-radius:50%;
  background:#07152d;display:flex;
  align-items:center;justify-content:center;
  box-shadow:0 0 25px #ffd700
}
.logo svg{width:125px;height:125px}
header h1{margin:12px 0;font-size:30px}
header p{margin:8px 0}
.creator{color:#ffd700;font-weight:bold}
main{max-width:700px;margin:auto;padding:15px}
h2,h3{text-align:center}
.menu{
  display:grid;grid-template-columns:1fr 1fr;gap:10px
}
button{
  border:0;border-radius:10px;padding:13px 8px;
  background:#20c997;color:#06251b;
  font-weight:bold;font-size:15px;cursor:pointer
}
button:active{opacity:.8}
input,select{
  width:100%;padding:13px;border-radius:9px;
  border:1px solid #64748b;font-size:16px;margin:10px 0
}
.panel{
  background:#172338;padding:15px;
  border-radius:12px;margin-top:15px
}
.card{
  background:#26364d;border-radius:10px;
  padding:12px;margin:10px 0
}
.news-title{
  font-size:17px;font-weight:bold;line-height:1.8
}
.news-description{color:#d4deeb;line-height:1.8}
.news-date{color:#aab7c8;font-size:12px}
.status{line-height:1.8;text-align:center}
.score{
  font-size:24px;font-weight:bold;color:#20c997;
  margin:8px;text-align:center
}
.live{color:#ff7373;font-weight:bold}
.finished{color:#5eead4}
a{color:#5eead4;text-decoration:none}
table{width:100%;border-collapse:collapse;font-size:13px}
td,th{border:1px solid #64748b;padding:8px 4px;text-align:center}
th{background:#087f5b}
footer{text-align:center;color:#aab7c8;padding:20px}
</style>
</head>

<body>

<header>
  <div class="logo">
    <svg viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg">
      <path d="M25 15 L45 30 L60 5 L75 30 L95 15 L90 48 L30 48 Z"
        fill="#ffd700" stroke="#fff0a0" stroke-width="2"/>
      <circle cx="25" cy="13" r="5" fill="#ffd700"/>
      <circle cx="60" cy="5" r="5" fill="#ffd700"/>
      <circle cx="95" cy="13" r="5" fill="#ffd700"/>
      <circle cx="60" cy="69" r="34" fill="#fff" stroke="#ffd700" stroke-width="4"/>
      <path d="M60 49 L73 58 L68 73 L52 73 L47 58 Z" fill="#101827"/>
      <path d="M60 49 L60 36 L75 31 L84 43 L73 58 Z" fill="#101827"/>
      <path d="M47 58 L34 52 L29 67 L40 80 L52 73 Z" fill="#101827"/>
      <path d="M68 73 L80 82 L70 96 L54 93 L52 73 Z" fill="#101827"/>
      <path d="M17 105 L103 105" stroke="#ffd700" stroke-width="4" stroke-linecap="round"/>
    </svg>
  </div>
  <h1>⚽ فوتبال من</h1>
  <p>اخبار، نتایج و مسابقات فوتبال</p>
  <p class="creator">سازنده: HAMED AKBARI</p>
</header>

<main>
<h2>منوی اصلی</h2>

<div class="menu">
  <button onclick="show('home')">🏠 خانه</button>
  <button onclick="show('teams')">🏆 تیم‌ها</button>
  <button onclick="show('results')">⚽ نتایج</button>
  <button onclick="show('news')">📰 اخبار</button>
  <button onclick="show('table')">📊 جدول لیگ</button>
  <button onclick="show('leagues')">🌍 لیگ‌ها</button>
</div>

<div class="panel">
  <input id="search" placeholder="نام تیم را جست‌وجو کن...">
  <button onclick="searchTeam()">🔎 جست‌وجوی تیم</button>
</div>

<div id="content" class="panel">
  <h3>به فوتبال من خوش آمدی!</h3>
  <p class="status">یک بخش را از منو انتخاب کن.</p>
</div>
</main>

<footer>
فوتبال من © 2026<br>
ساخته‌شده توسط HAMED AKBARI
</footer>

<script>
const content=document.getElementById("content");

const teams=[
"رئال مادرید","بارسلونا","منچستریونایتد",
"منچسترسیتی","بایرن مونیخ","لیورپول",
"آرسنال","پاری‌سن‌ژرمن","یوونتوس","اینتر میلان"
];

const leagues=[
{id:"eng.1",name:"لیگ برتر انگلیس"},
{id:"esp.1",name:"لالیگا اسپانیا"},
{id:"ger.1",name:"بوندس‌لیگا آلمان"},
{id:"ita.1",name:"سری آ ایتالیا"},
{id:"fra.1",name:"لیگ یک فرانسه"},
{id:"uefa.champions",name:"لیگ قهرمانان اروپا"}
];

function show(section){
  if(section==="home"){
    content.innerHTML=`
      <h3>🏠 به فوتبال من خوش آمدی</h3>
      <p class="status">اخبار و اطلاعات مسابقات را از منوی بالا بررسی کن.</p>
      <button onclick="show('news')">📰 مشاهده اخبار</button>
      <button onclick="show('results')">⚽ مشاهده نتایج</button>`;
  }

  if(section==="teams"){
    content.innerHTML="<h3>🏆 تیم‌های معروف</h3>"+
      teams.map(t=>'<div class="card">⚽ '+t+'</div>').join("");
  }

  if(section==="results") loadScores();

  if(section==="news") loadNews();

  if(section==="table"){
    content.innerHTML=`
      <h3>📊 جدول لیگ</h3>
      <p class="status">
        جدول امتیازات هنوز به داده‌های واقعی لیگ وصل نشده است.
        برای جلوگیری از نمایش اطلاعات نادرست، جدول نمونه حذف شده است.
      </p>`;
  }

  if(section==="leagues"){
    content.innerHTML=`
      <h3>🌍 لیگ‌های فوتبال</h3>
      ${leagues.map(l=>
        '<div class="card"><button style="width:100%" onclick="loadScores(\''+
        l.id+'\')">'+l.name+' — مشاهده مسابقات</button></div>'
      ).join("")}`;
  }
}

async function loadNews(){
  content.innerHTML=`
    <h3>📰 آخرین اخبار فوتبال</h3>
    <p class="status">در حال دریافت اخبار از اینترنت...</p>`;

  try{
    const response=await fetch(
      "https://site.api.espn.com/apis/site/v2/sports/soccer/eng.1/news?limit=20"
    );

    if(!response.ok) throw new Error("News unavailable");

    const data=await response.json();
    const articles=data.articles||[];

    if(!articles.length) throw new Error("No news");

    content.innerHTML=`
      <h3>📰 آخرین اخبار فوتبال</h3>
      <p class="status">منبع: ESPN</p>
      <button id="refreshNews">🔄 تازه‌سازی اخبار</button>
      <div id="newsList"></div>`;

    document.getElementById("refreshNews")
      .addEventListener("click",loadNews);

    const list=document.getElementById("newsList");

    articles.forEach(article=>{
      const card=document.createElement("div");
      card.className="card";

      const title=document.createElement("div");
      title.className="news-title";
      title.textContent=article.headline||"خبر فوتبال";
      card.appendChild(title);

      if(article.description){
        const desc=document.createElement("p");
        desc.className="news-description";
        desc.textContent=article.description;
        card.appendChild(desc);
      }

      if(article.published){
        const date=new Date(article.published);
        const dateEl=document.createElement("p");
        dateEl.className="news-date";
        dateEl.textContent=isNaN(date.getTime())
          ? "" : "تاریخ انتشار: "+date.toLocaleString("fa-IR");
        card.appendChild(dateEl);
      }

      const href=article.links?.web?.href;
      if(href){
        try{
          const u=new URL(href);
          if(["https:","http:"].includes(u.protocol)){
            const link=document.createElement("a");
            link.href=u.href;
            link.target="_blank";
            link.rel="noopener noreferrer";
            link.textContent="خواندن خبر کامل ←";
            card.appendChild(link);
          }
        }catch(e){}
      }

      list.appendChild(card);
    });

  }catch(error){
    content.innerHTML=`
      <h3>📰 اخبار فوتبال</h3>
      <p class="status">
        دریافت خبر ناموفق بود. اینترنت یا دسترسی منبع را بررسی کن.
      </p>
      <button id="retryNews">🔄 تلاش دوباره</button>`;
    document.getElementById("retryNews")
      .addEventListener("click",loadNews);
  }
}

async function loadScores(leagueId=null){
  content.innerHTML=`
    <h3>⚽ نتایج واقعی فوتبال</h3>
    <p class="status">در حال دریافت اطلاعات مسابقات...</p>`;

  const selected=leagueId
    ? leagues.filter(l=>l.id===leagueId)
    : leagues;

  try{
    const responses=await Promise.allSettled(
      selected.map(async league=>{
        const response=await fetch(
          "https://site.api.espn.com/apis/site/v2/sports/soccer/"+
          league.id+"/scoreboard"
        );

        if(!response.ok) throw new Error("Request failed");

        const data=await response.json();

        return (data.events||[]).map(event=>({
          ...event,
          leagueName:league.name
        }));
      })
    );

    const matches=responses
      .filter(r=>r.status==="fulfilled")
      .flatMap(r=>r.value)
      .sort((a,b)=>new Date(a.date)-new Date(b.date));

    const failed=responses.filter(r=>r.status==="rejected").length;

    content.innerHTML=`
      <h3>⚽ نتایج و مسابقات</h3>
      <p class="status">منبع: ESPN</p>
      <select id="leagueSelect">
        <option value="">همه لیگ‌ها</option>
        ${leagues.map(l=>
          '<option value="'+l.id+'" '+(l.id===leagueId?'selected':'')+'>'+
          l.name+'</option>'
        ).join("")}
      </select>
      <button id="refreshScores">🔄 تازه‌سازی نتایج</button>
      <div id="scoreList"></div>`;

    document.getElementById("leagueSelect")
      .addEventListener("change",e=>{
        loadScores(e.target.value||null);
      });

    document.getElementById("refreshScores")
      .addEventListener("click",()=>loadScores(leagueId));

    const list=document.getElementById("scoreList");

    if(!matches.length){
      list.innerHTML=`
        <p class="status">
          ${failed===selected.length
            ? "دریافت اطلاعات از منبع ناموفق بود. اینترنت یا دسترسی منبع را بررسی کن."
            : "در این فهرست مسابقه‌ای پیدا نشد."}
        </p>`;
      return;
    }

    matches.forEach(match=>{
      const competition=match.competitions?.[0];
      const competitors=competition?.competitors||[];
      const home=competitors.find(t=>t.homeAway==="home");
      const away=competitors.find(t=>t.homeAway==="away");

      if(!home||!away) return;

      const state=match.status?.type;
      const live=state?.state==="in";
      const finished=state?.completed;
      const date=new Date(match.date);

      const card=document.createElement("div");
      card.className="card";

      const league=document.createElement("p");
      league.className="news-date";
      league.textContent=match.leagueName;
      card.appendChild(league);

      const names=document.createElement("div");
      names.className="news-title";
      names.style.textAlign="center";
      names.textContent=
        home.team.displayName+"  -  "+away.team.displayName;
      card.appendChild(names);

      const score=document.createElement("div");
      score.className="score";
      score.textContent=
        (home.score??"—")+"  :  "+(away.score??"—");
      card.appendChild(score);

      const status=document.createElement("p");
      status.className="status";

      if(live){
        status.classList.add("live");
        status.textContent="🔴 زنده | "+
          (state.displayClock||state.detail||"در حال بازی");
      }else if(finished){
        status.classList.add("finished");
        status.textContent="🏁 پایان مسابقه";
      }else{
        status.textContent="🕒 "+
          (isNaN(date.getTime())
            ? (state?.detail||"زمان اعلام نشده")
            : date.toLocaleString("fa-IR"))+
          (state?.detail ? " | "+state.detail : "");
      }

      card.appendChild(status);
      list.appendChild(card);
    });

    if(!list.children.length){
      list.innerHTML=
        '<p class="status">اطلاعات مسابقات قابل نمایش نیست.</p>';
    }

    if(failed>0){
      const note=document.createElement("p");
      note.className="status";
      note.textContent=
        "توجه: اطلاعات بعضی لیگ‌ها دریافت نشد؛ نتایج نمایش‌داده‌شده فقط از منابع پاسخ‌گو هستند.";
      list.prepend(note);
    }

  }catch(error){
    content.innerHTML=`
      <h3>⚽ نتایج مسابقات</h3>
      <p class="status">
        دریافت اطلاعات ناموفق بود. اتصال اینترنت یا دسترسی منبع را بررسی کن.
      </p>
      <button id="retryScores">🔄 تلاش دوباره</button>`;
    document.getElementById("retryScores")
      .addEventListener("click",()=>loadScores(leagueId));
  }
}

function searchTeam(){
  const q=document.getElementById("search")
    .value.trim().toLowerCase();

  if(!q){
    content.innerHTML=
      '<p class="status">لطفاً نام یک تیم را بنویس.</p>';
    return;
  }

  const found=teams.filter(t=>t.toLowerCase().includes(q));

  content.innerHTML=found.length
    ? "<h3>🔎 نتیجه جست‌وجو</h3>"+
      found.map(t=>'<div class="card">⚽ '+t+'</div>').join("")
    : '<p class="status">تیمی با این نام در فهرست پیدا نشد.</p>';
}

show("home");
</script>
</body>
</html>


### 📁 Project Structure
