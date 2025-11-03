<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🩷 사랑의 아츄핑! 당신의 운명은..? 🩷</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Nanum+Pen+Script&family=Pretendard:wght@400;600&display=swap');
body { font-family: 'Pretendard', sans-serif; background: linear-gradient(to bottom, #fff8f9, #ffeef0); color: #5a4a4a; text-align: center; margin: 0; padding: 0; }
h1 { color: #ff7fa5; margin-top: 40px; font-family: 'Nanum Pen Script', cursive; font-size: 48px; }
.question { margin: 30px auto; width: 85%; max-width: 520px; background: #ffffffcc; border-radius: 20px; padding: 25px; box-shadow: 0 4px 10px rgba(255,182,193,0.3); backdrop-filter: blur(6px); }
button { background: #ffd3dc; color: #5a4a4a; border: none; padding: 12px 22px; margin: 8px; border-radius: 12px; cursor: pointer; font-size: 16px; font-weight: 600; }
button:hover { background: #ffb8c6; color: white; }
#result { display: none; margin-top: 40px; }
#result-text { background: #fff7f9; width: 85%; max-width: 500px; margin: 20px auto; border-radius: 15px; padding: 20px; line-height: 1.7; font-size: 18px; box-shadow: 0 3px 10px rgba(255,192,203,0.3); }
.restart-btn, .share-btn { background: #ffadc1; color: white; border: none; padding: 12px 25px; border-radius: 12px; cursor: pointer; font-size: 16px; margin: 5px; }
.restart-btn:hover, .share-btn:hover { background: #ff92af; }
</style>
</head>
<body>
<h1>🩷 사랑의 아츄핑! 당신의 운명은..? 🩷</h1>
<div id="quiz"></div>
<div id="result">
<h2>💓 당신의 사랑 타입은... 💓</h2>
<p id="result-text"></p>
<button class="restart-btn" onclick="location.reload()">다시 해보기 💌</button>
<button class="share-btn" onclick="shareResult()">결과 공유하기 💖</button>
</div>
<script>
const quizData = [
{ q: "연인과의 첫 데이트 장소로 고르고 싶은 곳은?", a: ["놀이공원 🎢","카페 ☕","영화관 🎬","드라이브 🚗"] },
{ q: "선물 받을 때 더 감동하는 건?", a: ["직접 만든 선물 🎁","진심이 담긴 편지 💌","깜짝 이벤트 🎉","필요한 물건 🛍️"] },
{ q: "싸웠을 때 나는 어떤 편?", a: ["바로 화해 시도","잠시 거리두기","상대가 먼저 오길 기다림","끝까지 내 입장 설명"] },
{ q: "연애할 때 연락 스타일은?", a: ["자주 연락해야 안심","필요할 때만","하루에 한 번 정도","분위기 따라 다름"] },
{ q: "내 이상형의 성격은?", a: ["활발하고 유쾌한","다정하고 조용한","자신감 넘치는","감성적인"] },
{ q: "사랑 표현을 할 때 나는?", a: ["말로 표현 💬","행동으로 보여줌 💪","선물로 마음 전함 🎁","눈빛과 분위기로 💞"] }
];
const results = [
"☀️ <b>A형</b> — <b>열정 폭발 사랑꾼!</b><br>표현력 만점의 분위기 리더형 💖<br><small>당신의 사랑은 늘 반짝이고 뜨거워요!</small>",
"🌙 <b>B형</b> — <b>감성파 츤데레!</b><br>겉은 쿨하지만 속은 따뜻한 반전 매력 💌<br><small>말보단 행동, 사랑은 조용히 보여주는 타입.</small>",
"☕ <b>C형</b> — <b>편안한 친구 같은 연인!</b><br>신뢰와 안정감이 최고인 현실 로맨티스트 💑<br><small>사랑이 곧 일상, 따뜻한 온도 유지형.</small>",
"💐 <b>D형</b> — <b>예측불가 매력형!</b><br>감정에 솔직하고 즉흥적인 로맨틱 타입 🌹<br><small>매 순간이 영화 같은 연애를 꿈꾸는 사람!</small>"
];
let current = 0; const answers = []; const quizDiv = document.getElementById("quiz");
function showQuestion(){ if(current<quizData.length){ const q=quizData[current]; quizDiv.innerHTML=`<div class="question"><h2>${q.q}</h2>${q.a.map((opt,i)=>`<button onclick="selectAnswer(${i})">${opt}</button>`).join("")}</div>`;} else showResult(); }
function selectAnswer(choice){ answers.push(choice); current++; showQuestion(); }
function showResult(){ quizDiv.style.display="none"; document.getElementById("result").style.display="block"; const counts=[0,0,0,0]; answers.forEach(a=>counts[a]++); const maxIndex=counts.indexOf(Math.max(...counts)); document.getElementById("result-text").innerHTML=results[maxIndex]; }
function shareResult(){ const text=`🩷 사랑의 아츄핑! 당신의 운명은..? 🩷\n${document.getElementById("result-text").innerText}\n테스트 해보러 가기: ${window.location.href}`; navigator.clipboard.writeText(text).then(()=>alert("결과가 클립보드에 복사되었어요! 💖 친구에게 공유해보세요!")).catch(()=>alert("복사 실패 😢")); }
showQuestion();
</script>
</body>
</html>
