
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InkySwot — quick note · component</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Crimson+Pro:wght@300;400;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  /* the three vars the scrap needs */
  :root{ --paper:#e7c986; --paper-edge:#d8b365; --paperink:#2a2016; }
  *{box-sizing:border-box;margin:0;padding:0;}
  html,body{height:100%;}

  /* ── DEMO HARNESS — delete when dropping into the platform ───────── */
  body{height:100vh;background:#0a0806;overflow:hidden;font-family:'Crimson Pro',Georgia,serif;}
  #content{position:absolute;inset:0;overflow:hidden;}      /* HOST: loose notes float here */
  #scroller{position:absolute;inset:0;overflow:auto;}
  #stage{position:relative;min-height:220vh;}                /* STAGE: pinned notes anchor here */
  .demo-hint{position:absolute;top:26px;left:50%;transform:translateX(-50%);width:520px;max-width:80%;
    text-align:center;font-family:'JetBrains Mono',monospace;font-size:11px;line-height:1.7;
    letter-spacing:.06em;color:#5a4d36;}
  .demo-trigger{position:fixed;right:26px;bottom:24px;z-index:9000;cursor:pointer;border:none;
    font-family:'JetBrains Mono',monospace;font-size:12px;letter-spacing:.1em;color:#0a0806;
    background:linear-gradient(160deg,#e8b060,#c9923a);padding:11px 16px;border-radius:24px;
    box-shadow:0 10px 28px rgba(0,0,0,.5);}
  .demo-trigger:hover{filter:brightness(1.06);}
  /* ────────────────────────────────────────────────────────────────── */

  /* ════════════════════════════════════════════════════════════════
     QUICK NOTE — STYLES   (lift this block whole)
     needs: --paper, --paper-edge, --paperink + Crimson Pro & JetBrains Mono
     ════════════════════════════════════════════════════════════════ */
  .note{position:absolute;width:312px;z-index:60;--pin:#c45b48;
    background:linear-gradient(160deg,var(--paper),var(--paper-edge));
    color:var(--paperink);border-radius:3px;
    box-shadow:0 22px 50px rgba(0,0,0,.55),0 4px 10px rgba(0,0,0,.4);
    transform-origin:50% 50%;
    transition:opacity .22s ease, transform .26s cubic-bezier(.4,.0,.2,1);}
  .note-grip{position:absolute;right:0;bottom:0;width:24px;height:24px;
    cursor:nwse-resize;border-radius:0 0 3px 0;
    background:linear-gradient(135deg,transparent 50%,rgba(0,0,0,.16) 50%);}
  .note-grip:hover{background:linear-gradient(135deg,transparent 50%,rgba(42,32,22,.34) 50%);}
  .note.in{animation:drop .26s cubic-bezier(.34,1.4,.5,1);}
  @keyframes drop{from{opacity:0;transform:translateY(-14px) scale(.96);} to{opacity:1;}}

  .note-head{display:flex;align-items:center;
    padding:8px 10px 6px;cursor:grab;gap:6px;}
  .note-head:active{cursor:grabbing;}
  .note-tools{display:flex;align-items:center;gap:4px;margin-left:auto;}

  /* colour palette — a small popup, opens on pin, closes once a colour is picked */
  .note-palette{display:none;position:absolute;top:34px;left:50%;transform:translateX(-50%);z-index:8;
    align-items:center;gap:8px;padding:8px 11px;border-radius:11px;
    background:#fdf6e6;border:1px solid rgba(42,32,22,.28);box-shadow:0 12px 28px rgba(0,0,0,.42);}
  .note-palette.open{display:flex;}
  .note-swatch{width:16px;height:16px;border-radius:50%;border:2px solid transparent;cursor:pointer;padding:0;
    transition:transform .12s ease;}
  .note-swatch:hover{transform:scale(1.18);}
  .note-swatch.active{border-color:rgba(42,32,22,.6);box-shadow:0 0 0 1px rgba(255,255,255,.6);}
  .note-x{background:transparent;border:none;cursor:pointer;padding:3px;
    display:flex;align-items:center;line-height:1;border-radius:3px;
    font-family:'JetBrains Mono',monospace;font-size:13px;color:#9a7a3e;}
  .note-x:hover{background:rgba(42,32,22,.1);color:#8a3320;}

  /* loose state — gold thumbtack, sitting on the note */
  .note-pin-tab{position:absolute;top:6px;left:50%;transform:translateX(-50%);
    background:transparent;border:none;cursor:pointer;padding:3px;z-index:6;
    display:flex;align-items:center;line-height:1;color:#9a7a3e;border-radius:3px;
    transition:transform .14s ease,color .14s ease;}
  .note-pin-tab svg{width:26px;height:26px;display:block;}
  .note-pin-tab:hover{color:var(--paperink);transform:translateX(-50%) translateY(-2px);}

  /* pinned state — same thumbtack shape as the outline, filled with the pin colour */
  .note-pin-tack{display:none;position:absolute;top:6px;left:50%;transform:translateX(-50%);
    background:transparent;border:none;cursor:pointer;padding:3px;z-index:6;
    filter:drop-shadow(0 1px 1px rgba(0,0,0,.35));transition:transform .14s ease,filter .14s ease;}
  .note-pin-tack svg{width:26px;height:26px;display:block;}
  .note-pin-tack .pin-head{fill:var(--pin);stroke:rgba(0,0,0,.28);stroke-width:1;}
  .note-pin-tack .pin-needle{fill:none;stroke:var(--pin);stroke-width:2.4;stroke-linecap:round;}
  .note-pin-tack:hover{transform:translateX(-50%) translateY(-2px);}

  .note.pinned .note-pin-tab{display:none;}
  .note.pinned .note-pin-tack{display:block;}
  .note.pinned{box-shadow:0 22px 50px rgba(0,0,0,.55),0 4px 10px rgba(0,0,0,.4),0 0 0 1px rgba(176,122,22,.45);}

  .note-body{padding:0 16px 4px;}
  .note-area{width:100%;min-height:200px;overflow:hidden;border:none;outline:none;resize:none;background:transparent;
    font-family:'Crimson Pro',serif;font-size:21px;line-height:1.45;color:var(--paperink);}
  .note-area::placeholder{color:rgba(42,32,22,.4);font-style:italic;}
  /* ════════════════════════════════════════════════════════════════ */
</style>
</head>
<body>

  <!-- ── DEMO HARNESS — delete when integrating ── -->
  <div id="content">
    <div id="scroller">
      <div id="stage">
        <div class="demo-hint">quick-note component · press N or tap ＋ to summon<br>pin one (gold tack → red pushpin), then scroll — it sticks to the page; loose notes float</div>
      </div>
    </div>
  </div>
  <button id="trigger" class="demo-trigger">＋ note · N</button>
  <!-- ───────────────────────────────────────────── -->

<script>
/* ════════════════════════════════════════════════════════════════
   STILL TO ADD (note for next time)
   1. PERSIST — notes should stay where they're dropped and survive a
      refresh. In this file that's browser memory; in the platform it
      should save into the InkySwot database.
   2. SEE ALL — one button that shows every note at once, wherever each
      is pinned. (Still to decide: a panel that lists them, or gather
      the actual notes onto the screen.)
   Dropped: notes do NOT hold images — images live in the Research section.
   ════════════════════════════════════════════════════════════════ */
/* ════════════════════════════════════════════════════════════════
   QUICK NOTE — SCRIPT   (lift this block whole)
   Wire two host references:
     HOST  = layer fixed in the viewport — loose scraps float here
     STAGE = the scrolling scene/page container — pinned scraps anchor here
   Optional hook:  window.QuickNoteOnKeep = function(text){ … file to Notes pad … }
   Call summonNote() from wherever you summon (a key, a button, the keypad).
   ════════════════════════════════════════════════════════════════ */
(function(){
  const HOST  = document.getElementById('content');   // ← map to the platform's viewport layer
  const STAGE = document.getElementById('stage');      // ← map to the platform's scrolling page
  let noteZ = 60;

  function summonNote(){
    const n=HOST.querySelectorAll('.note').length;
    const off=Math.min(n,6)*22;

    const note=document.createElement('div');
    note.className='note in';
    note.style.left=(150+off)+'px';
    note.style.top=(90+off)+'px';
    note.style.zIndex=++noteZ;
    note.innerHTML=
      '<button class="note-pin-tack" title="Unpin">'+
        '<svg viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round">'+
          '<path class="pin-needle" d="M12 17v5"/>'+
          '<path class="pin-head" d="M9 10.76V4a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v6.76a2 2 0 0 0 .59 1.42l1.12 1.12A1 1 0 0 1 17 15H7a1 1 0 0 1-.71-1.7l1.12-1.12A2 2 0 0 0 9 10.76Z"/>'+
        '</svg>'+
      '</button>'+
      '<button class="note-pin-tab" title="Pin to this scene"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 17v5"/><path d="M9 10.76V4a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v6.76a2 2 0 0 0 .59 1.42l1.12 1.12A1 1 0 0 1 17 15H7a1 1 0 0 1-.71-1.7l1.12-1.12A2 2 0 0 0 9 10.76Z"/></svg></button>'+
      '<div class="note-head"><span class="note-tools">'+
        '<button class="note-x" title="Delete">\u2715</button>'+
      '</span></div>'+
      '<div class="note-palette">'+
        '<button class="note-swatch" data-c="#c9923a" style="background:#c9923a" title="Events"></button>'+
        '<button class="note-swatch" data-c="#5fa898" style="background:#5fa898" title="Locations"></button>'+
        '<button class="note-swatch" data-c="#cf7f57" style="background:#cf7f57" title="Characters"></button>'+
        '<button class="note-swatch" data-c="#7a9bd0" style="background:#7a9bd0" title="Objects"></button>'+
        '<button class="note-swatch" data-c="#a07d9a" style="background:#a07d9a" title="Themes"></button>'+
        '<button class="note-swatch active" data-c="#c45b48" style="background:#c45b48" title="Tension"></button>'+
      '</div>'+
      '<div class="note-body"><textarea class="note-area" placeholder="jot the thought…"></textarea></div>'+
      '<div class="note-grip"></div>';
    HOST.appendChild(note);

    const area=note.querySelector('.note-area');
    note.addEventListener('mousedown',()=>{ note.style.zIndex=++noteZ; });   /* raise to front */

    /* auto-grow so the scrap deepens with the text — never a scrollbar */
    let minH=200;
    const grow=()=>{ area.style.height='auto'; area.style.height=Math.max(area.scrollHeight,minH)+'px'; };
    area.addEventListener('input',grow);
    setTimeout(grow,0);

    /* corner resize — drag the folded corner */
    const grip=note.querySelector('.note-grip');
    let rz=false,gx=0,gy=0,sw=0,sh=0;
    grip.addEventListener('mousedown',e=>{ rz=true; gx=e.clientX; gy=e.clientY; sw=note.offsetWidth; sh=minH; e.preventDefault(); });
    window.addEventListener('mousemove',e=>{
      if(!rz) return;
      note.style.width=Math.max(220, sw+(e.clientX-gx))+'px';
      minH=Math.max(140, sh+(e.clientY-gy));
      grow();
    });
    window.addEventListener('mouseup',()=>{ rz=false; });

    /* delete / keep */
    const bin=()=>{ note.style.opacity='0'; note.style.transform='scale(.92)'; setTimeout(()=>note.remove(),200); };
    const keep=()=>{
      const txt=area.value.trim();
      if(!txt){ bin(); return; }
      note.style.opacity='0'; note.style.transform='scale(.94)'; setTimeout(()=>note.remove(),200);
      if(typeof window.QuickNoteOnKeep==='function') window.QuickNoteOnKeep(txt);   /* file to Notes pad in the platform */
    };

    /* pin (anchor to the scene so it scrolls with the page) + delete */
    const pinTab=note.querySelector('.note-pin-tab');
    const pinTack=note.querySelector('.note-pin-tack');
    const xBtn=note.querySelector('.note-x');
    function setPinned(on){
      const r=note.getBoundingClientRect();
      if(on){
        const sr=STAGE.getBoundingClientRect();
        STAGE.appendChild(note);                 /* lives in the scrolling page now */
        note.style.left=(r.left-sr.left)+'px';
        note.style.top=(r.top-sr.top)+'px';
        note.classList.add('pinned');
        openPalette();
      } else {
        const cr=HOST.getBoundingClientRect();
        HOST.appendChild(note);                  /* back to floating over the view */
        note.style.left=(r.left-cr.left)+'px';
        note.style.top=(r.top-cr.top)+'px';
        note.classList.remove('pinned');
        closePalette();
      }
    }
    const togglePin=()=>setPinned(!note.classList.contains('pinned'));
    xBtn.addEventListener('click',e=>{ e.stopPropagation(); bin(); });

    /* colour palette — a small popup; opens on pin, closes once a colour is picked or you click away */
    const palette=note.querySelector('.note-palette');
    function openPalette(){ palette.classList.add('open'); setTimeout(()=>document.addEventListener('mousedown',paletteOutside),0); }
    function closePalette(){ palette.classList.remove('open'); document.removeEventListener('mousedown',paletteOutside); }
    function paletteOutside(e){ if(!palette.contains(e.target)) closePalette(); }
    note.querySelectorAll('.note-swatch').forEach(sw=>{
      sw.addEventListener('click',e=>{
        e.stopPropagation();
        note.style.setProperty('--pin', sw.dataset.c);
        note.querySelectorAll('.note-swatch').forEach(s=>s.classList.remove('active'));
        sw.classList.add('active');
        closePalette();
      });
    });

    /* the pin: a clean click toggles pinned; a drag moves the note (so a pinned scrap still moves) */
    function pinPointer(e){
      e.stopPropagation();
      beginDrag(e);
      const up=()=>{ window.removeEventListener('mouseup',up); if(!moved) togglePin(); };
      window.addEventListener('mouseup',up);
    }
    pinTab.addEventListener('mousedown',pinPointer);
    pinTack.addEventListener('mousedown',pinPointer);

    area.addEventListener('keydown',e=>{
      if(note.classList.contains('pinned')) return;   /* pinned scraps just edit */
      if(e.key==='Enter' && !e.shiftKey){ e.preventDefault(); keep(); }
      else if(e.key==='Escape'){ e.preventDefault(); bin(); }
    });

    /* drag — by the head, or by the pin (handlers above) */
    const head=note.querySelector('.note-head');
    let dragging=false,moved=false,sx=0,sy=0,ox=0,oy=0;
    function beginDrag(e){
      dragging=true; moved=false;
      const r=note.getBoundingClientRect();
      const pr=note.offsetParent.getBoundingClientRect();
      ox=r.left-pr.left; oy=r.top-pr.top; sx=e.clientX; sy=e.clientY;
      note.style.transition='opacity .22s ease';
      e.preventDefault();
    }
    head.addEventListener('mousedown',e=>{
      if(e.target.closest('.note-tools') || e.target.closest('.note-palette')) return;
      beginDrag(e);
    });
    window.addEventListener('mousemove',e=>{
      if(!dragging) return;
      if(Math.abs(e.clientX-sx)>3 || Math.abs(e.clientY-sy)>3) moved=true;
      note.style.left=(ox+e.clientX-sx)+'px';
      note.style.top=(oy+e.clientY-sy)+'px';
    });
    window.addEventListener('mouseup',()=>{ if(dragging){ dragging=false; note.style.transition=''; } });

    setTimeout(()=>area.focus(),60);
    setTimeout(()=>note.classList.remove('in'),300);
  }

  window.summonNote = summonNote;   /* call this from your summon key / button / keypad */

  /* demo triggers — remove with the harness */
  document.getElementById('trigger') && document.getElementById('trigger').addEventListener('click',summonNote);
  document.addEventListener('keydown',e=>{
    const typing=document.activeElement && document.activeElement.classList.contains('note-area');
    if(!typing && (e.key==='n'||e.key==='N')){ e.preventDefault(); summonNote(); }
  });
})();
</script>
</body>
</html>
