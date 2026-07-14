
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InkySwot — Concepts (story canvas)</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&family=Crimson+Pro:ital,wght@0,300;0,400;0,600;1,400&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0f0d0a; --panel:#18120d; --panel2:#0c0a07; --text:#e8e0d0; --text2:#b0a090; --muted:#706050;
    --gold:#c9923a; --gold-bright:#e8b060; --border2:#352815; --sketch:#5c5040;
    --mono:'JetBrains Mono',monospace; --body:'Crimson Pro',Georgia,serif; --head:'Playfair Display',serif;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  html,body{height:100%;}
  body{font-family:var(--body);background:var(--bg);color:var(--text);min-height:100vh;}
  .screen{display:flex;min-height:100vh;}
  .divide{width:1px;background:var(--border2);}
  .left{width:38%;padding:40px 44px;opacity:.32;}
  .left h1{font-family:var(--head);font-weight:900;font-size:28px;}
  .left .sub{font-style:italic;font-size:14px;color:var(--text2);letter-spacing:1px;text-transform:uppercase;margin-top:4px;}
  .proj-card{margin-top:26px;width:280px;border:1px solid var(--border2);border-radius:6px;padding:16px 18px;background:var(--panel);}
  .proj-card .g{font-family:var(--mono);font-size:10px;letter-spacing:1.4px;color:var(--gold);}
  .proj-card .t{font-family:var(--head);font-weight:900;font-size:19px;margin:6px 0;}
  .right{flex:1;padding:40px 44px 90px;position:relative;}
  .right h1{font-family:var(--head);font-weight:900;font-size:28px;margin-bottom:8px;}
  .right .hint{font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:.4px;margin-bottom:26px;}

  .folders{display:flex;flex-direction:column;gap:8px;}
  .folder-row{display:flex;align-items:flex-start;position:relative;}
  .folder-bar{display:flex;align-items:center;gap:8px;height:30px;padding:0 12px;width:210px;flex:none;
    border-radius:7px;cursor:pointer;border:1px solid;position:relative;z-index:2;
    background:var(--fbg,#241a12);border-color:var(--fbd,#4a3a28);color:var(--ftx,#e8e0d0);}
  .folder-caret{font-size:11px;transition:transform .2s;color:var(--ftx);opacity:.85;}
  .folder-row.open .folder-caret{transform:rotate(90deg);}
  .folder-name{flex:1;font-family:var(--mono);font-size:11px;font-weight:500;letter-spacing:1.4px;text-transform:uppercase;color:var(--ftx);}
  .folder-count{font-family:var(--mono);font-size:10px;opacity:.7;color:var(--ftx);}
  .add-btn{width:18px;height:18px;border-radius:4px;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:14px;line-height:1;opacity:.6;cursor:pointer;color:var(--ftx);}
  .add-btn:hover{opacity:1;}
  .folder-dot{width:13px;height:13px;border-radius:4px;cursor:pointer;border:1px solid rgba(0,0,0,.35);opacity:.75;background:var(--fbd);}
  .folder-dot:hover{opacity:1;}
  .fp{display:none;position:absolute;left:0;top:34px;z-index:9;align-items:center;gap:7px;padding:8px 10px;border-radius:9px;background:var(--panel);border:1px solid var(--border2);box-shadow:0 12px 28px rgba(0,0,0,.55);}
  .fp.open{display:flex;}
  .fp-sw{width:18px;height:18px;border-radius:5px;cursor:pointer;border:2px solid transparent;transition:transform .12s;}
  .fp-sw:hover{transform:scale(1.15);}
  .fp-sw.active{border-color:var(--gold-bright);}

  .folder-out{display:none;align-items:flex-start;position:absolute;left:210px;top:0;}
  .folder-row.open .folder-out{display:flex;}
  .connector{width:40px;height:30px;flex:none;position:relative;}
  .connector::before{content:"";position:absolute;left:0;top:15px;width:100%;border-top:1px dashed var(--muted);}
  .stories{display:flex;flex-direction:column;gap:8px;}
  .story-bar{display:flex;align-items:center;gap:8px;height:30px;padding:0 13px;width:250px;cursor:pointer;border-radius:6px;border:1px solid var(--border2);background:var(--panel2);font-family:var(--body);font-size:15px;color:var(--text);}
  .story-bar:hover{border-color:var(--gold);color:var(--gold-bright);}
  .story-bar .st-name{flex:1;}
  .story-bar .st-go{font-family:var(--mono);font-size:12px;color:var(--muted);}
  .story-bar:hover .st-go{color:var(--gold);}
  .story-add{width:250px;height:30px;padding:0 13px;display:flex;align-items:center;gap:7px;cursor:pointer;border-radius:6px;border:1px dashed var(--border2);background:transparent;font-family:var(--mono);font-size:11px;letter-spacing:.6px;color:var(--muted);}
  .story-add:hover{border-color:var(--gold);color:var(--gold-bright);}
  .new-folder{position:absolute;right:44px;bottom:34px;font-family:var(--mono);font-size:12px;letter-spacing:.8px;padding:10px 18px;border-radius:6px;background:var(--gold);color:#0a0806;font-weight:500;display:inline-flex;align-items:center;gap:7px;cursor:pointer;}

  /* ════ story card = pop-up holding a resizable canvas ════ */
  .scrim{position:fixed;inset:0;z-index:100;background:rgba(8,6,4,.72);display:flex;align-items:center;justify-content:center;padding:20px;opacity:0;pointer-events:none;transition:opacity .24s;}
  .scrim.open{opacity:1;pointer-events:auto;}
  .note{position:relative;width:94vw;min-width:560px;max-width:96vw;height:90vh;min-height:420px;max-height:94vh;background:var(--panel);color:var(--text);border-radius:8px;display:flex;flex-direction:column;border:1px solid var(--border2);
    box-shadow:0 30px 70px rgba(0,0,0,.65),0 0 0 1px rgba(201,146,58,.18);opacity:0;transform:translateY(10px) scale(.985);transition:opacity .24s;
    resize:both;overflow:hidden;}
  .scrim.open .note{opacity:1;transform:none;}
  .note-head{display:flex;align-items:center;gap:12px;padding:13px 16px;border-bottom:1px solid var(--border2);}
  .note-title{flex:1;border:none;outline:none;background:transparent;font-family:var(--head);font-weight:900;font-size:22px;color:var(--text);padding:0;}
  .note-title::placeholder{color:var(--muted);font-weight:400;font-style:italic;font-family:var(--body);}
  .add-idea{font-family:var(--mono);font-size:11px;letter-spacing:.5px;padding:7px 13px;border-radius:6px;cursor:pointer;background:var(--gold);color:#0a0806;font-weight:500;border:none;display:inline-flex;align-items:center;gap:6px;}
  .add-idea:hover{background:var(--gold-bright);}
  .note-x{background:transparent;border:none;cursor:pointer;padding:5px;border-radius:4px;font-family:var(--mono);font-size:16px;color:var(--muted);display:flex;}
  .note-x:hover{background:#120d08;color:var(--text);}

  /* the canvas — fills the space; the whole pop-up resizes, so head+foot grow with it */
  .canvas{position:relative;flex:1;min-height:180px;overflow:hidden;
    background:var(--panel2);background-image:radial-gradient(var(--border2) 1px,transparent 1px);background-size:22px 22px;}
  .canvas-empty{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:.5px;pointer-events:none;}

  /* header-band idea card on the canvas */
  .ic{position:absolute;width:230px;z-index:2;cursor:grab;}
  .ic:active{cursor:grabbing;}
  .ic-tab{display:inline-flex;align-items:baseline;height:24px;margin-left:12px;padding:0 14px;border:1px solid;border-bottom:none;border-radius:8px 8px 0 0;}
  .ic-tab .lab{font-family:var(--mono);font-size:10px;font-weight:500;letter-spacing:1.1px;text-transform:uppercase;line-height:1;}
  .ic-tab .dot{font-family:var(--mono);font-size:14px;font-weight:700;line-height:1;margin-left:1px;}
  .ic-body{border-radius:0 0 6px 6px;padding:10px 12px;border:1px solid;min-height:80px;}
  .ic-body textarea{width:100%;min-height:62px;border:none;outline:none;resize:none;background:transparent;font-family:var(--body);font-size:16px;line-height:1.4;color:var(--text);overflow:hidden;}
  .ic-body textarea::placeholder{opacity:.45;font-style:italic;}
  .ic-del{position:absolute;top:-6px;right:-6px;width:18px;height:18px;border-radius:50%;background:var(--panel);border:1px solid var(--border2);color:var(--muted);font-size:12px;line-height:1;display:none;align-items:center;justify-content:center;cursor:pointer;z-index:3;}
  .ic:hover .ic-del{display:flex;}
  .ic-del:hover{border-color:#c43a2a;color:#c43a2a;}

  .note-foot{display:flex;align-items:center;justify-content:flex-end;gap:10px;padding:11px 18px;border-top:1px solid var(--border2);}
  .foot-btn{font-family:var(--mono);font-size:11px;letter-spacing:.6px;padding:8px 14px;border-radius:5px;cursor:pointer;border:1px solid var(--border2);background:transparent;color:var(--text2);}
  .foot-btn:hover{border-color:var(--muted);color:var(--text);}
  .foot-btn.primary{background:var(--gold);color:#0a0806;border-color:var(--gold);font-weight:500;}

  /* AI assist buttons up the right edge */
  .ai-stack{position:absolute;top:56px;left:calc(100% + 10px);display:flex;flex-direction:column;gap:10px;}
  .ai-btn{font-family:var(--mono);font-size:12px;letter-spacing:.4px;padding:9px 15px;border-radius:6px;cursor:pointer;background:#120d08;border:1px solid var(--gold);color:var(--gold-bright);display:inline-flex;align-items:center;gap:7px;white-space:nowrap;}
  .ai-btn:hover{background:var(--gold);color:#0a0806;}
  .ai-btn:hover svg{stroke:#0a0806 !important;}

  /* Add Idea grouped dropdown */
  .ai-menu{display:none;position:absolute;top:46px;right:44px;z-index:20;width:230px;max-height:380px;overflow:auto;
    background:var(--panel);border:1px solid var(--border2);border-radius:9px;box-shadow:0 16px 40px rgba(0,0,0,.6);padding:6px;
    scrollbar-width:thin;scrollbar-color:var(--border2) transparent;}
  .ai-menu.open{display:block;}
  .ai-grp{font-family:var(--mono);font-size:9.5px;letter-spacing:1.4px;text-transform:uppercase;color:var(--gold);padding:9px 10px 5px;display:flex;align-items:center;gap:7px;}
  .ai-opt{padding:8px 10px 8px 26px;font-family:var(--body);font-size:15px;color:var(--text);cursor:pointer;border-radius:5px;display:flex;align-items:center;gap:9px;}
  .ai-opt:hover{background:var(--panel2);}
  .ai-opt .oc{width:10px;height:10px;border-radius:3px;flex:none;}

  /* +FOLDER genre picker */
  .gp-scrim{position:fixed;inset:0;z-index:120;background:rgba(8,6,4,.6);display:none;align-items:center;justify-content:center;}
  .gp-scrim.open{display:flex;}
  .gp{width:340px;max-height:70vh;background:var(--panel);border:1px solid var(--border2);border-radius:9px;display:flex;flex-direction:column;box-shadow:0 24px 60px rgba(0,0,0,.6);}
  .gp-head{padding:14px 16px;border-bottom:1px solid var(--border2);font-family:var(--mono);font-size:11px;letter-spacing:1.4px;text-transform:uppercase;color:var(--gold);}
  .gp-list{overflow:auto;padding:6px;scrollbar-width:thin;scrollbar-color:var(--border2) transparent;}
  .gp-opt{padding:9px 12px;font-family:var(--body);font-size:16px;color:var(--text);cursor:pointer;border-radius:5px;}
  .gp-opt:hover{background:var(--panel2);}
  .gp-opt.coming{color:var(--muted);cursor:default;}
  .gp-opt.coming::after{content:" · coming soon";font-family:var(--mono);font-size:9px;letter-spacing:.6px;color:var(--muted);}
</style>
</head>
<body>
  <div class="screen">
    <div class="left">
      <h1>My Projects</h1><div class="sub">Publish and be damned</div>
      <div class="proj-card"><div class="g">FANTASY</div><div class="t">The Man Who Learnt to Fly</div></div>
    </div>
    <div class="divide"></div>
    <div class="right">
      <h1>Ideas</h1>
      <div class="hint">click a genre → a story title opens its canvas · Add Idea drops a card · drag cards · resize the canvas from its corner</div>
      <div class="folders" id="folders">
        <div class="folder-row" data-folder>
          <div class="folder-bar" data-folder-bar>
            <span class="folder-caret">&#9656;</span><span class="folder-name">Romance</span><span class="folder-count">[2]</span>
            <span class="folder-dot" title="Change colour" data-folder-dot></span><span class="add-btn" title="Add a story" data-add-story>+</span>
          </div>
          <div class="fp" data-fp></div>
          <div class="folder-out"><div class="connector"></div><div class="stories">
            <div class="story-bar" data-story data-title="The Lighthouse Keeper"><span class="st-name">The Lighthouse Keeper</span><span class="st-go">→</span></div>
            <div class="story-bar" data-story data-title="Two Weeks in Devon"><span class="st-name">Two Weeks in Devon</span><span class="st-go">→</span></div>
            <div class="story-add" data-add-story><span>+</span> New story</div>
          </div></div>
        </div>
      </div>
      <div class="new-folder" id="newFolder">+ FOLDER</div>
    </div>
  </div>

  <!-- story card pop-up -->
  <div class="scrim" id="scrim">
    <div class="note" id="note">
      <div class="note-head">
        <input class="note-title" id="noteTitle" placeholder="Story title…" />
        <button class="add-idea" id="addIdea">+ Add Idea</button>
        <button class="note-x" id="closeBtn" title="Close">✕</button>
      </div>
      <div class="ai-menu" id="aiMenu"></div>
      <div class="canvas" id="canvas"><div class="canvas-empty" id="canvasEmpty">Add Idea → pick a category → a card lands here</div></div>
      <div class="note-foot">
        <button class="foot-btn" id="cancelBtn">Close</button>
        <button class="foot-btn primary" id="keepBtn">Save story</button>
      </div>
      <div class="ai-stack">
        <button class="ai-btn"><svg viewBox="0 0 24 24" width="13" height="13" fill="none" stroke="#e8b060" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3l1.9 5.8L20 10.7l-5.1 3.7L16.8 21 12 17.3 7.2 21l1.9-6.6L4 10.7l6.1-1.9L12 3z"/></svg> Prompt</button>
        <button class="ai-btn"><svg viewBox="0 0 24 24" width="13" height="13" fill="none" stroke="#e8b060" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 3-6.7L3 8"/><path d="M3 3v5h5"/></svg> Expand</button>
      </div>
    </div>
  </div>

  <!-- +FOLDER genre picker -->
  <div class="gp-scrim" id="gpScrim"><div class="gp"><div class="gp-head">Choose a genre for your new folder</div><div class="gp-list" id="gpList"></div></div></div>

<script>
(function(){
  /* genre folder palette — six deep track tints */
  var PALETTE=[{fbg:"#3a2c10",fbd:"#c9923a",ftx:"#e8c583"},{fbg:"#123230",fbd:"#5fa898",ftx:"#8fd0c2"},
    {fbg:"#3a2410",fbd:"#cf7f57",ftx:"#e0a878"},{fbg:"#1a2740",fbd:"#7a9bd0",ftx:"#a7c0e8"},
    {fbg:"#2e2036",fbd:"#a07d9a",ftx:"#c8a8c2"},{fbg:"#3a1818",fbd:"#c45b48",ftx:"#e09080"}];
  function paintFolder(bar,i){var c=PALETTE[i%PALETTE.length];bar.style.setProperty('--fbg',c.fbg);bar.style.setProperty('--fbd',c.fbd);bar.style.setProperty('--ftx',c.ftx);bar.dataset.pi=i%PALETTE.length;}

  /* the grouped category list — the platform's side menu; cards colour by family */
  var GROUPS=[
    {name:"Cast", glyph:"♟", fam:{bg:"#3a2410",bd:"#cf7f57",tx:"#e0a878"}, items:["Characters","Relationships","Factions & Orgs","Language & Dialogue"]},
    {name:"World",glyph:"◎", fam:{bg:"#123230",bd:"#5fa898",tx:"#8fd0c2"}, items:["Locations","Buildings","Objects & Artefacts","Rules & Lore"]},
    {name:"Plot", glyph:"⟁", fam:{bg:"#2e2036",bd:"#a07d9a",tx:"#c8a8c2"}, items:["Plot Threads","Subplots","Themes & Motifs","Events & Timeline"]}
  ];

  var GENRES=[{name:"Academic Essay / Thesis"},{name:"Adventure"},{name:"Audio Drama",coming:true},{name:"Audiobook",coming:true},{name:"Autobiography / Memoir"},{name:"Biography"},{name:"Children's Book"},{name:"Comedy / Humour"},{name:"Comic Script",coming:true},{name:"Coming of Age"},{name:"Cookbook"},{name:"Crime & Thriller"},{name:"Drama"},{name:"Dystopian"},{name:"Erotic"},{name:"Essay Collection"},{name:"Fantasy"},{name:"Flash Fiction"},{name:"Game Script",coming:true},{name:"Gothic"},{name:"Graphic Novel",coming:true},{name:"Historical Fiction"},{name:"History"},{name:"Horror"},{name:"Literary Fiction"},{name:"Literary Journal"},{name:"Non-Fiction"},{name:"Novel"},{name:"Novella"},{name:"Other"},{name:"Paranormal"},{name:"Personal Essay / Creative Non-Fiction"},{name:"Picture Book",coming:true},{name:"Poetry",coming:true},{name:"Poetry Collection",coming:true},{name:"Radio Drama",coming:true},{name:"Romance"},{name:"Science Fiction"},{name:"Screenplay",coming:true},{name:"Self-Help"},{name:"Short Story"},{name:"Speculative Fiction"},{name:"Stage Play",coming:true},{name:"Teleplay",coming:true},{name:"Thriller & Suspense"},{name:"Travel Writing"},{name:"True Crime"},{name:"Urban & Contemporary"},{name:"Western"}];

  /* ---- folders open/close + colour picker ---- */
  function buildPicker(row){var fp=row.querySelector('[data-fp]');if(!fp||fp.dataset.built)return;fp.dataset.built='1';
    PALETTE.forEach(function(c,i){var sw=document.createElement('span');sw.className='fp-sw';sw.style.background=c.fbd;sw.dataset.pi=i;
      sw.addEventListener('click',function(e){e.stopPropagation();paintFolder(row.querySelector('[data-folder-bar]'),i);fp.querySelectorAll('.fp-sw').forEach(function(s){s.classList.remove('active')});sw.classList.add('active');fp.classList.remove('open');});fp.appendChild(sw);});}
  function wireFolder(bar){var row=bar.closest('[data-folder]');buildPicker(row);
    bar.addEventListener('click',function(e){
      if(e.target.closest('[data-folder-dot]')){e.stopPropagation();var fp=row.querySelector('[data-fp]');document.querySelectorAll('[data-fp].open').forEach(function(o){if(o!==fp)o.classList.remove('open')});var pi=bar.dataset.pi||0;fp.querySelectorAll('.fp-sw').forEach(function(s){s.classList.toggle('active',s.dataset.pi==pi)});fp.classList.toggle('open');return;}
      if(e.target.closest('[data-add-story]')){e.stopPropagation();alert('(demo) + adds a new story');return;}
      row.classList.toggle('open');});}
  var existing=document.querySelectorAll('[data-folder-bar]');existing.forEach(function(bar,i){paintFolder(bar,i);wireFolder(bar);});
  document.addEventListener('click',function(){document.querySelectorAll('[data-fp].open').forEach(function(o){o.classList.remove('open')});});
  var folderCount=existing.length;
  document.querySelectorAll('.story-add').forEach(function(a){a.addEventListener('click',function(e){e.stopPropagation();alert('(demo) + adds a new story');});});

  /* ---- story card pop-up ---- */
  var scrim=document.getElementById('scrim'),note=document.getElementById('note'),title=document.getElementById('noteTitle'),
      canvas=document.getElementById('canvas'),canvasEmpty=document.getElementById('canvasEmpty'),
      aiMenu=document.getElementById('aiMenu'),addIdea=document.getElementById('addIdea');
  function openStory(t){title.value=t||'';scrim.classList.add('open');}
  function close(){scrim.classList.remove('open');aiMenu.classList.remove('open');}
  document.querySelectorAll('[data-story]').forEach(function(s){s.addEventListener('click',function(){openStory(s.dataset.title);});});
  document.getElementById('closeBtn').addEventListener('click',close);
  document.getElementById('cancelBtn').addEventListener('click',close);
  document.getElementById('keepBtn').addEventListener('click',close);
  scrim.addEventListener('mousedown',function(e){if(e.target===scrim)close();});
  document.addEventListener('keydown',function(e){if(e.key==='Escape'){close();document.getElementById('gpScrim').classList.remove('open');}});

  /* build the Add Idea grouped dropdown */
  GROUPS.forEach(function(g){
    var h=document.createElement('div');h.className='ai-grp';h.innerHTML='<span>'+g.glyph+'</span> '+g.name;aiMenu.appendChild(h);
    g.items.forEach(function(it){
      var o=document.createElement('div');o.className='ai-opt';
      o.innerHTML='<span class="oc" style="background:'+g.fam.bd+'"></span>'+it;
      o.addEventListener('click',function(e){e.stopPropagation();addCard(it,g.fam);aiMenu.classList.remove('open');});
      aiMenu.appendChild(o);
    });
  });
  addIdea.addEventListener('click',function(e){e.stopPropagation();aiMenu.classList.toggle('open');});
  document.addEventListener('mousedown',function(e){if(!aiMenu.contains(e.target)&&e.target!==addIdea)aiMenu.classList.remove('open');});

  /* drop a header-band card onto the canvas, coloured by family */
  var cardN=0;
  function addCard(label,fam){
    canvasEmpty.style.display='none';
    var x=24+(cardN%4)*52, y=20+(cardN%4)*44; cardN++;
    var ic=document.createElement('div');ic.className='ic';ic.style.left=x+'px';ic.style.top=y+'px';
    ic.innerHTML='<button class="ic-del" title="Remove">&times;</button>'+
      '<div class="ic-tab" style="background:'+fam.bg+';border-color:'+fam.bd+';color:'+fam.tx+'"><span class="lab">'+label+'</span><span class="dot">.</span></div>'+
      '<div class="ic-body" style="background:'+fam.bg+';border-color:'+fam.bd+'"><textarea placeholder="Write your idea…"></textarea></div>';
    canvas.appendChild(ic);
    var ta=ic.querySelector('textarea');var grow=function(){ta.style.height='auto';ta.style.height=ta.scrollHeight+'px';};ta.addEventListener('input',grow);setTimeout(grow,0);
    ta.addEventListener('pointerdown',function(e){e.stopPropagation();});
    ic.querySelector('.ic-del').addEventListener('click',function(e){e.stopPropagation();ic.remove();if(!canvas.querySelector('.ic'))canvasEmpty.style.display='flex';});
    /* drag within the canvas */
    ic.addEventListener('pointerdown',function(e){
      if(e.target.closest('textarea')||e.target.closest('.ic-del'))return;
      var r=canvas.getBoundingClientRect();var sx=e.clientX,sy=e.clientY,ox=ic.offsetLeft,oy=ic.offsetTop;
      ic.setPointerCapture(e.pointerId);ic.style.zIndex=10;
      function mv(ev){var nx=ox+(ev.clientX-sx),ny=oy+(ev.clientY-sy);
        nx=Math.max(0,Math.min(nx,canvas.clientWidth-ic.offsetWidth));ny=Math.max(0,Math.min(ny,canvas.clientHeight-ic.offsetHeight));
        ic.style.left=nx+'px';ic.style.top=ny+'px';}
      function up(){ic.releasePointerCapture(e.pointerId);ic.removeEventListener('pointermove',mv);ic.removeEventListener('pointerup',up);ic.style.zIndex=2;}
      ic.addEventListener('pointermove',mv);ic.addEventListener('pointerup',up);
    });
  }

  /* +FOLDER genre picker */
  var gpScrim=document.getElementById('gpScrim'),gpList=document.getElementById('gpList');
  GENRES.forEach(function(g){var o=document.createElement('div');o.className='gp-opt'+(g.coming?' coming':'');o.textContent=g.name;if(!g.coming)o.addEventListener('click',function(){makeFolder(g.name);gpScrim.classList.remove('open');});gpList.appendChild(o);});
  document.getElementById('newFolder').addEventListener('click',function(){gpScrim.classList.add('open');});
  gpScrim.addEventListener('mousedown',function(e){if(e.target===gpScrim)gpScrim.classList.remove('open');});
  function makeFolder(name){var row=document.createElement('div');row.className='folder-row';row.setAttribute('data-folder','');
    row.innerHTML='<div class="folder-bar" data-folder-bar><span class="folder-caret">&#9656;</span><span class="folder-name">'+name+'</span><span class="folder-count">[0]</span><span class="folder-dot" title="Change colour" data-folder-dot></span><span class="add-btn" data-add-story>+</span></div><div class="fp" data-fp></div><div class="folder-out"><div class="connector"></div><div class="stories"><div class="story-add" data-add-story><span>+</span> New story</div></div></div>';
    document.getElementById('folders').appendChild(row);var bar=row.querySelector('[data-folder-bar]');paintFolder(bar,folderCount++);wireFolder(bar);
    row.querySelector('.story-add').addEventListener('click',function(e){e.stopPropagation();alert('(demo) + adds a new story');});}
})();
</script>
</body>
</html>

