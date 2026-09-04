```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>AFRIN.EXE 👑</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    min-height:100vh;
    background:#050505;
    color:white;
    font-family:Arial,sans-serif;
    overflow:hidden;
}

/* BACKGROUND */

body::before{
    content:"";
    position:fixed;
    inset:0;
    background:
    radial-gradient(circle at 20% 20%,rgba(255,20,100,.20),transparent 30%),
    radial-gradient(circle at 80% 80%,rgba(140,30,255,.18),transparent 30%);
    pointer-events:none;
}

#app{
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    padding:25px;
    position:relative;
    z-index:5;
}

.box{
    width:100%;
    max-width:850px;
}

.warning{
    color:#ff4f91;
    font-size:16px;
    font-weight:bold;
    letter-spacing:4px;
    animation:blink .8s infinite;
}

.big{
    font-size:42px;
    font-weight:900;
    line-height:1.3;
    margin:20px 0;
    animation:zoom 1s ease;
}

.huge{
    font-size:65px;
    font-weight:900;
    line-height:1.2;
    margin:20px 0;
    text-shadow:0 0 25px #ff3f91;
    animation:zoom 1.3s ease;
}

.text{
    font-size:20px;
    line-height:1.8;
    white-space:pre-line;
}

.small{
    color:#999;
    margin-top:20px;
}

.pink{
    color:#ff5caa;
}

.gold{
    color:#ffd84d;
}

/* BUTTON */

button{
    margin-top:30px;
    padding:15px 30px;
    border:2px solid #ff4f91;
    border-radius:30px;
    background:#111;
    color:#ff6fa7;
    font-size:18px;
    font-weight:bold;
    cursor:pointer;
    transition:.3s;
}

button:hover{
    background:#ff4f91;
    color:white;
    transform:scale(1.08);
}

/* FLOATING STARS */

.star{
    position:fixed;
    color:#ff6fa7;
    z-index:1;
    animation:float 5s linear forwards;
}

/* HEARTS */

.heart{
    position:fixed;
    bottom:-60px;
    font-size:35px;
    z-index:20;
    animation:heartFly 5s ease-out forwards;
}

/* SPARKLES */

.spark{
    position:fixed;
    font-size:28px;
    z-index:30;
    animation:sparkBlast 1.5s ease-out forwards;
}

/* CONFETTI */

.confetti{
    position:fixed;
    top:-30px;
    font-size:20px;
    z-index:25;
    animation:fall 4s linear forwards;
}

/* ANIMATIONS */

@keyframes blink{
    50%{opacity:.2;}
}

@keyframes zoom{
    from{
        opacity:0;
        transform:scale(.4);
    }
    to{
        opacity:1;
        transform:scale(1);
    }
}

@keyframes float{
    from{
        transform:translateY(0) rotate(0);
        opacity:1;
    }
    to{
        transform:translateY(-110vh) rotate(360deg);
        opacity:0;
    }
}

@keyframes heartFly{
    from{
        transform:translateY(0) scale(.5);
        opacity:0;
    }
    20%{opacity:1;}
    to{
        transform:translateY(-110vh) rotate(25deg) scale(1.5);
        opacity:0;
    }
}

@keyframes sparkBlast{
    from{
        transform:scale(0);
        opacity:1;
    }
    50%{
        transform:scale(2);
        opacity:1;
    }
    to{
        transform:scale(.3);
        opacity:0;
    }
}

@keyframes fall{
    to{
        transform:translateY(110vh) rotate(720deg);
    }
}
</style>
</head>

<body>

<div id="app"></div>

<script>

const app = document.getElementById("app");

function wait(ms){
    return new Promise(resolve => setTimeout(resolve,ms));
}

/* TYPEWRITER */

async function typeText(text,speed=30){

    app.innerHTML = `
        <div class="box">
            <div class="text" id="typing"></div>
        </div>
    `;

    const typing = document.getElementById("typing");

    for(const char of text){
        typing.textContent += char;
        await wait(speed);
    }
}

/* STARS */

function createStar(){

    const star = document.createElement("div");

    star.className = "star";

    const symbols = ["✦","✧","✨","★"];

    star.innerHTML =
        symbols[Math.floor(Math.random()*symbols.length)];

    star.style.left = Math.random()*100 + "%";
    star.style.bottom = "-30px";
    star.style.fontSize = (15 + Math.random()*25) + "px";

    document.body.appendChild(star);

    setTimeout(() => star.remove(),5000);
}

setInterval(createStar,400);

/* HEART */

function createHeart(){

    const heart = document.createElement("div");

    heart.className = "heart";
    heart.innerHTML = "❤️";

    heart.style.left =
        (Math.random()*90+5) + "%";

    document.body.appendChild(heart);

    setTimeout(() => heart.remove(),5000);
}

/* SPARK */

function createSpark(){

    const spark = document.createElement("div");

    spark.className = "spark";

    const symbols = [
        "✨","💥","⭐","🎆","💖"
    ];

    spark.innerHTML =
        symbols[Math.floor(Math.random()*symbols.length)];

    spark.style.left =
        (Math.random()*85+5) + "%";

    spark.style.top =
        (Math.random()*70+10) + "%";

    document.body.appendChild(spark);

    setTimeout(() => spark.remove(),1600);
}

/* CONFETTI */

function createConfetti(){

    const c = document.createElement("div");

    c.className = "confetti";

    const symbols = [
        "✦","✧","★","✨","💖","•"
    ];

    c.innerHTML =
        symbols[Math.floor(Math.random()*symbols.length)];

    c.style.left = Math.random()*100 + "%";

    document.body.appendChild(c);

    setTimeout(() => c.remove(),4500);
}

/* SECRET MESSAGE */

function secretMessage(){

    app.innerHTML = `
        <div class="box">

            <div class="huge">
                🤫❤️
            </div>

            <div class="warning">
                SECRET FILE UNLOCKED
            </div>

            <div class="big">
                THE REAL AFRIN
            </div>

            <div class="text">
                Behind all the chaos...

                Behind all the overthinking...

                Behind all the confidence...

                There is simply a girl
                trying to build a beautiful life.

                She has fallen.
                She has failed.
                She has been disappointed.

                But she STILL GETS UP.

                And that...

                is her real superpower. 👑❤️
            </div>

            <button onclick="location.reload()">
                🔄 RUN AFRIN.EXE AGAIN
            </button>

        </div>
    `;

    for(let i=0;i<20;i++){

        setTimeout(() => {
            createHeart();
        },i*120);

    }
}

/* MAIN STORY */

async function start(){

    /* INTRO */

    app.innerHTML = `
        <div class="box">

            <div class="warning">
                SYSTEM INITIALIZING...
            </div>

            <div class="huge">
                AFRIN.EXE
            </div>

            <div class="text">
                Loading personality...

                Loading dreams...

                Loading chaos...

                Loading main character energy...
            </div>

        </div>
    `;

    await wait(3500);

    /* MAIN CHARACTER */

    app.innerHTML = `
        <div class="box">

            <div class="warning">
                ⚠️ MAIN CHARACTER DETECTED ⚠️
            </div>

            <div class="huge">
                AFRIN 👑
            </div>

            <div class="text">
                Status:
                <span class="pink">UNSTOPPABLE</span>

                Main character energy:
                <span class="gold">100%</span>
            </div>

        </div>
    `;

    await wait(3000);

    /* WHO IS AFRIN */

    await typeText(
        "WHO IS AFRIN?\n\n"+
        "Quick learner. ⚡\n"+
        "Movie lover. 🎬\n"+
        "Music lover. 🎧\n"+
        "Book lover. 📚\n"+
        "Food experimenter. 🍜\n\n"+
        "Basically...\n"+
        "one person with approximately\n"+
        "47 different personalities. 😂",
        28
    );

    await wait(3200);

    /* ACADEMIC ARC */

    await typeText(
        "THE ACADEMIC ARC 🎓\n\n"+
        "B.Tech — Artificial Intelligence & Data Science\n\n"+
        "Python ✓\n"+
        "C ✓\n"+
        "SQL ✓\n"+
        "AI Projects ✓\n\n"+
        "Assignments ✓\n"+
        "Placement preparation ✓\n"+
        "Last-minute panic ✓✓✓\n\n"+
        "SOMEHOW STILL SURVIVING. 💀",
        28
    );

    await wait(3200);

    /* MUSIC */

    await typeText(
        "AFRIN'S VIBES 🎧\n\n"+
        "Headphones ON.\n"+
        "World OFF. 🌎\n\n"+
        "Music when happy.\n"+
        "Music when sad.\n"+
        "Music when angry.\n"+
        "Music when doing absolutely nothing. 😂\n\n"+
        "Basically...\n"+
        "MUSIC = THERAPY. 🎶❤️",
        28
    );

    await wait(3200);

    /* MOVIES */

    await typeText(
        "CINEMA MODE 🎬🍿\n\n"+
        "Movie buff detected.\n\n"+
        "Mass scene = 🔥\n"+
        "Romance = ❤️\n"+
        "Emotional scene = 😭\n"+
        "Good plot = OBSESSED.\n\n"+
        "One thing is certain:\n\n"+
        "A GOOD MOVIE WILL NEVER\n"+
        "BE LEFT UNWATCHED. 😂",
        28
    );

    await wait(3200);

    /* BOOKS + FOOD */

    await typeText(
        "OTHER SIDE QUESTS 📚🍜\n\n"+
        "Reading books. 📖\n"+
        "Trying new dishes. 🍜\n"+
        "Exploring random things. 👀\n"+
        "Watching Netflix. 🎬\n\n"+
        "Because apparently\n"+
        "ONE HOBBY WAS NOT ENOUGH. 😂",
        28
    );

    await wait(3200);

    /* CHARACTER ANALYSIS */

    await typeText(
        "CHARACTER ANALYSIS 🧠\n\n"+
        "Quick learner.\n"+
        "Adapts fast.\n"+
        "Explains things to friends.\n"+
        "Dedicated when something matters.\n\n"+
        "BUT...\n\n"+
        "When pressure arrives:\n\n"+
        "ANGER.EXE\n"+
        "HAS STOPPED RESPONDING. 💀",
        28
    );

    await wait(3500);

    /* DREAMS */

    await typeText(
        "THE REAL GOAL 💫\n\n"+
        "Not just getting a job.\n\n"+
        "Building a life where\n"+
        "she can stand on her own.\n\n"+
        "Earn her own money.\n"+
        "Make her own decisions.\n"+
        "Build her own future.\n\n"+
        "INDEPENDENCE MODE: 🔥",
        30
    );

    await wait(3500);

    /* HIDDEN SIDE */

    await typeText(
        "BEHIND THE CHARACTER...\n\n"+
        "There is someone who has faced\n"+
        "failures and difficult moments.\n\n"+
        "Sometimes emotional.\n"+
        "Sometimes confused.\n"+
        "Sometimes completely exhausted.\n\n"+
        "But somehow...\n\n"+
        "SHE KEEPS MOVING FORWARD. ❤️",
        30
    );

    await wait(3500);

    /* FRIENDS */

    await typeText(
        "PEOPLE WHO MATTER 🫶\n\n"+
        "Some people enter your life\n"+
        "and simply become part of your story.\n\n"+
        "The friends who make you laugh.\n"+
        "The friends who listen.\n"+
        "The friends who roast you. 😂\n"+
        "The friends who stay.\n\n"+
        "Those memories?\n\n"+
        "PRICELESS. ❤️",
        28
    );

    await wait(3500);

    /* FINAL REPORT */

    app.innerHTML = `
        <div class="box">

            <div class="warning">
                ✨ FINAL CHARACTER REPORT ✨
            </div>

            <div class="huge">
                AFRIN ❤️
            </div>

            <div class="text">
                Not perfect.

                Not always confident.

                Sometimes confused.

                Sometimes emotional.

                Sometimes completely chaotic. 😂

                But still...

                SHE'S BECOMING THE PERSON
                SHE ALWAYS WANTED TO BE. 👑
            </div>

        </div>
    `;

    await wait(4000);

    /* SECRET */

    app.innerHTML = `
        <div class="box">

            <div class="warning">
                🔐 CLASSIFIED
            </div>

            <div class="big">
                WAIT...
            </div>

            <div class="text">
                There is one more thing
                hidden inside AFRIN.EXE. 👀

                Think you're brave enough?
            </div>

            <button onclick="secretMessage()">
                🔓 OPEN SECRET
            </button>

        </div>
    `;

    await wait(7000);

    /* AUTO FINAL */

    app.innerHTML = `
        <div class="box">

            <div class="huge">
                👑
            </div>

            <div class="big">
                MAIN CHARACTER MODE
                ACTIVATED.
            </div>

            <div class="text">
                This isn't the end.

                This is just the beginning. ✨

                AFRIN.EXE
                IS STILL LOADING...
            </div>

            <div class="small">
                © Main Character Energy
            </div>

        </div>
    `;

    /* FINAL BLAST */

    for(let i=0;i<30;i++){

        setTimeout(() => {
            createHeart();
        },i*120);

    }

    for(let i=0;i<50;i++){

        setTimeout(() => {
            createSpark();
        },i*80);

    }

    for(let i=0;i<80;i++){

        setTimeout(() => {
            createConfetti();
        },i*40);

    }

}

start();

</script>

</body>
</html>
```
