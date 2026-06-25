
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InkySwot — the hybrid card (still)</title>
<link href="https://fonts.googleapis.com/css2?family=Crimson+Pro:wght@300;400;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  /* values lifted straight from the DCW blueprint */
  :root{
    --bg:#0a0806; --bg2:#18120d; --ink:#e8e0d0; --ink2:#b0a090; --ink3:#706050;
    --gold:#c9923a; --gold2:#e8b060; --rule:#221709; --rule2:#352815;
    --char:#cf7f57;                       /* track colour — only the kicker + title use it for now */
    --danger:#c45b48;                     /* the Dark Thoughts dot */
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  body{background:var(--bg);color:var(--ink);font-family:'Crimson Pro',serif;
    min-height:100vh;display:flex;gap:60px;align-items:flex-start;justify-content:center;padding:70px 30px;}
  .col{display:flex;flex-direction:column;align-items:center;gap:18px;}
  .col > .cap{font-family:'Crimson Pro',serif;font-size:19px;color:var(--ink);}

  /* ===== THE HYBRID CARD ===== */
  .card{width:248px;background:var(--bg2);border:1px solid var(--rule2);border-radius:3px;
    box-shadow:0 14px 50px rgba(0,0,0,.55);overflow:hidden;}

  /* shared header bar — tinted to the track colour */
  .cardhead{display:flex;align-items:center;gap:8px;padding:11px 12px 10px;
    border-bottom:1px solid var(--rule);
    background:var(--char);}
  .ch-kicker{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.18em;
    text-transform:uppercase;color:rgba(20,14,8,.85);flex:1;font-weight:600;}
  .ch-tool{font-family:'JetBrains Mono',monospace;font-size:13px;color:rgba(20,14,8,.7);cursor:pointer;
    line-height:1;padding:2px 3px;background:none;border:none;position:relative;}
  .ch-tool:hover{color:rgba(20,14,8,1);}
  .ch-tool svg{width:15px;height:15px;display:block;}
  /* the flip control — turns the card to its Dark Thoughts side */
  .ch-flip{color:rgba(20,14,8,.7);}
  .ch-flip:hover{color:rgba(20,14,8,1);}
  /* a small red dot shows when Dark Thoughts has something written on the back */
  .ch-flip.has-dt::after{content:"";position:absolute;top:1px;right:0;width:4px;height:4px;
    border-radius:50%;background:var(--danger);box-shadow:0 0 3px rgba(196,91,72,.7);}

  /* contracted body — just the name + a fine rule */
  .ct-body{padding:14px 16px 16px;}
  .ct-name{font-family:'Crimson Pro',serif;font-weight:600;font-size:21px;line-height:1.2;color:var(--char);}
  .ct-rule{height:0;border-top:1px solid var(--char);opacity:.5;margin-top:11px;}

  /* expanded body */
  .ex-body{padding:6px 0 4px;max-height:430px;overflow-y:auto;
    scrollbar-width:thin;scrollbar-color:var(--rule2) transparent;}
  .ex-body::-webkit-scrollbar{width:9px;}
  .ex-body::-webkit-scrollbar-thumb{background:var(--rule2);border-radius:5px;border:2px solid var(--bg2);}
  .ex-back{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.08em;
    color:var(--ink3);cursor:pointer;padding:11px 16px 9px;}
  .ex-back:hover{color:var(--gold);}
  .ex-record{padding:0 16px 14px;}
  .ex-name{font-family:'Crimson Pro',serif;font-weight:600;font-size:21px;line-height:1.2;color:var(--char);margin-bottom:3px;}
  .ex-kind{font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.16em;text-transform:uppercase;color:var(--ink3);margin-bottom:14px;}
  .ex-field{margin-bottom:13px;}
  .ex-fhead{display:flex;align-items:baseline;gap:8px;margin-bottom:4px;}
  .ex-flabel{font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.14em;text-transform:uppercase;color:var(--ink3);flex:1;}
  .ex-copy{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.12em;text-transform:uppercase;color:var(--ink3);cursor:pointer;}
  .ex-copy:hover{color:var(--gold);}
  .ex-fval{font-family:'Crimson Pro',serif;font-weight:300;font-size:15px;line-height:1.5;color:var(--ink);}
  .ex-fdiv{height:0;border-top:1px solid var(--char);opacity:.4;margin:0 0 13px;}
  .ex-end{height:0;border-top:1px solid var(--char);opacity:.55;margin-top:4px;}

  .chev-up svg{transform:rotate(180deg);}
</style>
</head>
<body>

  <!-- EXPANDED -->
  <div class="col">
    <div class="cap">Expanded view</div>
    <div class="card">
      <div class="cardhead">
        <span class="ch-kicker">Characters</span>
        <button class="ch-tool ch-flip" title="Flip to Dark Thoughts"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 9-9"/><path d="M3 3v6h6"/></svg></button>
        <button class="ch-tool chev-up" title="Collapse"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"/></svg></button>
        <button class="ch-tool" title="Close">&#10005;</button>
      </div>
      <div class="ex-body">
        <div class="ex-back">&lsaquo; back to list</div>
        <div class="ex-record">
          <div class="ex-name">Ebenezer Scrooge</div>
          <div class="ex-kind">Character</div>

          <div class="ex-field">
            <div class="ex-fhead"><span class="ex-flabel">Role</span><span class="ex-copy">Copy</span></div>
            <div class="ex-fval">Protagonist</div>
          </div>
          <div class="ex-fdiv"></div>
          <div class="ex-field">
            <div class="ex-fhead"><span class="ex-flabel">Description</span><span class="ex-copy">Copy</span></div>
            <div class="ex-fval">A squeezing, wrenching, grasping, scraping, clutching, covetous old sinner; hard and sharp as flint, from which no steel had ever struck out generous fire; secret, and self-contained, and solitary as an oyster.</div>
          </div>
          <div class="ex-fdiv"></div>
          <div class="ex-field">
            <div class="ex-fhead"><span class="ex-flabel">Arc</span><span class="ex-copy">Copy</span></div>
            <div class="ex-fval">From miser to merciful, walked there across one night by three spirits — Past, Present, and Yet to Come.</div>
          </div>
          <div class="ex-end"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- CONTRACTED -->
  <div class="col">
    <div class="cap">Contracted view</div>
    <div class="card">
      <div class="cardhead">
        <span class="ch-kicker">Characters</span>
        <button class="ch-tool ch-flip has-dt" title="Flip to Dark Thoughts (has notes)"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 9-9"/><path d="M3 3v6h6"/></svg></button>
        <button class="ch-tool" title="Expand"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"/></svg></button>
        <button class="ch-tool" title="Close">&#10005;</button>
      </div>
      <div class="ct-body">
        <div class="ct-name">Ebenezer Scrooge</div>
        <div class="ct-rule"></div>
      </div>
    </div>
  </div>

</body>
</html>
