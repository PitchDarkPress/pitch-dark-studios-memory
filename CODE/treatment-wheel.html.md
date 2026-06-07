
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
  .app{display:grid;grid-template-rows:52px 1fr;grid-template-columns:230px 1fr 230px;height:100vh;}

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
  .sidebar.right{border-right:none;border-left:1px solid var(--rule);}
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
  .stage{position:relative;width:1340px;margin:0 auto 0 300px;padding:28px 0 60vh;}
  body.writing .stage{padding:28px 0 80px;}

  /* one scene per full page */
  .sheet{background:var(--page);color:var(--pageink);width:816px;margin:0 0 26px;
    min-height:1056px;border-radius:2px;box-shadow:0 8px 44px rgba(0,0,0,.5);position:relative;
    padding:54px 64px 110px;font-family:'Crimson Pro',serif;}
  .page-head{position:absolute;top:18px;right:24px;font-family:'Crimson Pro',serif;
    font-size:13px;color:var(--pagemute);text-align:right;}

  .ch-h{font-family:'JetBrains Mono',monospace;font-size:13px;letter-spacing:.14em;text-transform:uppercase;
    font-weight:500;color:var(--pageink);border-bottom:1px solid #ded6c6;padding-bottom:6px;margin-bottom:22px;}
  .sc-h{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.14em;text-transform:uppercase;
    color:var(--pagemute);margin-bottom:20px;display:flex;align-items:baseline;gap:8px;}
  .sc-h b{color:var(--pageink);font-weight:500;}
  .sc-h .ttl{font-family:'Crimson Pro',serif;font-size:15px;letter-spacing:0;text-transform:none;color:#5a4a38;font-style:italic;}
  .sc-h .add{font-family:'Crimson Pro',serif;font-size:13px;letter-spacing:0;text-transform:none;color:#b8ad97;font-style:italic;cursor:text;}

  .event{margin:0 0 20px 14px;padding-left:14px;border-left:2px solid #e0d8c8;}
  .ev-t{font-size:18px;color:var(--pageink);margin-bottom:2px;}
  .ev-write{margin-top:6px;color:#b8ad97;font-style:italic;font-size:14px;cursor:text;padding:3px 0;}
  .ev-write:hover{color:var(--gold);}

  .writing-surface{display:none;}
  body.writing .sheet:not(.live){display:none;}
  body.writing .sheet > .page-head,
  body.writing .sheet > .ch-h,
  body.writing .sheet > .sc-h,
  body.writing .sheet > .event{display:none;}
  body.writing .sheet.live > .writing-surface{display:block;}
  .ws-scene{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.14em;text-transform:uppercase;
    color:var(--pagemute);margin-bottom:8px;display:flex;align-items:baseline;gap:8px;}
  .ws-scene b{color:var(--pageink);font-weight:500;}
  .ws-scene .add{font-family:'Crimson Pro',serif;font-size:13px;letter-spacing:0;text-transform:none;color:#b8ad97;font-style:italic;}
  .ws-event{font-size:20px;color:var(--pageink);margin-bottom:16px;}
  .ws-area{width:100%;min-height:760px;border:none;outline:none;resize:none;background:transparent;
    font-family:'Crimson Pro',serif;font-size:18px;line-height:1.5;color:var(--pageink);}
  .ws-area::placeholder{color:#c3b9a4;font-style:italic;}

  /* ===== THE WHEEL ===== */
  #wheel{position:absolute;top:0;bottom:0;left:0;width:300px;
    pointer-events:none;z-index:40;overflow:hidden;}
  #wheel .wrail{position:absolute;top:0;bottom:0;left:40px;width:1px;background:rgba(201,146,58,.28);}
  #wheel .wfade{position:absolute;left:37px;width:7px;height:64px;text-align:center;z-index:4;}
  #wheel .wfade.top{top:0;background:linear-gradient(var(--bg0),transparent);}
  #wheel .wfade.bot{bottom:0;background:linear-gradient(transparent,var(--bg0));}

  .wlabel{position:absolute;left:40px;height:0;pointer-events:auto;cursor:pointer;will-change:top,opacity;}
  .wlabel .wnode{position:absolute;left:0;top:0;width:7px;height:7px;border-radius:50%;
    background:var(--bg0);border:1px solid rgba(201,146,58,.45);transform:translate(-50%,-50%);transition:background .18s,border-color .18s,box-shadow .18s;}
  .wlabel .wtext{position:absolute;left:46px;top:0;width:200px;white-space:normal;
    font-family:'Crimson Pro',serif;font-size:18px;color:var(--ink);
    transform:translateY(-50%);letter-spacing:.01em;line-height:1.2;
    transition:color .35s ease,font-weight .35s ease,opacity .35s ease;}
  .wlabel .wkick{display:block;font-family:'JetBrains Mono',monospace;font-size:9px;font-weight:500;
    letter-spacing:.16em;text-transform:uppercase;color:var(--gold);margin-bottom:3px;opacity:.7;}
  .wlabel .wttl{display:block;}

  .wlabel.near .wnode{border-color:rgba(201,146,58,.7);}
  .wlabel:hover .wnode{background:var(--gold2);border-color:var(--gold2);box-shadow:0 0 5px rgba(232,176,96,.7);}
  .wlabel.live .wttl{color:var(--gold2);font-weight:600;}
  .wlabel.live .wnode{opacity:0;}

  #wheel .wcentre{position:absolute;left:40px;top:50%;height:0;z-index:2;pointer-events:none;}
  #wheel .wring{position:absolute;left:0;top:0;width:17px;height:17px;border-radius:50%;
    border:2px solid var(--gold2);transform:translate(-50%,-50%);box-shadow:0 0 8px rgba(232,176,96,.5);}
  #wheel .wring i{position:absolute;left:50%;top:50%;width:5px;height:5px;margin:-2.5px 0 0 -2.5px;
    border-radius:50%;background:var(--gold2);box-shadow:0 0 5px rgba(232,176,96,.75);}
  #wheel .wlead{position:absolute;left:9px;top:0;height:1px;width:32px;
    background:linear-gradient(90deg,var(--gold2),rgba(232,176,96,.15));transform:translateY(-50%);}

  /* ===== THE ENTITY POP-UP ===== */
  .popup{position:absolute;top:30px;left:24px;width:248px;
    background:var(--bg2);border:1px solid var(--rule2);border-radius:3px;
    box-shadow:0 14px 50px rgba(0,0,0,.55);}
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

        <!-- ===== STAVE ONE — Marley's Ghost ===== -->
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h" data-stave-open="1">Stave One — Marley's Ghost</div>
          <div class="sc-h" data-rail data-label="The Counting-House"><b>Scene 1</b><span class="ttl">— The Counting-House</span></div>
          <div class="event"><div class="ev-t">Scrooge works in the bitter cold, begrudging Bob Cratchit a single coal for the fire.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave One — Marley's Ghost</div>
          <div class="sc-h" data-rail data-label="Fred's Visit"><b>Scene 2</b><span class="ttl">— Fred's Visit</span></div>
          <div class="event"><div class="ev-t">Scrooge's nephew arrives to cheerfully invite him to Christmas dinner, which Scrooge gruffly rejects.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave One — Marley's Ghost</div>
          <div class="sc-h" data-rail data-label="The Charity Collectors"><b>Scene 3</b><span class="ttl">— The Charity Collectors</span></div>
          <div class="event"><div class="ev-t">Two gentlemen ask Scrooge to donate to the poor; he refuses, citing workhouses and prisons.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave One — Marley's Ghost</div>
          <div class="sc-h" data-rail data-label="Scrooge's Home"><b>Scene 4</b><span class="ttl">— Scrooge's Home</span></div>
          <div class="event"><div class="ev-t">Scrooge returns to his dark, isolated house. The door knocker transforms into the face of Jacob Marley.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave One — Marley's Ghost</div>
          <div class="sc-h" data-rail data-label="Marley's Warning"><b>Scene 5</b><span class="ttl">— Marley's Warning</span></div>
          <div class="event"><div class="ev-t">Marley's ghost, bound by chains of ledgers and cashboxes, warns Scrooge of his doom and the coming of three spirits.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>

        <!-- ===== STAVE TWO — The First of the Three Spirits ===== -->
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h" data-stave-open="1">Stave Two — The First of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="The Lonely School"><b>Scene 1</b><span class="ttl">— The Lonely School</span></div>
          <div class="event"><div class="ev-t">The Ghost of Christmas Past takes Scrooge to his boyhood boarding school, where he is left alone at the holidays.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Two — The First of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="A Joyful Return"><b>Scene 2</b><span class="ttl">— A Joyful Return</span></div>
          <div class="event"><div class="ev-t">Scrooge's sister, Fan, arrives to bring him home, revealing her loving nature.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Two — The First of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="Fezziwig's Party"><b>Scene 3</b><span class="ttl">— Fezziwig's Party</span></div>
          <div class="event"><div class="ev-t">Scrooge revisits his old, jovial employer, Mr. Fezziwig, who throws a lively Christmas party for his staff.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Two — The First of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="The Broken Engagement"><b>Scene 4</b><span class="ttl">— The Broken Engagement</span></div>
          <div class="event"><div class="ev-t">Scrooge's former fiancée, Belle, tearfully releases him, realising his greed has eclipsed his love for her.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Two — The First of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="Belle's Family Home"><b>Scene 5</b><span class="ttl">— Belle's Family Home</span></div>
          <div class="event"><div class="ev-t">Scrooge sees Belle years later, on the night Marley died, happily married and surrounded by a loving family.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>

        <!-- ===== STAVE THREE — The Second of the Three Spirits ===== -->
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h" data-stave-open="1">Stave Three — The Second of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="The Spirit's Lair"><b>Scene 1</b><span class="ttl">— The Spirit's Lair</span></div>
          <div class="event"><div class="ev-t">The Ghost of Christmas Present appears, surrounded by a feast of holiday abundance.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Three — The Second of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="The Cratchit Home"><b>Scene 2</b><span class="ttl">— The Cratchit Home</span></div>
          <div class="event"><div class="ev-t">Scrooge watches the poor but loving Cratchits eat a humble Christmas dinner, and learns of ailing Tiny Tim.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Three — The Second of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="People Across the World"><b>Scene 3</b><span class="ttl">— People Across the World</span></div>
          <div class="event"><div class="ev-t">The Spirit shows Scrooge miners and lighthouse keepers celebrating, proving the Christmas spirit reaches anyone.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Three — The Second of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="Fred's Christmas Party"><b>Scene 4</b><span class="ttl">— Fred's Christmas Party</span></div>
          <div class="event"><div class="ev-t">At Fred's house the family plays games and affectionately laughs at Scrooge's miserly ways.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Three — The Second of the Three Spirits</div>
          <div class="sc-h" data-rail data-label="Ignorance and Want"><b>Scene 5</b><span class="ttl">— Ignorance and Want</span></div>
          <div class="event"><div class="ev-t">Before vanishing, the Spirit reveals two emaciated children beneath its robes — the grim realities of society.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>

        <!-- ===== STAVE FOUR — The Last of the Spirits ===== -->
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h" data-stave-open="1">Stave Four — The Last of the Spirits</div>
          <div class="sc-h" data-rail data-label="The Businessmen"><b>Scene 1</b><span class="ttl">— The Businessmen</span></div>
          <div class="event"><div class="ev-t">The Ghost of Christmas Yet to Come silently shows Scrooge businessmen discussing the death of an unpopular man.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Four — The Last of the Spirits</div>
          <div class="sc-h" data-rail data-label="The Thieves"><b>Scene 2</b><span class="ttl">— The Thieves</span></div>
          <div class="event"><div class="ev-t">In a squalid shop, scavengers barter over clothing and belongings stripped from the dead man.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Four — The Last of the Spirits</div>
          <div class="sc-h" data-rail data-label="The Debtors"><b>Scene 3</b><span class="ttl">— The Debtors</span></div>
          <div class="event"><div class="ev-t">Scrooge sees a family relieved at the man's death, granting them extra time to pay their debts.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Four — The Last of the Spirits</div>
          <div class="sc-h" data-rail data-label="The Cratchit Home"><b>Scene 4</b><span class="ttl">— The Cratchit Home</span></div>
          <div class="event"><div class="ev-t">Scrooge observes the Cratchit family grieving deeply over the death of Tiny Tim.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Four — The Last of the Spirits</div>
          <div class="sc-h" data-rail data-label="The Graveyard"><b>Scene 5</b><span class="ttl">— The Graveyard</span></div>
          <div class="event"><div class="ev-t">The Spirit points to a neglected headstone bearing Scrooge's own name, and he promises he will change.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>

        <!-- ===== STAVE FIVE — The End of It ===== -->
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h" data-stave-open="1">Stave Five — The End of It</div>
          <div class="sc-h" data-rail data-label="A Changed Man"><b>Scene 1</b><span class="ttl">— A Changed Man</span></div>
          <div class="event"><div class="ev-t">Scrooge wakes in his own bed on Christmas morning, overjoyed and transformed.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Five — The End of It</div>
          <div class="sc-h" data-rail data-label="The Turkey"><b>Scene 2</b><span class="ttl">— The Turkey</span></div>
          <div class="event"><div class="ev-t">He buys the largest turkey in the shop and anonymously sends it to the Cratchit family.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Five — The End of It</div>
          <div class="sc-h" data-rail data-label="Reconciliation"><b>Scene 3</b><span class="ttl">— Reconciliation</span></div>
          <div class="event"><div class="ev-t">Scrooge wishes the street a Merry Christmas, donates to the charity men, and visits Fred to apologise.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Five — The End of It</div>
          <div class="sc-h" data-rail data-label="A Raise for Bob"><b>Scene 4</b><span class="ttl">— A Raise for Bob</span></div>
          <div class="event"><div class="ev-t">Next morning at work, Scrooge surprises Bob Cratchit with a large raise and vows to help his family.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>
        <div class="sheet">
          <div class="page-head">A Christmas Carol by Charles Dickens</div>
          <div class="ch-h">Stave Five — The End of It</div>
          <div class="sc-h" data-rail data-label="Epilogue"><b>Scene 5</b><span class="ttl">— Epilogue</span></div>
          <div class="event"><div class="ev-t">The narrator concludes: Scrooge keeps Christmas perfectly ever after, especially with Tiny Tim, who survives.</div><div class="ev-write" onclick="enterWriting(this)">— click to write this scene —</div></div>
          <div class="writing-surface"><div class="ws-scene"></div><div class="ws-event"></div><textarea class="ws-area" placeholder="Write the scene here…"></textarea></div>
        </div>

      </div>
    </div>

    <!-- entity pop-ups are created dynamically (multiple, independent) -->

    <!-- THE WHEEL -->
    <div id="wheel">
      <div class="wrail"></div>
      <div class="wfade top"></div>
      <div class="wfade bot"></div>
      <div class="wcentre" id="wcentre">
        <span class="wlead"></span>
        <span class="wring"><i></i></span>
      </div>
    </div>
  </main>

  <aside class="sidebar right"></aside>
</div>

<div class="tip" id="tip">click a counted nav section — the list opens on the left</div>

<script>
  const body=document.body;
  const content=document.getElementById('content');
  const scroller=document.getElementById('scroller');
  const stage=document.getElementById('stage');
  const wheel=document.getElementById('wheel');
  const wcentre=document.getElementById('wcentre');

  /* the shared reading line — how far below the header a page's top sits */
  const READ_PAD=28;

  let writingMode=false;
  let currentIndex=0;
  const drafts={};

  const popData={
    characters:{ label:'Characters', colour:'var(--char)', items:[
      {sub:'Ebenezer Scrooge', desc:'A cold, solitary miser; the counting-house its own master.',
       fields:[
        ['Role','Protagonist'],
        ['Description','A squeezing, wrenching, grasping, scraping, clutching, covetous old sinner; hard and sharp as flint, from which no steel had ever struck out generous fire; secret, and self-contained, and solitary as an oyster.'],
        ['Arc','From miser to merciful, walked there across one night by three spirits — Past, Present, and Yet to Come.'],
        ['Notes (private)','Watch the thaw — it must be earned scene by scene, never sudden.'],
       ]},
      {sub:'Jacob Marley', desc:'Scrooge\u2019s dead partner; returns in chains as the first warning.',
       fields:[['Role','The first warning'],['Description','Dead these seven years; appears bound in the chains he forged in life.']]},
      {sub:'Bob Cratchit', desc:'Scrooge\u2019s underpaid clerk; warm where his master is cold.',
       fields:[['Role','Scrooge\u2019s clerk'],['Description','Toils for fifteen shillings a week; father to a large, loving family.']]},
      {sub:'Fred', desc:'Scrooge\u2019s nephew; arrives full of Christmas cheer and refused.',
       fields:[['Role','Scrooge\u2019s nephew'],['Description','Ruddy, warm, and good-humoured; keeps Christmas in his heart despite his uncle.']]},
      {sub:'Tiny Tim', desc:'The Cratchits\u2019 youngest; frail, hopeful, the story\u2019s tender heart.',
       fields:[['Role','The Cratchits\u2019 youngest'],['Description','Bears a little crutch; frail of body but bright of spirit.']]},
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
    ]},
    chapters:{ label:'Chapters', colour:'var(--chap)', items:[
      {sub:'Stave One — Marley\u2019s Ghost', desc:'Marley dead; Scrooge warned by his old partner.',
       fields:[['Scenes','5'],['Characters','Scrooge, Marley, Fred, Bob Cratchit']]},
      {sub:'Stave Two — The First of the Three Spirits', desc:'Christmas Past walks Scrooge through his youth.',
       fields:[['Scenes','5'],['Characters','Scrooge, Ghost of Christmas Past, Fezziwig']]},
    ]},
  };

  /* ===== THE ENTITY POP-UPS — multiple, independent ===== */
  let popZ=70;   /* z-index counter so a clicked pop-up rises to the front */

  document.querySelectorAll('.item[data-pop]').forEach(it=>{
    it.addEventListener('click',()=>createPopup(it.getAttribute('data-pop')));
  });

  function createPopup(key){
    const d=popData[key]; if(!d) return;

    /* always start at the home position; cascade a little so a second
       pop-up is visible rather than stacked exactly on the first */
    const n=content.querySelectorAll('.popup').length;
    const off=Math.min(n,6)*22;

    const pop=document.createElement('div');
    pop.className='popup';
    pop.style.left=(24+off)+'px';
    pop.style.top =(30+off)+'px';
    pop.style.zIndex=Math.min(89,++popZ);
    pop.innerHTML=
      '<div class="pu-head">'+
        '<span class="pu-kicker"></span>'+
        '<span class="pu-x">\u2715</span>'+
      '</div>'+
      '<div class="pu-list"></div>';
    content.appendChild(pop);

    const kicker=pop.querySelector('.pu-kicker');
    const list=pop.querySelector('.pu-list');

    /* clicking anywhere on this pop-up raises it above the others */
    pop.addEventListener('mousedown',()=>{ pop.style.zIndex=Math.min(89,++popZ); });
    /* close removes just this pop-up */
    pop.querySelector('.pu-x').addEventListener('click',e=>{ e.stopPropagation(); pop.remove(); });

    function showList(){
      kicker.textContent=d.label+' \u00B7 '+d.items.length;
      kicker.style.color=d.colour;
      list.innerHTML='';
      d.items.forEach((item,i)=>{
        const e=document.createElement('div');
        e.className='pu-entry';
        e.innerHTML='<div class="pu-sub" style="color:'+d.colour+'">'+item.sub+'</div>'+
          '<div class="pu-desc">'+item.desc+'</div>'+
          '<div class="pu-end" style="border-color:'+d.colour+'"></div>';
        e.addEventListener('click',()=>showRecord(i));
        list.appendChild(e);
      });
    }
    function showRecord(i){
      const item=d.items[i];
      kicker.textContent=d.label; kicker.style.color=d.colour;
      let fields='';
      (item.fields||[]).forEach((f,fi)=>{
        if(fi>0) fields+='<div class="pu-fdiv" style="border-color:'+d.colour+'"></div>';
        fields+='<div class="pu-field"><div class="pu-field-head">'+
          '<span class="pu-field-label">'+f[0]+'</span>'+
          '<span class="pu-copy" data-copy="'+fi+'">copy</span></div>'+
          '<div class="pu-field-val">'+f[1]+'</div></div>';
      });
      list.innerHTML='<div class="pu-back">\u2039 back to list</div>'+
        '<div class="pu-record"><div class="pu-rec-name" style="color:'+d.colour+'">'+item.sub+'</div>'+
        '<div class="pu-rec-kind">'+d.label.replace(/ &amp;.*/,'').replace(/s$/,'')+'</div>'+fields+
        '<div class="pu-rec-end" style="border-color:'+d.colour+'"></div></div>';
      list.querySelector('.pu-back').addEventListener('click',showList);
      list.querySelectorAll('.pu-copy').forEach(btn=>{
        btn.addEventListener('click',e=>{
          e.stopPropagation();
          const text=item.fields[+btn.getAttribute('data-copy')][1];
          const plain=text.replace(/&amp;/g,'&').replace(/&quot;/g,'"');
          navigator.clipboard&&navigator.clipboard.writeText(plain);
          btn.textContent='copied'; btn.classList.add('done');
          setTimeout(()=>{btn.textContent='copy';btn.classList.remove('done');},1400);
        });
      });
    }

    /* drag by the header — moves only this pop-up */
    const head=pop.querySelector('.pu-head');
    let dragging=false, sx=0, sy=0, ox=0, oy=0;
    head.addEventListener('mousedown',e=>{
      if(e.target.classList.contains('pu-x')) return;
      dragging=true;
      const r=pop.getBoundingClientRect();
      const pr=pop.offsetParent.getBoundingClientRect();
      ox=r.left-pr.left; oy=r.top-pr.top; sx=e.clientX; sy=e.clientY;
      pop.style.left=ox+'px'; pop.style.top=oy+'px'; e.preventDefault();
    });
    window.addEventListener('mousemove',e=>{
      if(!dragging) return;
      pop.style.left=(ox+e.clientX-sx)+'px';
      pop.style.top=(oy+e.clientY-sy)+'px';
    });
    window.addEventListener('mouseup',()=>{ dragging=false; });

    showList();
  }

  /* ===== THE WHEEL ===== */
  /* one label per scene; each carries a stave/scene kicker + its title */
  const STAVE_WORD=['','One','Two','Three','Four','Five','Six','Seven','Eight','Nine','Ten'];
  const SCENE_WORD=['','One','Two','Three','Four','Five','Six','Seven','Eight','Nine','Ten'];
  const sheets=[...stage.querySelectorAll('.sheet')];
  let staveNo=0, sceneNo=0;
  const rows=[];
  sheets.forEach(sheet=>{
    const chh=sheet.querySelector('.ch-h');
    if(chh && chh.getAttribute('data-stave-open')==='1'){ staveNo++; sceneNo=0; }
    sceneNo++;
    const sc=sheet.querySelector('.sc-h[data-rail]');
    if(sc){
      const kick='Stave '+STAVE_WORD[staveNo]+' — Scene '+SCENE_WORD[sceneNo];
      rows.push({ kick, title:sc.getAttribute('data-label'), sheet, h:sc });
    }
  });

  rows.forEach((r,i)=>{
    const el=document.createElement('div');
    el.className='wlabel';
    el.innerHTML='<span class="wnode"></span><span class="wtext">'+
      '<span class="wkick">'+r.kick+'</span>'+
      '<span class="wttl">'+r.title+'</span></span>';
    el.addEventListener('click',()=>{
      if(writingMode){ openForWriting(i); }
      else if(el.classList.contains('live')){ openForWriting(i); }
      else { rollToTop(r.sheet, true); }
    });
    wheel.appendChild(el);
    r.el=el;
  });

  /* land a page's TOP on the shared reading line (just below the header) */
  function rollToTop(target, smooth){
    const rect=target.getBoundingClientRect();
    const cBox=content.getBoundingClientRect();
    const top=scroller.scrollTop+(rect.top-cBox.top)-READ_PAD;
    scroller.scrollTo({top,behavior:smooth?'smooth':'auto'});
  }

  function enterWriting(writeEl){
    const sheet=writeEl.closest('.sheet');
    const idx=rows.findIndex(r=>r.sheet===sheet);
    openForWriting(idx<0?0:idx);
  }

  function openForWriting(idx){
    if(writingMode) saveDraft(currentIndex);
    currentIndex=idx;
    const r=rows[idx];
    sheets.forEach(s=>s.classList.remove('live'));
    r.sheet.classList.add('live');
    const wsScene=r.sheet.querySelector('.ws-scene');
    const wsEvent=r.sheet.querySelector('.ws-event');
    const wsArea=r.sheet.querySelector('.ws-area');
    wsScene.innerHTML = r.h ? r.h.innerHTML : '';
    const firstEv=r.sheet.querySelector('.ev-t');
    wsEvent.textContent = firstEv ? firstEv.textContent : '';
    wsArea.value = drafts[idx]||'';
    body.classList.add('writing');
    writingMode=true;
    document.getElementById('modeNote').textContent='writing · use the wheel to move';
    paintWheel(idx);
    /* layout changes when .writing is applied (stage padding, hidden content);
       wait two frames for it to settle, then land the page top on the reading line */
    requestAnimationFrame(()=>requestAnimationFrame(()=>{ rollToTop(r.sheet, false); }));
    setTimeout(()=>wsArea.focus(),160);
  }

  function saveDraft(idx){
    const r=rows[idx]; if(!r) return;
    const ta=r.sheet.querySelector('.ws-area');
    if(ta) drafts[idx]=ta.value;
  }

  function exitWriting(){
    saveDraft(currentIndex);
    body.classList.remove('writing');
    writingMode=false;
    sheets.forEach(s=>s.classList.remove('live'));
    document.getElementById('modeNote').textContent='the wheel · centre = where you are';
    /* two frames for the overview padding to settle, then land on the scene we left */
    requestAnimationFrame(()=>requestAnimationFrame(()=>{ rollToTop(rows[currentIndex].sheet, false); turnFromScroll(); }));
  }
  window.exitWriting=exitWriting;

  /* belt geometry — ring stays fixed at the channel's vertical centre */
  const TIGHT=46, GAP=64, WINDOW=9, BOW=0;
  function placeBelt(cur){
    const cBox=content.getBoundingClientRect();
    const centreY=cBox.height/2;
    wcentre.style.top=centreY+'px';
    rows.forEach((r,i)=>{
      const steps=i-cur;
      const asteps=Math.abs(steps);
      let y,op;
      if(asteps<0.5){ y=centreY; }
      else if(steps<0){ y=centreY-GAP-(-steps-0.5)*TIGHT; }
      else { y=centreY+GAP+(steps-0.5)*TIGHT; }
      if(asteps<0.5){ op=1; }
      else {
        const t=Math.min(1,(asteps-0.5)/WINDOW);
        op=0.95*(1-t*t);
        op=Math.max(0.85,op);
        if(asteps>1.5) op=op*0.71;
      }
      if(asteps>WINDOW+0.7) op=0;
      const t2=Math.min(1,asteps/(WINDOW+0.5));
      const push=BOW*(1-t2*t2);
      r.el.style.top=y+'px';
      r.el.style.opacity=op;
      r.el.querySelector('.wtext').style.transform='translateY(-50%) translateX('+push+'px)';
      r.el.style.pointerEvents = op>0.05 ? 'auto':'none';
      const live=(Math.round(cur)===i);
      r.el.classList.toggle('live',live);
      r.el.classList.toggle('near',!live && asteps<1.6);
      r.el.classList.toggle('far', asteps>=1.6);
    });
  }
  function paintWheel(idx){ placeBelt(idx); }

  function positionWheel(){
    const cRect=content.getBoundingClientRect();
    const sRect=sheets[0].getBoundingClientRect();
    const gapLeft=sRect.right-cRect.left;
    const gapRight=cRect.width;
    const gapW=gapRight-gapLeft;
    const gapCentre=(gapLeft+gapRight)/2;
    const labelW=Math.max(120, gapW*0.5);
    document.querySelectorAll('.wlabel .wtext').forEach(t=>t.style.width=labelW+'px');
    const blockW=46+labelW;
    const blockLeft=gapCentre-blockW/2;
    wheel.style.left=(blockLeft-40)+'px';
  }

  /* "where you are" reads from the SAME line the page lands on:
     whichever scene's TOP has reached the reading line is at centre */
  let targetFrac=0, shownFrac=0, easing=false;
  function measureFrac(){
    const cBox=content.getBoundingClientRect();
    const line=cBox.top+READ_PAD;
    const tops=rows.map(r=>r.sheet.getBoundingClientRect().top);
    let frac=0;
    if(line<=tops[0]) frac=0;
    else if(line>=tops[tops.length-1]) frac=tops.length-1;
    else for(let i=0;i<tops.length-1;i++){
      if(line>=tops[i] && line<=tops[i+1]){
        const span=tops[i+1]-tops[i];
        frac=i+(span?(line-tops[i])/span:0);
        break;
      }
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

  window.addEventListener('load',()=>{ positionWheel(); turnFromScroll(); scroller.scrollTo({top:1}); requestAnimationFrame(turnFromScroll); });
  window.addEventListener('resize',()=>{ positionWheel(); writingMode?paintWheel(currentIndex):turnFromScroll(); });
  let ticking=false;
  scroller.addEventListener('scroll',()=>{
    if(!ticking){ requestAnimationFrame(()=>{ turnFromScroll(); ticking=false; }); ticking=true; }
  },{passive:true});
</script>
</body>
</html>