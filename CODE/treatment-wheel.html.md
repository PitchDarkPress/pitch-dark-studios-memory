<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InkySwot — the wheel</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&family=Crimson+Pro:wght@300;400;600&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0f0d0a; --bg2:#18120d; --bg3:#221a14; --bg0:#0a0806;
    --ink:#e8e0d0; --ink2:#b0a090; --ink3:#706050;
    --gold:#c9923a; --gold2:#e8b060; --rule:#221709; --rule2:#352815;
    --page:#f7f4ec; --pageink:#221a14; --pagemute:#8a7d68;
    --char:#cba36a; --loc:#5fa898; --evt:#b08a6a; --chap:#9a8fb0;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  html,body{height:100%;}
  *{scrollbar-width:thin;scrollbar-color:var(--rule2) transparent;}
  *::-webkit-scrollbar{width:10px;height:10px;}
  *::-webkit-scrollbar-track{background:transparent;}
  *::-webkit-scrollbar-thumb{background:var(--rule2);border-radius:6px;border:2px solid var(--bg0);}
  *::-webkit-scrollbar-thumb:hover{background:var(--gold);}
  body{height:100vh;font-family:'Crimson Pro',Georgia,serif;background:var(--bg);color:var(--ink);overflow:hidden;}
  .app{display:grid;grid-template-rows:52px 1fr;grid-template-columns:230px 1fr;height:100vh;}

  .header{grid-column:1/-1;background:var(--bg2);border-bottom:1px solid var(--rule);display:flex;align-items:center;padding:0 16px;gap:14px;z-index:90;}
  .wordmark{font-family:'Playfair Display',serif;font-size:26px;font-weight:900;}
  .sep{width:1px;height:22px;background:var(--rule2);}
  .proj{font-style:italic;font-size:16px;color:var(--ink2);}
  .hr{margin-left:auto;font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.08em;color:var(--ink3);display:flex;align-items:center;gap:14px;}
  .backview{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.06em;color:var(--ink2);
    border:1px solid var(--rule2);border-radius:4px;padding:5px 12px;cursor:pointer;background:transparent;display:none;align-items:center;gap:7px;}
  .backview:hover{color:var(--gold);border-color:var(--gold);}
  body.writing .backview{display:inline-flex;}

  .sidebar{background:var(--bg2);border-right:1px solid var(--rule);overflow-y:auto;}
  .sec{padding:14px 0;border-bottom:1px solid var(--rule);}
  .sec-title{font-family:'JetBrains Mono',monospace;font-size:12px;letter-spacing:.2em;text-transform:uppercase;color:var(--gold);padding:0 16px;margin-bottom:7px;}
  .grp{font-family:'JetBrains Mono',monospace;font-size:14px;color:var(--ink2);padding:7px 16px 4px;display:flex;align-items:center;gap:9px;}
  .item{display:flex;align-items:center;gap:9px;padding:6px 16px;cursor:pointer;font-family:'JetBrains Mono',monospace;font-size:14px;color:var(--ink2);border-left:2px solid transparent;}
  .item.sub{padding-left:30px;font-size:13px;}
  .item:hover{background:var(--bg3);color:var(--ink);}
  .item.active{background:var(--bg3);color:var(--gold);border-left-color:var(--gold);}
  .item.open{color:var(--ink);border-left-color:var(--ink3);}
  .ic{width:15px;text-align:center;flex-shrink:0;}
  .nm{flex:1;}
  .ct{font-family:'JetBrains Mono',monospace;font-size:12px;color:var(--gold);background:rgba(201,146,58,.1);
    border:1px solid rgba(201,146,58,.25);border-radius:10px;padding:1px 8px;min-width:22px;text-align:center;}
  .ct.zero{color:var(--ink3);background:transparent;border-color:var(--rule2);}

  .content{position:relative;overflow:hidden;background:var(--bg0);}
  .scroller{position:absolute;inset:0;overflow:auto;}
  .stage{position:relative;width:1340px;margin:0 auto 0 300px;padding:40vh 0 60vh;}
  body.writing .stage{padding:34px 0 80px;}

  .sheet{background:var(--page);color:var(--pageink);width:760px;margin:0 0 26px;
    min-height:980px;border-radius:2px;box-shadow:0 8px 44px rgba(0,0,0,.5);position:relative;
    padding:80px 84px 100px;font-family:'Crimson Pro',serif;}
  .page-title{font-family:'Playfair Display',serif;font-size:28px;font-weight:900;color:var(--pageink);text-align:center;margin-bottom:4px;}
  .page-by{font-family:'Crimson Pro',serif;font-style:italic;font-size:16px;color:var(--pagemute);text-align:center;margin-bottom:34px;}

  .chapter{margin-bottom:30px;}
  .ch-h{font-family:'Playfair Display',serif;font-size:20px;font-weight:900;color:var(--pageink);
    border-bottom:1px solid #ded6c6;padding-bottom:7px;margin-bottom:16px;}
  .scene{margin:0 0 20px;}
  .sc-h{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.14em;text-transform:uppercase;
    color:var(--pagemute);margin-bottom:11px;display:flex;align-items:baseline;gap:8px;}
  .sc-h b{color:var(--pageink);font-weight:500;}
  .sc-h .ttl{font-family:'Crimson Pro',serif;font-size:15px;letter-spacing:0;text-transform:none;color:#5a4a38;font-style:italic;}
  .sc-h .add{font-family:'Crimson Pro',serif;font-size:13px;letter-spacing:0;text-transform:none;color:#b8ad97;font-style:italic;cursor:text;}

  .event{margin:0 0 16px 14px;padding-left:14px;border-left:2px solid #e0d8c8;}
  .ev-t{font-size:18px;color:var(--pageink);margin-bottom:2px;}
  .ev-write{margin-top:6px;color:#b8ad97;font-style:italic;font-size:14px;cursor:text;padding:3px 0;}
  .ev-write:hover{color:var(--gold);}

  .writing-surface{display:none;}
  body.writing .sheet > .page-title,
  body.writing .sheet > .page-by,
  body.writing .sheet > .chapter{display:none;}
  body.writing .sheet > .writing-surface{display:block;}
  .ws-scene{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.14em;text-transform:uppercase;
    color:var(--pagemute);margin-bottom:8px;display:flex;align-items:baseline;gap:8px;}
  .ws-scene b{color:var(--pageink);font-weight:500;}
  .ws-scene .add{font-family:'Crimson Pro',serif;font-size:13px;letter-spacing:0;text-transform:none;color:#b8ad97;font-style:italic;}
  .ws-event{font-size:20px;color:var(--pageink);margin-bottom:16px;}
  .ws-area{width:100%;min-height:760px;border:none;outline:none;resize:none;background:transparent;
    font-family:'Crimson Pro',serif;font-size:18px;line-height:1.8;color:var(--pageink);}
  .ws-area::placeholder{color:#c3b9a4;font-style:italic;}

  /* ===== THE WHEEL ===== */
  #wheel{position:absolute;top:0;bottom:0;left:50%;margin-left:300px;width:480px;
    pointer-events:none;z-index:40;overflow:hidden;}
  .wlabel{position:absolute;left:0;white-space:nowrap;pointer-events:auto;cursor:pointer;
    font-family:'Crimson Pro',serif;font-size:21px;color:var(--ink);
    transition:top .22s ease,opacity .22s ease;}
  .wlabel:hover{color:var(--gold);}
  .wlabel.live::after{content:'';position:absolute;left:100%;top:50%;margin-left:16px;
    width:360px;height:0;border-top:1px solid var(--gold);opacity:.5;}
  .wcentre{position:absolute;left:0;right:0;height:0;border-top:1px solid rgba(201,146,58,.18);}
  .wcentre::before{content:'';position:absolute;left:-14px;top:-3px;width:6px;height:6px;border-radius:50%;
    background:var(--gold);box-shadow:0 0 8px rgba(201,146,58,.6);}

  /* ===== THE ENTITY POP-UP (left of the workspace) ===== */
  /* Static for now: list view only. No drag, no record, no copy yet. */
  #popup{position:absolute;top:30px;left:24px;width:248px;z-index:70;
    background:var(--bg2);border:1px solid var(--rule2);border-radius:3px;
    box-shadow:0 14px 50px rgba(0,0,0,.55);display:none;}
  #popup.shown{display:block;}
  .pu-head{display:flex;align-items:center;gap:8px;padding:12px 14px 11px;border-bottom:1px solid var(--rule);cursor:grab;}
  .pu-head:active{cursor:grabbing;}
  .pu-kicker{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.18em;text-transform:uppercase;flex:1;}
  .pu-x{font-family:'JetBrains Mono',monospace;font-size:14px;color:var(--ink3);cursor:pointer;line-height:1;padding:2px 4px;}
  .pu-x:hover{color:var(--gold);}
  .pu-list{max-height:60vh;overflow-y:auto;padding:6px 0 4px;}
  .pu-entry{padding:13px 16px 0;cursor:pointer;}
  .pu-entry:hover .pu-sub{color:var(--gold2);}
  .pu-sub{font-family:'Crimson Pro',serif;font-weight:600;font-size:17px;line-height:1.25;margin-bottom:2px;}
  .pu-desc{font-family:'Crimson Pro',serif;font-weight:300;font-size:14px;line-height:1.4;color:var(--ink2);margin-bottom:11px;}
  .pu-end{height:0;border-top:1px solid;opacity:.5;margin:0 16px 0;}
  .pu-entry:last-child .pu-end{margin-bottom:4px;}

  /* ===== RECORD VIEW (same panel, swaps in) ===== */
  .pu-back{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.08em;
    color:var(--ink3);cursor:pointer;padding:11px 16px 9px;display:flex;align-items:center;gap:6px;}
  .pu-back:hover{color:var(--gold);}
  .pu-record{padding:4px 16px 16px;}
  .pu-rec-name{font-family:'Crimson Pro',serif;font-weight:600;font-size:21px;line-height:1.2;margin-bottom:3px;}
  .pu-rec-kind{font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.16em;text-transform:uppercase;color:var(--ink3);margin-bottom:13px;}
  .pu-field{margin-bottom:13px;}
  .pu-fdiv{height:0;border-top:1px solid;opacity:.4;margin:0 0 13px;}
  .pu-field-head{display:flex;align-items:baseline;gap:8px;margin-bottom:3px;}
  .pu-field-label{font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.14em;text-transform:uppercase;color:var(--ink3);flex:1;}
  .pu-copy{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.12em;text-transform:uppercase;
    color:var(--ink3);cursor:pointer;opacity:1;transition:color .15s;}
  .pu-copy:hover{color:var(--gold);}
  .pu-copy.done{color:var(--gold2);}
  .pu-field-val{font-family:'Crimson Pro',serif;font-weight:300;font-size:15px;line-height:1.5;color:var(--ink);}
  .pu-rec-end{height:0;border-top:1px solid;opacity:.55;margin-top:4px;}

  .tip{position:fixed;bottom:14px;left:246px;font-family:'JetBrains Mono',monospace;font-size:9px;
    letter-spacing:.1em;color:var(--ink3);text-transform:uppercase;opacity:.5;z-index:90;}
</style>
</head>
<body>
<div class="app">

  <div class="header">
    <span class="wordmark">InkySwot</span>
    <span class="sep"></span>
    <span class="proj">A Christmas Carol</span>
    <span class="hr">
      <span class="backview" onclick="exitWriting()">‹ overview</span>
      <span id="modeNote">the wheel · centre = where you are</span>
    </span>
  </div>

  <aside class="sidebar">
    <div class="sec">
      <div class="sec-title">Navigate</div>
      <div class="item"><span class="ic">⊞</span><span class="nm">My Projects</span></div>
      <div class="item active"><span class="ic">✒</span><span class="nm">Write</span></div>
    </div>
    <div class="sec">
      <div class="sec-title">Project</div>
      <div class="item"><span class="ic">◈</span><span class="nm">Overview</span></div>
      <div class="grp"><span class="ic">♟</span> Cast</div>
      <div class="item sub" data-pop="characters"><span class="ic">·</span><span class="nm">Characters</span><span class="ct">5</span></div>
      <div class="item sub" data-pop="locations"><span class="ic">·</span><span class="nm">Locations</span><span class="ct">3</span></div>
      <div class="grp"><span class="ic">⟁</span> Plot</div>
      <div class="item sub" data-pop="events"><span class="ic">·</span><span class="nm">Events &amp; Timeline</span><span class="ct">7</span></div>
      <div class="grp"><span class="ic">≡</span> Chapters</div>
      <div class="item sub" data-pop="chapters"><span class="ic">·</span><span class="nm">Chapters</span><span class="ct">5</span></div>
      <div class="item sub"><span class="ic">·</span><span class="nm">The Treatment</span></div>
    </div>
  </aside>

  <main class="content" id="content">
    <div class="scroller" id="scroller">
      <div class="stage" id="stage">
        <div class="sheet" id="sheet">
          <div class="page-title">A Christmas Carol</div>
          <div class="page-by">by Charles Dickens</div>

          <div class="chapter">
            <div class="ch-h" data-rail data-label="Stave One — Marley's Ghost">Stave One — Marley's Ghost</div>
            <div class="scene">
              <div class="sc-h" data-rail data-label="Scene 1 — The Counting-House"><b>Scene 1</b><span class="ttl">— The Counting-House</span></div>
              <div class="event">
                <div class="ev-t" data-rail data-label="Scrooge at his counting-house">Scrooge at his counting-house</div>
                <div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div>
              </div>
              <div class="event">
                <div class="ev-t" data-rail data-label="Fred arrives with Christmas cheer">Fred arrives with Christmas cheer</div>
                <div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div>
              </div>
              <div class="event">
                <div class="ev-t" data-rail data-label="The charity men are turned away">The charity men are turned away</div>
                <div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div>
              </div>
            </div>
            <div class="scene">
              <div class="sc-h" data-rail data-label="Scene 2 — untitled"><b>Scene 2</b><span class="add">+ add a title</span></div>
              <div class="event">
                <div class="ev-t" data-rail data-label="The knocker becomes Marley's face">The knocker becomes Marley's face</div>
                <div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div>
              </div>
            </div>
          </div>

          <div class="chapter">
            <div class="ch-h" data-rail data-label="Stave Two — The First of the Three Spirits">Stave Two — The First of the Three Spirits</div>
            <div class="scene">
              <div class="sc-h" data-rail data-label="Scene 1 — The Old School"><b>Scene 1</b><span class="ttl">— The Old School</span></div>
              <div class="event">
                <div class="ev-t" data-rail data-label="The Ghost of Christmas Past appears">The Ghost of Christmas Past appears</div>
                <div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div>
              </div>
              <div class="event">
                <div class="ev-t" data-rail data-label="The lonely boy at school">The lonely boy at school</div>
                <div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div>
              </div>
              <div class="event">
                <div class="ev-t" data-rail data-label="Fezziwig's Christmas party">Fezziwig's Christmas party</div>
                <div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div>
              </div>
            </div>
          </div>

          <div class="writing-surface" id="ws">
            <div class="ws-scene" id="wsScene"></div>
            <div class="ws-event" id="wsEvent"></div>
            <textarea class="ws-area" id="wsArea" placeholder="Write the scene here…"></textarea>
          </div>

        </div>
      </div>
    </div>

    <!-- the entity pop-up — list view, static for now -->
    <div id="popup">
      <div class="pu-head">
        <span class="pu-kicker" id="puKicker">Characters · 5</span>
        <span class="pu-x" onclick="closePopup()">✕</span>
      </div>
      <div class="pu-list" id="puList"></div>
    </div>

    <div id="wheel">
      <div class="wcentre" id="wcentre"></div>
    </div>
  </main>
</div>

<div class="tip" id="tip">click a counted nav section — the list opens on the left</div>

<script>
  const body=document.body;
  const content=document.getElementById('content');
  const scroller=document.getElementById('scroller');
  const sheet=document.getElementById('sheet');
  const wheel=document.getElementById('wheel');
  const wcentre=document.getElementById('wcentre');
  const ws=document.getElementById('ws');
  const wsScene=document.getElementById('wsScene');
  const wsEvent=document.getElementById('wsEvent');
  const wsArea=document.getElementById('wsArea');

  let writingMode=false;
  let currentIndex=0;
  const drafts={};

  /* ===== THE ENTITY POP-UP DATA (sample Carol data) ===== */
  const popData={
    characters:{ label:'Characters', colour:'var(--char)', items:[
      {sub:'Ebenezer Scrooge', desc:'A cold, solitary miser; the counting-house its own master.',
       fields:[
        ['Role','Protagonist'],
        ['Description','A squeezing, wrenching, grasping, scraping, clutching, covetous old sinner; hard and sharp as flint, from which no steel had ever struck out generous fire; secret, and self-contained, and solitary as an oyster. The cold within him froze his old features, nipped his pointed nose, shrivelled his cheek, stiffened his gait, made his eyes red, his thin lips blue.'],
        ['Manner','He carried his own low temperature always about with him; he iced his office in the dog-days, and didn\u2019t thaw it one degree at Christmas. External heat and cold had little influence on him. No warmth could warm, no wintry weather chill him.'],
        ['Arc','From miser to merciful, walked there across one night by three spirits \u2014 Past, Present, and Yet to Come. By morning he is light as a feather, happy as an angel, merry as a schoolboy, giddy as a drunken man.'],
        ['Relationships','Nephew Fred (warm, rejected); clerk Bob Cratchit (underpaid, then raised); dead partner Jacob Marley (the first warning); the boy Tiny Tim, whom he comes to cherish.'],
        ['Key line','\u201CI will honour Christmas in my heart, and try to keep it all the year.\u201D'],
        ['Notes (private)','Watch the thaw \u2014 it must be earned scene by scene, never sudden. The turn at Fezziwig\u2019s is where the first crack shows.'],
       ]},
      {sub:'Jacob Marley', desc:'Scrooge\u2019s dead partner; returns in chains as the first warning.',
       fields:[['Role','The first warning'],['Description','Dead these seven years; appears bound in the chains he forged in life.'],['Note','Sets the whole night in motion.']]},
      {sub:'Bob Cratchit', desc:'Scrooge\u2019s underpaid clerk; warm where his master is cold.',
       fields:[['Role','Scrooge\u2019s clerk'],['Description','Toils for fifteen shillings a week; father to a large, loving family.'],['Family','Father of Tiny Tim.']]},
      {sub:'Fred', desc:'Scrooge\u2019s nephew; arrives full of Christmas cheer and refused.',
       fields:[['Role','Scrooge\u2019s nephew'],['Description','Ruddy, warm, and good-humoured; keeps Christmas in his heart despite his uncle.']]},
      {sub:'Tiny Tim', desc:'The Cratchits\u2019 youngest; frail, hopeful, the story\u2019s tender heart.',
       fields:[['Role','The Cratchits\u2019 youngest'],['Description','Bears a little crutch; frail of body but bright of spirit.'],['Line','\u201CGod bless us, every one!\u201D']]},
    ]},
    locations:{ label:'Locations', colour:'var(--loc)', items:[
      {sub:'The Counting-House', desc:'Scrooge\u2019s place of business; bleak, cold, candle-lit.',
       fields:[['Type','Place of business'],['Description','A dismal little cell; the fire a single coal, the clerk\u2019s smaller still.']]},
      {sub:'Scrooge\u2019s Chambers', desc:'His gloomy rooms; where the knocker becomes a face.',
       fields:[['Type','Dwelling'],['Description','A gloomy suite of rooms in a lowering pile of building; dark, for darkness was cheap.']]},
      {sub:'The Cratchit Home', desc:'Small and poor, but bright with family at Christmas.',
       fields:[['Type','Family home'],['Description','Four rooms in Camden Town; poor, but warm with love and a modest goose.']]},
    ]},
    events:{ label:'Events & Timeline', colour:'var(--evt)', items:[
      {sub:'Scrooge at his counting-house', desc:'The miser at work on Christmas Eve.',
       fields:[['When','Christmas Eve'],['Characters','Scrooge, Bob Cratchit'],['Location','The Counting-House']]},
      {sub:'Fred arrives with Christmas cheer', desc:'The nephew\u2019s invitation, coldly refused.',
       fields:[['When','Christmas Eve'],['Characters','Scrooge, Fred'],['Location','The Counting-House']]},
      {sub:'The charity men are turned away', desc:'Scrooge denies the poor; \u201Care there no prisons?\u201D',
       fields:[['When','Christmas Eve'],['Characters','Scrooge'],['Location','The Counting-House']]},
      {sub:'The knocker becomes Marley\u2019s face', desc:'The first supernatural sign at his door.',
       fields:[['When','Christmas Eve, night'],['Characters','Scrooge, Marley'],['Location','Scrooge\u2019s Chambers']]},
      {sub:'The Ghost of Christmas Past appears', desc:'The first spirit comes at the stroke of one.',
       fields:[['When','One o\u2019clock'],['Characters','Scrooge'],['Location','Scrooge\u2019s Chambers']]},
      {sub:'The lonely boy at school', desc:'Scrooge sees his abandoned younger self.',
       fields:[['When','Christmas past'],['Characters','Young Scrooge'],['Location','The Old School']]},
      {sub:'Fezziwig\u2019s Christmas party', desc:'A warm memory of a generous old master.',
       fields:[['When','Christmas past'],['Characters','Fezziwig, Young Scrooge'],['Location','Fezziwig\u2019s warehouse']]},
    ]},
    chapters:{ label:'Chapters', colour:'var(--chap)', items:[
      {sub:'Stave One — Marley\u2019s Ghost', desc:'Marley dead; Scrooge warned by his old partner.',
       fields:[['Scenes','2'],['Characters','Scrooge, Marley, Fred, Bob Cratchit']]},
      {sub:'Stave Two — The First of the Three Spirits', desc:'Christmas Past walks Scrooge through his youth.',
       fields:[['Scenes','1'],['Characters','Scrooge, Ghost of Christmas Past, Fezziwig']]},
      {sub:'Stave Three — The Second of the Three Spirits', desc:'Christmas Present; the Cratchits and the city.',
       fields:[['Scenes','—'],['Characters','Scrooge, Ghost of Christmas Present, the Cratchits']]},
      {sub:'Stave Four — The Last of the Spirits', desc:'Christmas Yet to Come; the silent, pointing ghost.',
       fields:[['Scenes','—'],['Characters','Scrooge, Ghost of Christmas Yet to Come']]},
      {sub:'Stave Five — The End of It', desc:'Scrooge wakes changed; the morning of mercy.',
       fields:[['Scenes','—'],['Characters','Scrooge, Bob Cratchit, Fred']]},
    ]},
  };

  const popup=document.getElementById('popup');
  const puKicker=document.getElementById('puKicker');
  const puList=document.getElementById('puList');
  let openSection=null;

  document.querySelectorAll('.item[data-pop]').forEach(it=>{
    it.addEventListener('click',()=>openPopup(it.getAttribute('data-pop'),it));
  });

  function openPopup(key,navEl){
    const d=popData[key];
    if(!d) return;
    document.querySelectorAll('.item.open').forEach(e=>e.classList.remove('open'));
    if(navEl) navEl.classList.add('open');
    openSection=key;
    showList();
    popup.classList.add('shown');
  }

  function showList(){
    const d=popData[openSection];
    puKicker.textContent=d.label+' \u00B7 '+d.items.length;
    puKicker.style.color=d.colour;
    puList.innerHTML='';
    d.items.forEach((item,i)=>{
      const e=document.createElement('div');
      e.className='pu-entry';
      e.innerHTML=
        '<div class="pu-sub" style="color:'+d.colour+'">'+item.sub+'</div>'+
        '<div class="pu-desc">'+item.desc+'</div>'+
        '<div class="pu-end" style="border-color:'+d.colour+'"></div>';
      e.addEventListener('click',()=>showRecord(i));
      puList.appendChild(e);
    });
  }

  function showRecord(i){
    const d=popData[openSection];
    const item=d.items[i];
    puKicker.textContent=d.label;
    puKicker.style.color=d.colour;
    let fields='';
    (item.fields||[]).forEach((f,fi)=>{
      if(fi>0) fields+='<div class="pu-fdiv" style="border-color:'+d.colour+'"></div>';
      fields+='<div class="pu-field">'+
                '<div class="pu-field-head">'+
                  '<span class="pu-field-label">'+f[0]+'</span>'+
                  '<span class="pu-copy" data-copy="'+fi+'">copy</span>'+
                '</div>'+
                '<div class="pu-field-val">'+f[1]+'</div>'+
              '</div>';
    });
    puList.innerHTML=
      '<div class="pu-back" onclick="backToList()">\u2039 back to list</div>'+
      '<div class="pu-record">'+
        '<div class="pu-rec-name" style="color:'+d.colour+'">'+item.sub+'</div>'+
        '<div class="pu-rec-kind">'+d.label.replace(/ &amp;.*/,'').replace(/s$/,'')+'</div>'+
        fields+
        '<div class="pu-rec-end" style="border-color:'+d.colour+'"></div>'+
      '</div>';
    // wire per-field copy — text only
    puList.querySelectorAll('.pu-copy').forEach(btn=>{
      btn.addEventListener('click',e=>{
        e.stopPropagation();
        const text=item.fields[+btn.getAttribute('data-copy')][1];
        const plain=text.replace(/&amp;/g,'&').replace(/&quot;/g,'"');
        navigator.clipboard&&navigator.clipboard.writeText(plain);
        btn.textContent='copied';
        btn.classList.add('done');
        setTimeout(()=>{btn.textContent='copy';btn.classList.remove('done');},1400);
      });
    });
  }

  function backToList(){ showList(); }
  window.backToList=backToList;

  function closePopup(){
    popup.classList.remove('shown');
    document.querySelectorAll('.item.open').forEach(e=>e.classList.remove('open'));
    openSection=null;
  }
  window.closePopup=closePopup;

  /* ===== DRAG BY THE HEADER ===== */
  (function(){
    const head=popup.querySelector('.pu-head');
    let dragging=false, sx=0, sy=0, ox=0, oy=0;
    head.addEventListener('mousedown',e=>{
      if(e.target.classList.contains('pu-x')) return; // the ✕ still closes
      dragging=true;
      const r=popup.getBoundingClientRect();
      const pr=popup.offsetParent.getBoundingClientRect();
      ox=r.left-pr.left; oy=r.top-pr.top;
      sx=e.clientX; sy=e.clientY;
      popup.style.left=ox+'px'; popup.style.top=oy+'px';
      e.preventDefault();
    });
    window.addEventListener('mousemove',e=>{
      if(!dragging) return;
      popup.style.left=(ox+e.clientX-sx)+'px';
      popup.style.top=(oy+e.clientY-sy)+'px';
    });
    window.addEventListener('mouseup',()=>{ dragging=false; });
  })();

  /* ===== THE WHEEL ===== */
  const rows=[...sheet.querySelectorAll('[data-rail]')].map(h=>({h,label:h.getAttribute('data-label')}));

  rows.forEach((r,i)=>{
    const el=document.createElement('div');
    el.className='wlabel';
    el.textContent=r.label;
    el.addEventListener('click',()=>{
      if(writingMode){ openForWriting(i); }
      else if(el.classList.contains('live')){ openForWriting(i); }
      else { rollToCentre(r.h); }
    });
    wheel.appendChild(el);
    r.el=el;
  });

  function rollToCentre(h){
    const rect=h.getBoundingClientRect();
    const cBox=content.getBoundingClientRect();
    const target=scroller.scrollTop+(rect.top-cBox.top)-(cBox.height/2)+rect.height/2;
    scroller.scrollTo({top:target,behavior:'smooth'});
  }

  function enterWriting(writeEl){
    const evt=writeEl.previousElementSibling;
    const idx=rows.findIndex(r=>r.h===evt);
    openForWriting(idx<0?0:idx);
  }

  function openForWriting(idx){
    if(writingMode) drafts[currentIndex]=wsArea.value;
    currentIndex=idx;
    const r=rows[idx];
    const scene=r.h.closest('.scene');
    const sc=scene?scene.querySelector('.sc-h'):null;
    wsScene.innerHTML = sc ? sc.innerHTML : '';
    wsEvent.textContent = r.h.classList.contains('ev-t') ? r.label : '';
    wsArea.value = drafts[idx]||'';
    body.classList.add('writing');
    writingMode=true;
    document.getElementById('modeNote').textContent='writing · use the wheel to move';
    scroller.scrollTo({top:0,behavior:'auto'});
    paintWheel(idx);
    setTimeout(()=>wsArea.focus(),120);
  }

  function exitWriting(){
    drafts[currentIndex]=wsArea.value;
    body.classList.remove('writing');
    writingMode=false;
    document.getElementById('modeNote').textContent='the wheel · centre = where you are';
    requestAnimationFrame(()=>{ rollToCentre(rows[currentIndex].h); requestAnimationFrame(turnFromScroll); });
  }
  window.exitWriting=exitWriting;

  const TIGHT=46, GAP=170;
  const WINDOW=3;
  function placeBelt(cur){
    const cBox=content.getBoundingClientRect();
    const centreY=cBox.height/2;
    wcentre.style.top=centreY+'px';
    const curI=Math.round(cur);
    rows.forEach((r,i)=>{
      const steps=i-curI;
      const within=Math.abs(steps)<=WINDOW;
      let y,op;
      if(steps===0){ y=centreY; op=1; }
      else if(steps<0){ y=centreY-GAP-(-steps-1)*TIGHT; }
      else { y=centreY+GAP+(steps-1)*TIGHT; }
      if(steps===0) op=1;
      else if(!within) op=0;
      else op=Math.max(0.12, 0.62 - (Math.abs(steps)-1)*0.16);
      r.el.style.top=(y-13)+'px';
      r.el.style.opacity=op;
      r.el.style.pointerEvents = within?'auto':'none';
      const live=(steps===0);
      r.el.style.color=live?'var(--gold2)':'var(--ink)';
      r.el.classList.toggle('live',live);
    });
  }

  function paintWheel(idx){ placeBelt(idx); }

  let targetFrac=0, shownFrac=0, easing=false;
  function measureFrac(){
    const cBox=content.getBoundingClientRect();
    const centreY=cBox.height/2;
    const ys=rows.map(r=>{const rect=r.h.getBoundingClientRect();return (rect.top-cBox.top)+rect.height/2;});
    let frac=0;
    if(centreY<=ys[0])frac=0;
    else if(centreY>=ys[ys.length-1])frac=ys.length-1;
    else for(let i=0;i<ys.length-1;i++){
      if(centreY>=ys[i]&&centreY<=ys[i+1]){const span=ys[i+1]-ys[i];frac=i+(span?(centreY-ys[i])/span:0);break;}
    }
    return frac;
  }
  function easeLoop(){
    const diff=targetFrac-shownFrac;
    if(Math.abs(diff)<0.002){ shownFrac=targetFrac; placeBelt(shownFrac); easing=false; return; }
    shownFrac += diff*0.072;
    placeBelt(shownFrac);
    requestAnimationFrame(easeLoop);
  }
  function turnFromScroll(){
    if(writingMode) return;
    targetFrac=measureFrac();
    if(!easing){ easing=true; requestAnimationFrame(easeLoop); }
  }

  window.addEventListener('load',()=>{ turnFromScroll(); scroller.scrollTo({top:1}); requestAnimationFrame(turnFromScroll); });
  window.addEventListener('resize',()=>{ writingMode?paintWheel(currentIndex):turnFromScroll(); });
  let ticking=false;
  scroller.addEventListener('scroll',()=>{
    if(!ticking){ requestAnimationFrame(()=>{ turnFromScroll(); ticking=false; }); ticking=true; }
  },{passive:true});
</script>
</body>
</html>