
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InkySwot — Plot Mapping · rotated</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&family=JetBrains+Mono:wght@300;400;500&family=Crimson+Pro:ital,wght@0,300;0,400;0,600;1,400&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0f0d0a; --panel:#18120d;
    --text:#e8e0d0; --text2:#b0a090; --muted:#706050;
    --gold:#c9923a; --gold-bright:#e8b060;
    --border:#221709; --border2:#352815; --rule-soft:#1c1915; --danger:#c45b48;
    --mono:'JetBrains Mono',monospace; --body:'Crimson Pro',Georgia,serif; --head:'Playfair Display',serif;

    --t-events:#c9923a; --t-locations:#5fa898; --t-characters:#cf7f57;
    --t-objects:#7a9bd0; --t-themes:#a07d9a; --t-tension:#c45b48;
    --t-custom:#9a8f72;

    --spine:96px;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  html,body{height:100%;}
  body{font-family:var(--body);background:var(--bg);color:var(--text);overflow:hidden;}
  #app{display:flex;flex-direction:column;height:100vh;}

  header{display:flex;align-items:center;justify-content:space-between;
    padding:12px 22px;background:var(--panel);border-bottom:1px solid var(--border2);}
  .brand{display:flex;align-items:baseline;gap:12px;}
  .wordmark{font-family:var(--head);font-weight:900;font-size:22px;color:var(--text);letter-spacing:.5px;}
  .screen-title{font-family:var(--body);font-style:italic;font-size:16px;color:var(--text2);}
  .screen-title::before{content:"·";margin-right:10px;color:var(--muted);}
  .axis{font-family:var(--mono);font-size:10px;letter-spacing:.18em;text-transform:uppercase;color:var(--muted);}
  .actions{display:flex;align-items:center;gap:14px;}
  .snap-btn{display:flex;align-items:center;gap:7px;height:30px;padding:0 13px;cursor:pointer;
    font-family:var(--mono);font-size:10px;letter-spacing:.1em;text-transform:uppercase;color:var(--text2);
    background:#120d08;border:1px solid var(--border2);border-radius:5px;}
  .snap-btn:hover{color:var(--gold-bright);border-color:var(--gold);background:#1d150d;}
  .snap-btn:active{background:#241a0e;}
  .snap-btn svg{width:14px;height:14px;display:block;}
  #zoom{display:flex;align-items:stretch;height:30px;background:#120d08;border:1px solid var(--border2);border-radius:5px;overflow:hidden;}
  #zoom button{width:30px;font-family:var(--mono);font-size:16px;color:var(--text2);display:flex;align-items:center;justify-content:center;background:transparent;border:none;cursor:pointer;}
  #zoom button:hover{color:var(--gold-bright);background:#1d150d;}
  #zoom .zlabel{width:52px;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:11px;
    color:var(--text2);border-left:1px solid var(--border2);border-right:1px solid var(--border2);}

  .stage{flex:1;display:flex;min-height:0;position:relative;}

  /* full-width chapter band across the whole stage (spine + board) */
  #chapBands{position:absolute;left:0;right:0;top:46px;bottom:0;overflow:hidden;pointer-events:none;z-index:4;}
  .sband{position:absolute;left:0;right:0;display:flex;align-items:center;gap:10px;height:48px;
    padding:0 18px 0 9px;background:#14100b;pointer-events:auto;
    border-top:1px solid rgba(201,146,58,.4);border-bottom:1px solid rgba(201,146,58,.4);}
  .sband .clabel{font-family:var(--mono);font-size:16px;letter-spacing:.1em;color:var(--gold);white-space:nowrap;font-weight:600;}
  .sband .del{flex:0 0 auto;}

  /* THE SPINE */
  .spine{width:var(--spine);flex:0 0 var(--spine);background:var(--bg);
    display:flex;flex-direction:column;position:relative;border-right:1px solid var(--border2);z-index:2;}
  .spine-head{padding:11px 8px;border-bottom:1px solid var(--border2);
    display:flex;align-items:center;justify-content:center;flex:0 0 auto;height:46px;}
  .spine-head .ttl{font-family:var(--mono);font-size:13px;letter-spacing:1.5px;text-transform:uppercase;color:var(--gold);white-space:nowrap;}
  .chapters{flex:1;overflow-y:auto;overflow-x:hidden;padding:6px;position:relative;
    scrollbar-width:thin;scrollbar-color:var(--border2) transparent;}
  .chapters::-webkit-scrollbar{width:11px;}
  .chapters::-webkit-scrollbar-track{background:transparent;}
  .chapters::-webkit-scrollbar-thumb{background:var(--border2);border-radius:6px;border:3px solid var(--panel);background-clip:padding-box;}
  .chapters::-webkit-scrollbar-thumb:hover{background:var(--gold);border-color:var(--panel);background-clip:padding-box;}

  .chapter{position:relative;display:flex;flex-direction:column;margin-bottom:2px;}
  .chapter-head{flex:0 0 auto;display:flex;align-items:center;gap:10px;padding:9px 8px 9px 9px;}
  .chapter-head .clabel{font-family:var(--mono);font-size:14px;letter-spacing:.1em;color:var(--gold);white-space:nowrap;font-weight:600;}
  .ch-title{flex:0 1 auto;min-width:150px;font-family:var(--body);font-size:25px;line-height:1.3;color:var(--text);outline:none;
    white-space:nowrap;overflow:hidden;text-overflow:ellipsis;border-bottom:1px solid transparent;padding:1px 4px;cursor:text;}
  .ch-title:hover{border-bottom-color:var(--border2);}
  .ch-title:focus{border-bottom-color:var(--gold);overflow:visible;}
  .ch-title:empty:before{content:"Name this chapter\2026";color:var(--muted);font-style:italic;}
  .ch-rule{flex:1;height:1px;min-width:8px;background:linear-gradient(90deg,rgba(201,146,58,.5),rgba(201,146,58,.12));}
  .ch-rule-lead{flex:0 0 60px;height:1px;background:transparent;}
  .chapter-head .add-scene{margin-left:auto;font-family:var(--mono);font-size:13px;line-height:1;
    color:var(--muted);cursor:pointer;padding:1px 4px;border-radius:3px;flex:0 0 auto;}
  .chapter-head .add-scene:hover{color:var(--gold);background:rgba(201,146,58,.1);}
  .del{font-family:var(--mono);font-size:13px;line-height:1;color:var(--muted);cursor:pointer;
    padding:1px 4px;border-radius:3px;flex:0 0 auto;opacity:0;transition:opacity .12s,color .12s,background .12s;}
  .chapter:hover .del,.scene:hover .del{opacity:.6;}
  .sband .del,.scene-band .del{flex:0 0 auto;order:-1;align-self:center;font-size:18px;line-height:1;padding:1px 8px 2px;
    opacity:1;background:var(--danger);color:#fff;border-radius:4px;}
  .sband .del:hover,.scene-band .del:hover{filter:brightness(1.15);}
  .del:hover{opacity:1 !important;color:#fff;background:var(--danger);}

  .ch-row .del{margin-left:auto;}
  .add-scene-row{margin-top:1px;padding:6px 7px;border:1px dashed var(--border2);border-radius:3px;
    display:flex;align-items:center;justify-content:center;gap:5px;
    font-family:var(--mono);font-size:13px;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);cursor:pointer;white-space:nowrap;}
  .add-scene-row:hover{color:var(--gold-bright);border-color:var(--gold);background:rgba(201,146,58,.05);}
  .scenes{flex:0 0 auto;display:flex;flex-direction:column;padding:5px 5px 0;gap:6px;}
  .scene{position:relative;display:flex;flex-direction:column;}

  /* scene title+text band, full width across the board (mirrors the chapter band) */
  .scene-band{position:absolute;left:0;right:0;display:flex;align-items:flex-start;gap:10px;
    padding:6px 18px 6px 9px;background:transparent;pointer-events:none;overflow:hidden;
    border-top:1px dashed rgba(138,129,112,.5);border-bottom:1px dashed rgba(138,129,112,.5);}
  .scene-band .sc-title,.scene-band .sc-text,.scene-band .del,.scene-band .grip{pointer-events:auto;}
  .scene-band .slabel{font-family:var(--mono);font-size:16px;letter-spacing:.1em;color:var(--gold);
    white-space:nowrap;font-weight:600;flex:0 0 auto;opacity:.9;padding-top:1px;}
  .scene-band .sb-lead{flex:0 0 60px;}
  .sb-stack{flex:1 1 auto;min-width:0;display:flex;flex-direction:column;gap:0;}
  .sc-title{font-family:var(--body);font-style:italic;font-size:25px;line-height:1.25;color:var(--text);outline:none;
    align-self:flex-start;max-width:100%;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;padding:0 2px;cursor:text;}
  .sc-title:focus{overflow:visible;}
  .sc-title:empty:before{content:"Name this scene\2026";color:var(--muted);}
  .sc-uline{align-self:stretch;height:1px;background:rgba(201,146,58,.32);pointer-events:none;margin:5px 2px 9px;}
  .sc-text{font-family:var(--body);font-style:italic;font-size:21px;line-height:1.35;color:var(--text2);outline:none;
    align-self:flex-start;max-width:100%;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;padding:0 2px;cursor:text;}
  .sc-text:focus{overflow:visible;color:var(--text);}
  .sc-text:empty:before{content:"This is where the text goes\2026";color:var(--muted);}
  .scene-band .del{flex:0 0 auto;}
  .ch-filler{flex:1 1 auto;min-height:6px;}
  .grip{position:absolute;left:0;right:0;bottom:0;height:8px;cursor:ns-resize;z-index:4;}
  .grip::after{content:"";position:absolute;left:50%;bottom:2px;transform:translateX(-50%);
    width:26px;height:2px;border-radius:2px;background:var(--border2);transition:background .12s;}
  .grip:hover::after{background:var(--gold);}
  body.depth-resizing{cursor:ns-resize;user-select:none;}

  .add-chapter{margin:2px 0 4px;padding:9px 8px;border:1px dashed var(--border2);border-radius:4px;
    display:flex;align-items:center;justify-content:center;gap:6px;
    font-family:var(--mono);font-size:13px;letter-spacing:.6px;color:var(--text2);cursor:pointer;white-space:nowrap;}
  .add-chapter:hover{color:var(--gold-bright);border-color:var(--gold);background:rgba(201,146,58,.06);}

  .spine-grip{position:absolute;top:0;right:-3px;width:7px;height:100%;cursor:ew-resize;z-index:5;border-right:1px solid var(--gold);}
  .spine-grip::after{content:"";position:absolute;top:50%;right:2px;transform:translateY(-50%);
    width:2px;height:34px;border-radius:2px;background:var(--border2);transition:background .12s;}
  .spine-grip:hover::after{background:var(--gold);}
  body.resizing{cursor:ew-resize;user-select:none;}

  /* THE BOARD — tracks running top to bottom */
  #board{flex:1;display:flex;flex-direction:column;min-width:0;background:var(--bg);position:relative;}
  .track-head{flex:0 0 auto;min-height:52px;display:flex;align-items:stretch;position:relative;
    border-bottom:1px solid var(--border2);background:linear-gradient(180deg,#13110d,#0c0a07);}
  .th{position:relative;flex:0 0 auto;display:flex;flex-direction:column;justify-content:center;gap:3px;
    padding:7px 12px 7px 24px;border-right:2px solid var(--border2);}
  .th-move{position:absolute;top:6px;left:5px;width:15px;height:18px;cursor:grab;color:var(--text2);
    opacity:.6;transition:opacity .12s,color .12s;display:flex;align-items:center;justify-content:center;z-index:7;}
  .th:hover .th-move{opacity:.95;color:var(--gold);}
  .th-move:hover{opacity:1;color:var(--gold);}
  .th-move:active{cursor:grabbing;}
  .th-move svg{width:14px;height:16px;display:block;}
  #dropline{position:absolute;top:0;width:2px;height:100%;background:var(--gold);box-shadow:0 0 7px var(--gold);z-index:20;pointer-events:none;}
  .th-ghost{position:fixed;z-index:9000;pointer-events:none;border:1px solid var(--gold);border-radius:6px;
    background:linear-gradient(180deg,#1b160f,#100d09);box-shadow:0 16px 36px rgba(0,0,0,.62);
    opacity:.97;transform:scale(1.03);transition:none;}
  .th.th-src{opacity:.26;}
  .confirm-pop{position:fixed;z-index:9500;background:var(--panel);border:1px solid var(--border2);border-radius:8px;
    padding:12px 14px;box-shadow:0 14px 34px rgba(0,0,0,.62);min-width:190px;}
  .confirm-pop .cp-msg{font-family:var(--body);font-size:16px;color:var(--text);margin-bottom:11px;}
  .confirm-pop .cp-row{display:flex;gap:8px;justify-content:flex-end;}
  .confirm-pop button{font-family:var(--mono);font-size:12px;letter-spacing:.05em;padding:6px 13px;border-radius:5px;
    cursor:pointer;border:1px solid var(--border2);background:transparent;color:var(--text2);}
  .confirm-pop .cp-no:hover{border-color:var(--muted);color:var(--text);}
  .confirm-pop .cp-yes{background:var(--danger);border-color:var(--danger);color:#fff;}
  .confirm-pop .cp-yes:hover{filter:brightness(1.12);}
  body.reordering{cursor:grabbing;user-select:none;}
  .th .tname{font-family:var(--mono);font-size:12px;letter-spacing:.1em;text-transform:uppercase;font-weight:500;
    outline:none;padding:1px 16px 1px 2px;border-radius:2px;border-bottom:1px solid transparent;
    white-space:normal;word-break:break-word;overflow-wrap:anywhere;line-height:1.25;min-height:14px;}
  .th .tname:hover{border-bottom-color:var(--border2);}
  .th .tname:focus{border-bottom-color:currentColor;}
  .th .tname:empty:before{content:attr(data-ph);color:var(--muted);}
  .th .trule{height:2px;width:22px;border-radius:2px;opacity:.85;}
  .th .del{position:absolute;top:4px;right:4px;margin:0;font-size:18px;line-height:1;padding:1px 8px 2px;
    opacity:1;background:var(--danger);color:#fff;border-radius:4px;}
  .th .del:hover{filter:brightness(1.15);}
  .th-grip{position:absolute;top:0;right:-4px;width:8px;height:100%;cursor:ew-resize;z-index:6;}
  .th-grip::after{content:"";position:absolute;top:50%;right:2px;transform:translateY(-50%);
    width:2px;height:22px;border-radius:2px;background:transparent;transition:background .12s;}
  .th-grip:hover::after{background:var(--gold);}
  .add-track{flex:0 0 auto;align-self:stretch;display:flex;align-items:center;gap:6px;padding:0 16px;
    font-family:var(--mono);font-size:13px;letter-spacing:.1em;text-transform:uppercase;color:var(--text2);
    cursor:pointer;white-space:nowrap;border-right:2px solid var(--border2);}
  .add-track:hover{color:var(--gold-bright);background:rgba(201,146,58,.06);}
  .head-fill{flex:1 1 auto;}

  .track-lanes{flex:1;display:flex;overflow:auto;position:relative;
    background-image:radial-gradient(circle, var(--border) 1px, transparent 1px);background-size:34px 34px;
    scrollbar-width:thin;scrollbar-color:var(--border2) transparent;}
  .track-lanes::-webkit-scrollbar{width:11px;height:11px;}
  .track-lanes::-webkit-scrollbar-track{background:transparent;}
  .track-lanes::-webkit-scrollbar-thumb{background:var(--border2);border-radius:6px;border:3px solid var(--bg);background-clip:padding-box;}
  .track-lanes::-webkit-scrollbar-thumb:hover{background:var(--gold);background-clip:padding-box;}
  .track-lanes::-webkit-scrollbar-corner{background:transparent;}
  .lane{flex:0 0 auto;border-right:2px solid var(--border2);}
  .lane-fill{flex:1 1 auto;min-width:40px;}

  /* horizontal grid lines projected from the spine's chapters & scenes */
  #gridLines{position:absolute;inset:0;pointer-events:none;z-index:1;overflow:hidden;}
  .gline{position:absolute;left:14px;width:calc(100% - 14px);height:0;}
  .gline.chap{border-top:1px solid rgba(201,146,58,.4);}
  .gline.scn{border-top:1px dashed rgba(138,129,112,.7);}
  .cband{position:absolute;left:0;right:0;display:flex;align-items:center;padding:0;}
  .cband-rule{flex:1;height:1px;background:linear-gradient(90deg,rgba(201,146,58,.55),rgba(201,146,58,0) 80%);}

  .board-empty{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:10px;
    color:var(--muted);pointer-events:none;z-index:1;}
  .board-empty .g{font-family:var(--head);font-size:38px;color:var(--border2);}
  .board-empty p{font-family:var(--mono);font-size:11px;letter-spacing:.5px;}

  /* floating layer for the loose cards */
  #cardLayer{position:absolute;top:0;left:0;pointer-events:none;z-index:3;}
  #cardLayer .card{pointer-events:auto;}

  .card-trigger{position:absolute;right:22px;bottom:20px;z-index:400;cursor:pointer;border:none;
    font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:#0a0806;
    background:linear-gradient(160deg,var(--gold-bright),var(--gold));padding:10px 15px;border-radius:22px;
    box-shadow:0 10px 26px rgba(0,0,0,.5);display:flex;align-items:center;gap:6px;}
  .card-trigger:hover{filter:brightness(1.06);}

  /* ===================== THE TRACK CARD (take 6 — header band, floating) ===================== */
  .card{position:absolute;width:230px;border:1px solid var(--border2);border-radius:4px;
    --c:var(--t-custom);--pin:var(--t-tension);transition:box-shadow .15s;
    box-shadow:0 10px 26px rgba(0,0,0,.5);}
  .card.pinned{box-shadow:0 0 0 1px rgba(201,146,58,.45),0 10px 26px rgba(0,0,0,.5);}
  .card.snapping{transition:left .22s cubic-bezier(.4,.1,.2,1), top .22s cubic-bezier(.4,.1,.2,1), box-shadow .15s;}
  .card-flip{perspective:1400px;}
  .card-inner{position:relative;transition:transform .5s cubic-bezier(.4,.15,.2,1);}
  .card-inner.d3{transform-style:preserve-3d;}
  .card.flipped .card-inner{transform:rotateY(180deg);}
  .face{backface-visibility:hidden;-webkit-backface-visibility:hidden;}

  .front{background:#14100b;border-radius:4px;overflow:hidden;}
  .c-band{display:flex;align-items:center;gap:6px;padding:5px 9px;background:var(--c);min-height:24px;cursor:grab;}
  .c-band:active{cursor:grabbing;}
  .card.pinned .c-band{cursor:default;}
  .c-type{font-family:var(--mono);font-size:10px;letter-spacing:.1em;text-transform:uppercase;font-weight:600;
    color:rgba(20,14,8,.85);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
  .c-band .pin{margin-left:auto;background:transparent;border:none;cursor:pointer;padding:1px;display:flex;line-height:1;flex:0 0 auto;}
  .c-band .pin svg{width:17px;height:17px;display:block;}
  .c-band .pin .outline{stroke:rgba(20,14,8,.7);fill:none;stroke-width:2;}
  .c-band .pin .fill{display:none;}
  .card.pinned .c-band .pin .outline{display:none;}
  .card.pinned .c-band .pin .fill{display:block;fill:var(--pin);stroke:rgba(20,14,8,.5);stroke-width:1;}

  .c-body{padding:8px 10px 10px;}
  .c-titlerow{display:flex;align-items:flex-start;gap:5px;}
  .c-title{flex:1;min-width:0;font-size:17px;line-height:1.2;color:var(--text);outline:none;
    word-break:break-word;border-bottom:1px solid transparent;padding-bottom:1px;}
  .c-title:hover{border-bottom-color:var(--rule-soft);}
  .c-title:focus{border-bottom-color:var(--c);}
  .c-title:empty:before{content:"Name\2026";color:var(--muted);font-style:italic;}
  .c-tool{flex:0 0 auto;width:20px;height:20px;border-radius:4px;display:flex;align-items:center;justify-content:center;
    color:var(--muted);cursor:pointer;opacity:.55;transition:all .12s;background:transparent;border:none;}
  .card:hover .c-tool{opacity:.8;}
  .c-tool:hover{opacity:1;color:var(--text);background:rgba(0,0,0,.3);}
  .c-tool svg{width:14px;height:14px;display:block;}

  .fields{display:none;flex-direction:column;gap:8px;margin-top:10px;padding-top:9px;border-top:1px solid var(--rule-soft);}
  .card.open .fields{display:flex;}
  .field{display:flex;flex-direction:column;gap:3px;}
  .field label{font-family:var(--mono);font-size:10px;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);}
  .field input,.field select,.field textarea{background:#0c0a07;border:1px solid var(--border2);color:var(--text);
    font-family:var(--body);font-size:16px;border-radius:3px;padding:7px 9px;outline:none;width:100%;}
  .field input:focus,.field select:focus,.field textarea:focus{border-color:var(--c);}
  .field textarea{resize:none;min-height:38px;line-height:1.3;overflow:hidden;}
  .field select{appearance:none;-webkit-appearance:none;cursor:pointer;padding-right:24px;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%23b0a090' stroke-width='3' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'/%3E%3C/svg%3E");
    background-repeat:no-repeat;background-position:right 8px center;}
  .field select option{background:var(--panel);color:var(--text);}

  .back{position:absolute;inset:0;transform:rotateY(180deg);background:#0c0a07;border:1px solid var(--border2);
    border-radius:4px;padding:8px 10px;display:flex;flex-direction:column;}
  .dt-head{font-family:var(--mono);font-size:10px;letter-spacing:.14em;text-transform:uppercase;color:var(--gold);margin-bottom:5px;}
  .dt-body{flex:1;width:100%;min-height:60px;background:transparent;border:none;outline:none;resize:none;
    font-family:var(--body);font-size:16px;line-height:1.3;color:var(--text2);overflow:auto;}
  .dt-body::placeholder{color:var(--muted);font-style:italic;}
  .dt-hint{font-family:var(--mono);font-size:7.5px;letter-spacing:.04em;color:var(--muted);margin-top:5px;opacity:.7;}

  .pin-pop{display:none;position:absolute;top:24px;right:6px;z-index:20;gap:7px;padding:7px 9px;border-radius:9px;
    background:var(--panel);border:1px solid var(--border2);box-shadow:0 10px 26px rgba(0,0,0,.55);}
  .pin-pop.open{display:flex;}
  .sw{width:14px;height:14px;border-radius:50%;border:2px solid transparent;cursor:pointer;padding:0;transition:transform .12s;}
  .sw:hover{transform:scale(1.18);}
  .sw.active{border-color:rgba(232,224,208,.6);}

  .track-pop{position:fixed;z-index:5000;background:var(--panel);border:1px solid var(--border2);border-radius:8px;
    padding:6px;display:flex;flex-direction:column;gap:2px;box-shadow:0 12px 32px rgba(0,0,0,.6);min-width:230px;
    max-height:78vh;overflow-y:auto;scrollbar-width:thin;scrollbar-color:var(--border2) transparent;}
  .track-pop .pop-group{font-family:var(--mono);font-size:9px;letter-spacing:1.4px;text-transform:uppercase;font-weight:600;padding:9px 6px 3px;}
  .track-pop .pop-head{font-family:var(--mono);font-size:9px;letter-spacing:1.2px;text-transform:uppercase;color:var(--muted);padding:4px 6px 6px;}
  .track-pop .pop-pill{display:flex;align-items:center;gap:9px;padding:6px 8px;border-radius:5px;background:transparent;
    font-family:var(--mono);font-size:12px;color:var(--text);text-align:left;border:none;cursor:pointer;width:100%;}
  .track-pop .pop-pill:hover{background:#120d08;}
  .track-pop .pop-dot{width:12px;height:12px;border-radius:3px;flex:none;}
  .track-pop .pop-div{height:1px;background:var(--border2);margin:4px 2px;}
  .track-pop .pop-pill.custom .pop-dot{border:1px dashed var(--muted);background:transparent;}
</style>
</head>
<body>
<div id="app">
  <header>
    <div class="brand">
      <span class="wordmark">InkySwot</span>
      <span class="screen-title">Plot Mapping</span>
    </div>
    <div class="actions">
      <button class="snap-btn" id="snapAll" title="Snap every card into its grid cell">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="1"/><path d="M3 9h18M3 15h18M9 3v18M15 3v18"/></svg>
        Snap to grid
      </button>
      <div id="zoom"><button id="zoomOut" title="Zoom out">&minus;</button><span class="zlabel" id="zlabel">100%</span><button id="zoomIn" title="Zoom in">+</button></div>
    </div>
  </header>

  <div class="stage">

    <div class="spine" id="spine">
      <div class="spine-head"><span class="ttl">Time</span></div>
      <div class="chapters" id="chapters"></div>
      <div class="spine-grip" id="grip" title="Drag to widen"></div>
    </div>

    <div id="board">
      <div class="track-head" id="trackHead"></div>
      <div class="track-lanes" id="trackLanes">
        <div id="gridLines"></div>
        <div id="cardLayer"></div>
      </div>
      <button class="card-trigger" id="cardTrigger">+ card</button>
    </div>

    <div id="chapBands"></div>

  </div>
</div>

<script>
  var TRACK_GROUPS = [
    { group:'People', col:'#cf7f57', items:[
      { name:'Characters',                col:'#cf7f57' },
      { name:'Relationships',             col:'#e09a72' },
      { name:'Factions & Organisations',  col:'#b86846' },
      { name:'Language & Dialogue',       col:'#d98c64' } ]},
    { group:'World', col:'#5fa898', items:[
      { name:'Locations',          col:'#5fa898' },
      { name:'Buildings',          col:'#4d8f82' },
      { name:'Objects & Artefacts',col:'#79bdab' },
      { name:'Rules & Lore',       col:'#3f7d72' } ]},
    { group:'Story', col:'#c9923a', items:[
      { name:'Plot & Story Threads',    col:'#c9923a' },
      { name:'Themes & Motifs',         col:'#ddae54' },
      { name:'Events & Timeline',       col:'#b27e2c' },
      { name:'Chapter & Scene Tracker', col:'#e6bd70' },
      { name:'Synopsis',                col:'#a06f24' },
      { name:'Dialogue',                col:'#cf9c44' } ]},
    { group:'Reference', col:'#9a8f72', items:[
      { name:'Research & Reference', col:'#9a8f72' },
      { name:'Notes & Scratchpad',   col:'#b3a98c' } ]}
  ];
  var TRACK_LIST = [];
  TRACK_GROUPS.forEach(function(g){ g.items.forEach(function(it){ TRACK_LIST.push(it); }); });

  var FIELDS = {
    'Characters':[ {k:'role',label:'Role',kind:'select',opts:['Protagonist','Antagonist','Supporting Character','Minor Character','Other']},
                   {k:'desc',label:'Description',kind:'textarea'} ],
    'Locations': [ {k:'ltype',label:'Type',kind:'select',opts:['City','Town','Building','Wilderness','Region','Other']},
                   {k:'desc',label:'Description',kind:'textarea'} ],
    'Events':    [ {k:'etype',label:'Type',kind:'select',opts:['Story Event','Turning Point','Revelation','Climax','Other']},
                   {k:'summary',label:'Summary',kind:'textarea'} ],
    'Objects':   [ {k:'cat',label:'Category',kind:'select',opts:['Weapon','Document','Vehicle','Jewellery','Artefact','Other']},
                   {k:'desc',label:'Description',kind:'textarea'} ],
    'Themes':    [ {k:'desc',label:'Description',kind:'textarea'} ],
    'Tension':   [ {k:'level',label:'Level',kind:'text'},
                   {k:'notes',label:'Notes',kind:'textarea'} ],
    '_default':  [ {k:'notes',label:'Notes',kind:'textarea'} ]
  };
  function fieldsFor(name){ return FIELDS[name] || FIELDS._default; }

  var TRACK_MIN = 96;
  var CARD_W = 230;
  var TRACKS = [];
  var CARDS  = [];
  var cardZ = 10;

  var lanes = document.getElementById('trackLanes');
  var cardLayer = document.getElementById('cardLayer');
  var gridLines = document.getElementById('gridLines');
  var chaptersEl = document.getElementById('chapters');

  function effW(ti){ return Math.max(TRACK_MIN, TRACKS[ti].width); }

  // ---- tracks ----
  function renderTracks(){
    var head = document.getElementById('trackHead');
    head.innerHTML = '';
    Array.prototype.slice.call(lanes.querySelectorAll('.lane,.lane-fill,.board-empty')).forEach(function(n){ n.remove(); });

    TRACKS.forEach(function(t, ti){
      var th = document.createElement('div');
      th.className = 'th'; th.dataset.ti = ti; th.style.width = effW(ti) + 'px';
      var name = document.createElement('div');
      name.className = 'tname'; name.contentEditable = 'true'; name.spellcheck = false;
      name.dataset.ph = 'Track'; name.textContent = t.name; name.style.color = t.col;
      name.oninput = function(){ t.name = name.textContent; };
      var rule = document.createElement('span'); rule.className = 'trule'; rule.style.background = t.col;
      var del = document.createElement('span');
      del.className = 'del'; del.title = 'Delete this track'; del.textContent = '\u00d7';
      del.onclick = function(e){ e.stopPropagation(); deleteTrack(ti); };
      var tgrip = document.createElement('div');
      tgrip.className = 'th-grip'; tgrip.title = 'Drag to set this track\u2019s width';
      tgrip.addEventListener('pointerdown', function(e){ startTrackWidth(e, ti); });
      var mv = document.createElement('div');
      mv.className = 'th-move'; mv.title = 'Drag to reorder this track';
      mv.innerHTML = '<svg viewBox="0 0 24 24" fill="currentColor"><circle cx="9" cy="6" r="1.7"/><circle cx="9" cy="12" r="1.7"/><circle cx="9" cy="18" r="1.7"/><circle cx="15" cy="6" r="1.7"/><circle cx="15" cy="12" r="1.7"/><circle cx="15" cy="18" r="1.7"/></svg>';
      mv.addEventListener('pointerdown', function(e){ startReorder(e, ti); });

      th.appendChild(mv); th.appendChild(name); th.appendChild(rule); th.appendChild(del); th.appendChild(tgrip);
      head.appendChild(th);

      var lane = document.createElement('div');
      lane.className = 'lane'; lane.dataset.ti = ti; lane.style.width = effW(ti) + 'px';
      lanes.insertBefore(lane, gridLines);
    });

    var add = document.createElement('div');
    add.className = 'add-track'; add.id = 'addTrack'; add.textContent = '+ track';
    add.onclick = function(e){ e.stopPropagation(); openTrackPicker(add); };
    head.appendChild(add);
    var hf = document.createElement('div'); hf.className = 'head-fill'; head.appendChild(hf);

    var lf = document.createElement('div'); lf.className = 'lane-fill'; lanes.insertBefore(lf, gridLines);

    if (TRACKS.length === 0 && CARDS.length === 0){
      var em = document.createElement('div');
      em.className = 'board-empty';
      em.innerHTML = '<div class="g">\u2225</div><p>+ TRACK &middot; + CARD</p>';
      lanes.insertBefore(em, gridLines);
    }
    renderGrid();
  }

  // ---- the across-board grid lines + vertical sync ----
  function renderGrid(){
    fitScenesToCards();                       // grow scenes to hold their card stacks
    var H = chaptersEl.scrollHeight;
    var W = 0;
    document.querySelectorAll('.lane').forEach(function(l){ W += l.offsetWidth; });
    var lf = lanes.querySelector('.lane-fill'); if (lf) W += lf.offsetWidth;
    if (W < lanes.clientWidth) W = lanes.clientWidth;

    cardLayer.style.width = W + 'px'; cardLayer.style.height = H + 'px';
    document.querySelectorAll('.lane').forEach(function(l){ l.style.minHeight = H + 'px'; });

    // keep the two heads the same height so the rows line up across
    var th = document.getElementById('trackHead');
    document.querySelector('.spine-head').style.height = th.offsetHeight + 'px';

    drawLines();
    placePinnedCards();
  }
  function drawLines(){
    gridLines.innerHTML = '';
    var r = lanes.getBoundingClientRect();
    var z = parseFloat(document.querySelector('.stage').style.zoom) || 1;
    chaptersEl.querySelectorAll('.scene').forEach(function(sc){ placeLine(sc.getBoundingClientRect().bottom, r.top, r.height, z, 'scn'); });
    repositionBands();
  }
  function repositionBands(){
    var wrap = document.getElementById('chapBands'); if (!wrap) return;
    var th = document.getElementById('trackHead');
    wrap.style.top = (th ? th.offsetHeight : 46) + 'px';
    var z = getZoom();
    var wrapTop = wrap.getBoundingClientRect().top;
    var chaps = chaptersEl.querySelectorAll('.chapter');
    Array.prototype.forEach.call(wrap.children, function(band){
      var ch = chaps[+band.dataset.ci]; if (!ch) return;
      if (band.dataset.kind === 'scene'){
        var sc = ch.querySelectorAll('.scene')[+band.dataset.si]; if (!sc) return;
        var r = sc.getBoundingClientRect();
        band.style.top = ((r.top - wrapTop) / z) + 'px';
        band.style.height = (r.height / z) + 'px';
      } else {
        band.style.top = ((ch.getBoundingClientRect().top - wrapTop) / z) + 'px';
      }
    });
  }
  function drawChapterBand(chapEl, laneTop, vh, z){
    var head = chapEl.querySelector('.chapter-head'); if (!head) return;
    var ctop = (chapEl.getBoundingClientRect().top - laneTop) / z;
    var hh = head.getBoundingClientRect().height / z;
    if (ctop > vh || (ctop + hh) < -2) return;          // off-board, skip
    var band = document.createElement('div'); band.className = 'cband';
    band.style.top = ctop + 'px'; band.style.height = hh + 'px';
    band.innerHTML = '<span class="cband-rule"></span>';
    gridLines.appendChild(band);
  }
  function placeLine(screenY, laneTop, vh, z, cls){
    var d = screenY - laneTop;                 // where this boundary sits on screen
    if (d < -2 || d > vh) return;               // off-board, skip
    var ln = document.createElement('div'); ln.className = 'gline ' + cls; ln.style.top = (d / z) + 'px';
    gridLines.appendChild(ln);
  }

  // vertical scroll runs the spine and the board together
  var syncing = false;
  chaptersEl.addEventListener('scroll', function(){ if (syncing) return; syncing = true; lanes.scrollTop = chaptersEl.scrollTop; syncing = false; drawLines(); });
  lanes.addEventListener('scroll', function(){ if (syncing) return; syncing = true; chaptersEl.scrollTop = lanes.scrollTop; syncing = false; drawLines(); });
  window.addEventListener('resize', renderGrid);

  // ---- floating cards ----
  function getZoom(){ return parseFloat(document.querySelector('.stage').style.zoom) || 1; }
  function lanesPt(clientX, clientY){
    var r = lanes.getBoundingClientRect(), z = getZoom();
    return { x: (clientX - r.left) / z + lanes.scrollLeft, y: (clientY - r.top) / z + lanes.scrollTop };
  }
  function newCard(type, x, y){
    return { type:type, x:x, y:y, z:++cardZ, title:'', fields:{}, dark:'',
             open:false, flipped:false, pinned:false, pinColor:'var(--t-tension)' };
  }
  function renderCards(){
    cardLayer.innerHTML = '';
    CARDS.forEach(function(card){ cardLayer.appendChild(buildCard(card)); });
  }

  // ---- snap to grid: a card's home is its track column (by type) and the scene row it sits over ----
  function colLefts(){ var a = [], acc = 0; for (var i=0;i<TRACKS.length;i++){ a.push(acc); acc += effW(i); } return a; }
  function sceneBands(){
    var lr = lanes.getBoundingClientRect(), z = getZoom(), out = [];
    chaptersEl.querySelectorAll('.scene').forEach(function(sc){
      var r = sc.getBoundingClientRect();
      out.push({ top: (r.top - lr.top) / z + lanes.scrollTop, bot: (r.bottom - lr.top) / z + lanes.scrollTop });
    });
    return out;
  }
  function assignHome(card){
    if (!TRACKS.length) return;
    var ti = -1;
    if (card.type.name){ for (var i=0;i<TRACKS.length;i++){ if (TRACKS[i].name === card.type.name){ ti = i; break; } } }
    if (ti < 0){ var lefts = colLefts(), cx = card.x + CARD_W/2, best = 0, bd = 1e9;
      for (var i=0;i<TRACKS.length;i++){ var c = lefts[i] + effW(i)/2, dd = Math.abs(c - cx); if (dd < bd){ bd = dd; best = i; } } ti = best; }
    card.homeTrack = TRACKS[ti].name;
    var bands = sceneBands(), si = -1;
    for (var i=0;i<bands.length;i++){ if (card.y >= bands[i].top && card.y < bands[i].bot){ si = i; break; } }
    if (si < 0 && bands.length){ var best = 0, bd = 1e9; for (var i=0;i<bands.length;i++){ var dd = Math.abs(bands[i].top - card.y); if (dd < bd){ bd = dd; best = i; } } si = best; }
    card.homeScene = si;
  }
  function ensureTrack(card){
    if (card.type.name){ if (!TRACKS.some(function(t){ return t.name === card.type.name; })){ TRACKS.push({ name:card.type.name, col:card.type.col, width:248 }); renderTracks(); } }
    else if (!TRACKS.length){ TRACKS.push({ name:'', col:card.type.col, width:248 }); renderTracks(); }
  }
  function snapCard(card){ ensureTrack(card); assignHome(card); repositionPinned(); }

  // ---- universal snap: pull every card onto the grid at once ----
  function snapAll(){
    var names = {}; CARDS.forEach(function(c){ if (c.type.name) names[c.type.name] = c.type.col; });
    var created = false;
    Object.keys(names).forEach(function(nm){ if (!TRACKS.some(function(t){ return t.name === nm; })){ TRACKS.push({ name:nm, col:names[nm], width:248 }); created = true; } });
    if (!TRACKS.length && CARDS.length){ TRACKS.push({ name:'', col:'var(--t-custom)', width:248 }); created = true; }
    if (created) renderTracks();
    CARDS.forEach(function(c){
      c.pinned = true;
      if (c._el){ c._el.classList.add('pinned','snapping'); var pb = c._el.querySelector('.pin'); if (pb) pb.title = 'Unpin'; }
      assignHome(c);
      if (c._el){ (function(el){ setTimeout(function(){ el.classList.remove('snapping'); }, 300); })(c._el); }
    });
    repositionPinned();
  }
  function positionFromHome(card){
    if (card.homeTrack == null) return;
    var lefts = colLefts(), ti = -1;
    for (var i=0;i<TRACKS.length;i++){ if (TRACKS[i].name === card.homeTrack){ ti = i; break; } }
    if (ti < 0) return;
    card.x = lefts[ti] + Math.max(0, (effW(ti) - CARD_W) / 2);
    if (card.homeScene != null && card.homeScene >= 0){
      var bands = sceneBands();
      if (card.homeScene < bands.length) card.y = bands[card.homeScene].top + 6;
    }
    if (card._el){ card._el.style.left = card.x + 'px'; card._el.style.top = card.y + 'px'; }
  }
  function trackIndexByName(name){ for (var i=0;i<TRACKS.length;i++){ if (TRACKS[i].name===name) return i; } return -1; }
  function cardsByCell(){
    var map = {};
    CARDS.forEach(function(c){
      if (!c.pinned || c.homeTrack == null) return;
      var ti = trackIndexByName(c.homeTrack); if (ti < 0) return;
      var si = (c.homeScene != null && c.homeScene >= 0) ? c.homeScene : -1;
      (map[si] = map[si] || {});
      (map[si][ti] = map[si][ti] || []).push(c);
    });
    return map;
  }
  function headerHeightFor(si){
    var sb = document.querySelectorAll('.scene-band')[si]; if (!sb) return 76;
    var stk = sb.querySelector('.sb-stack');
    return Math.max(64, 6 + (stk ? stk.offsetHeight : 60) + 12);   // never less than a clear title's height
  }
  // grow each scene so it contains the tallest stack of cards pinned in any of its tracks
  function fitScenesToCards(){
    if (!TRACKS.length) return;
    var map = cardsByCell();
    var sceneEls = chaptersEl.querySelectorAll('.scene');
    var flat = 0;
    spineData.forEach(function(ch){
      ch.scenes.forEach(function(sc){
        var el = sceneEls[flat];
        var needed = sc.depth;
        var cell = map[flat];
        if (cell){
          var hH = headerHeightFor(flat), tallest = 0;
          Object.keys(cell).forEach(function(ti){
            var list = cell[ti], sum = 0;
            list.forEach(function(c){ sum += (c._el ? c._el.offsetHeight : 130); });
            sum += 8 * Math.max(0, list.length - 1);
            if (sum > tallest) tallest = sum;
          });
          needed = Math.max(sc.depth, hH + tallest + 14);
        }
        if (el) el.style.minHeight = needed + 'px';
        flat++;
      });
    });
    var chapEls = chaptersEl.querySelectorAll('.chapter');
    spineData.forEach(function(ch, ci){ var ce = chapEls[ci]; if (ce) ce.style.height = chapterHeight(ch, ce) + 'px'; });
  }
  function placePinnedCards(){
    if (!TRACKS.length) return;
    var lefts = colLefts(), bands = sceneBands(), map = cardsByCell();
    Object.keys(map).forEach(function(sk){
      var si = +sk, hasScene = (si >= 0 && si < bands.length);
      var hH = hasScene ? headerHeightFor(si) : 0, top = hasScene ? bands[si].top : null;
      Object.keys(map[si]).forEach(function(tk){
        var ti = +tk, x = lefts[ti] + Math.max(0, (effW(ti) - CARD_W) / 2);
        if (hasScene){
          var y = top + hH + 12;
          map[si][ti].forEach(function(c){
            c.x = x; c.y = y;
            if (c._el){ c._el.style.left = x + 'px'; c._el.style.top = y + 'px'; }
            y += (c._el ? c._el.offsetHeight : 130) + 8;
          });
        } else {
          // no scene to pin to — stack the cards down their track column, below the chapter band
          var y = 56;
          map[si][ti].forEach(function(c){
            c.x = x; c.y = y;
            if (c._el){ c._el.style.left = x + 'px'; c._el.style.top = y + 'px'; }
            y += (c._el ? c._el.offsetHeight : 130) + 8;
          });
        }
      });
    });
  }
  function repositionPinned(){ renderGrid(); }

  function buildCard(card){
    var el = document.createElement('div');
    el.className = 'card' + (card.open?' open':'') + (card.flipped?' flipped':'') + (card.pinned?' pinned':'');
    el.style.left = card.x + 'px'; el.style.top = card.y + 'px'; el.style.zIndex = card.z;
    el.style.setProperty('--c', card.type.col);
    el.style.setProperty('--pin', card.pinColor);
    card._el = el;
    var typeLabel = (card.type.name || 'Note');

    var flip = document.createElement('div'); flip.className = 'card-flip';
    var inner = document.createElement('div'); inner.className = 'card-inner' + (card.flipped?' d3':'');

    var front = document.createElement('div'); front.className = 'face front';
    var band = document.createElement('div'); band.className = 'c-band';
    band.innerHTML =
      '<span class="c-type">' + typeLabel + '</span>' +
      '<button class="pin" title="Pin to a scene">' +
        '<svg class="outline" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"><path d="M12 17v5"/><path d="M9 10.76V4a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v6.76a2 2 0 0 0 .59 1.42l1.12 1.12A1 1 0 0 1 17 15H7a1 1 0 0 1-.71-1.7l1.12-1.12A2 2 0 0 0 9 10.76Z"/></svg>' +
        '<svg class="fill" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"><path d="M12 17v5"/><path d="M9 10.76V4a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v6.76a2 2 0 0 0 .59 1.42l1.12 1.12A1 1 0 0 1 17 15H7a1 1 0 0 1-.71-1.7l1.12-1.12A2 2 0 0 0 9 10.76Z"/></svg>' +
      '</button>';
    front.appendChild(band);

    var body = document.createElement('div'); body.className = 'c-body';
    var titlerow = document.createElement('div'); titlerow.className = 'c-titlerow';
    var title = document.createElement('div');
    title.className = 'c-title'; title.contentEditable = 'true'; title.spellcheck = false;
    title.textContent = card.title;
    title.oninput = function(){ card.title = title.textContent; };
    var flipBtn = document.createElement('button'); flipBtn.className = 'c-tool'; flipBtn.title = 'Dark Thoughts';
    flipBtn.innerHTML = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 9-9"/><path d="M3 3v6h6"/></svg>';
    var detBtn = document.createElement('button'); detBtn.className = 'c-tool'; detBtn.title = 'Show details';
    detBtn.innerHTML = chevSvg(card.open);
    var delBtn = document.createElement('button'); delBtn.className = 'c-tool'; delBtn.title = 'Delete this card';
    delBtn.innerHTML = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="5" y1="5" x2="19" y2="19"/><line x1="19" y1="5" x2="5" y2="19"/></svg>';
    titlerow.appendChild(title); titlerow.appendChild(flipBtn); titlerow.appendChild(detBtn); titlerow.appendChild(delBtn);
    body.appendChild(titlerow);

    var fieldsWrap = document.createElement('div'); fieldsWrap.className = 'fields';
    fieldsFor(card.type.name).forEach(function(f){
      var fl = document.createElement('div'); fl.className = 'field';
      var lab = document.createElement('label'); lab.textContent = f.label; fl.appendChild(lab);
      var ctl;
      if (f.kind === 'select'){
        ctl = document.createElement('select');
        f.opts.forEach(function(o){ var op = document.createElement('option'); op.textContent = o; ctl.appendChild(op); });
        ctl.value = card.fields[f.k] || f.opts[0];
        ctl.onchange = function(){ card.fields[f.k] = ctl.value; };
      } else if (f.kind === 'textarea'){
        ctl = document.createElement('textarea'); ctl.rows = 1; ctl.value = card.fields[f.k] || '';
        var grow = function(){ ctl.style.height='auto'; ctl.style.height = ctl.scrollHeight + 'px'; };
        ctl.oninput = function(){ card.fields[f.k] = ctl.value; grow(); repositionPinned(); };
        requestAnimationFrame(grow);
      } else {
        ctl = document.createElement('input'); ctl.type = 'text'; ctl.value = card.fields[f.k] || '';
        ctl.oninput = function(){ card.fields[f.k] = ctl.value; };
      }
      fl.appendChild(ctl); fieldsWrap.appendChild(fl);
    });
    body.appendChild(fieldsWrap);
    front.appendChild(body);

    var back = document.createElement('div'); back.className = 'face back';
    back.innerHTML = '<div class="dt-head">Dark Thoughts</div>';
    var dta = document.createElement('textarea'); dta.className = 'dt-body'; dta.value = card.dark || '';
    dta.placeholder = 'Your eyes only\u2026'; dta.spellcheck = false;
    dta.oninput = function(){ card.dark = dta.value; };
    var dh = document.createElement('div'); dh.className = 'dt-hint'; dh.textContent = 'private \u00b7 never exported \u00b7 flip to turn back';
    back.appendChild(dta); back.appendChild(dh);

    inner.appendChild(front); inner.appendChild(back);
    flip.appendChild(inner); el.appendChild(flip);

    var pop = document.createElement('div'); pop.className = 'pin-pop';
    ['var(--t-events)','var(--t-locations)','var(--t-characters)','var(--t-objects)','var(--t-themes)','var(--t-tension)'].forEach(function(c){
      var sw = document.createElement('button'); sw.className = 'sw' + (card.pinColor===c?' active':'');
      sw.style.background = c; sw.dataset.c = c;
      sw.onclick = function(e){ e.stopPropagation();
        card.pinColor = c; el.style.setProperty('--pin', c);
        pop.querySelectorAll('.sw').forEach(function(s){ s.classList.remove('active'); });
        sw.classList.add('active'); closePop();
      };
      pop.appendChild(sw);
    });
    el.appendChild(pop);

    function raise(){ card.z = ++cardZ; el.style.zIndex = card.z; }
    el.addEventListener('pointerdown', raise);

    detBtn.onclick = function(e){ e.stopPropagation();
      card.open = !card.open; el.classList.toggle('open', card.open);
      detBtn.innerHTML = chevSvg(card.open); detBtn.title = card.open ? 'Hide details' : 'Show details';
      repositionPinned();
    };
    flipBtn.onclick = function(e){ e.stopPropagation();
      var willFlip = !el.classList.contains('flipped'); card.flipped = willFlip;
      if (willFlip){ inner.classList.add('d3'); requestAnimationFrame(function(){ el.classList.add('flipped'); }); }
      else { el.classList.remove('flipped');
        var onEnd = function(){ inner.classList.remove('d3'); inner.removeEventListener('transitionend', onEnd); };
        inner.addEventListener('transitionend', onEnd); }
    };
    delBtn.onclick = function(e){ e.stopPropagation(); var i = CARDS.indexOf(card); if (i>=0) CARDS.splice(i,1); renderCards(); repositionPinned(); };

    var pinBtn = band.querySelector('.pin');
    function openPop(){ pop.classList.add('open'); setTimeout(function(){ document.addEventListener('pointerdown', outside); },0); }
    function closePop(){ pop.classList.remove('open'); document.removeEventListener('pointerdown', outside); }
    function outside(e){ if (!pop.contains(e.target) && e.target !== pinBtn && !pinBtn.contains(e.target)) closePop(); }
    pinBtn.onclick = function(e){ e.stopPropagation();
      card.pinned = !card.pinned; el.classList.toggle('pinned', card.pinned);
      pinBtn.title = card.pinned ? 'Unpin' : 'Pin to a scene';
      if (card.pinned){
        el.classList.add('snapping');
        snapCard(card);
        setTimeout(function(){ el.classList.remove('snapping'); }, 240);
        openPop();
      } else { closePop(); repositionPinned(); }
    };

    // drag the card by its band — only when NOT pinned
    band.addEventListener('pointerdown', function(e){
      if (e.target.closest('.pin')) return;
      if (card.pinned) return;              // pinned cards stay put until unpinned
      e.preventDefault();
      raise();
      var p = lanesPt(e.clientX, e.clientY);
      cardDrag = { card:card, el:el, offX:p.x - card.x, offY:p.y - card.y };
      document.body.style.userSelect = 'none';
    });

    return el;
  }

  var cardDrag = null;
  window.addEventListener('pointermove', function(e){
    if (!cardDrag) return;
    var p = lanesPt(e.clientX, e.clientY);
    cardDrag.card.x = Math.max(0, p.x - cardDrag.offX);
    cardDrag.card.y = Math.max(0, p.y - cardDrag.offY);
    cardDrag.el.style.left = cardDrag.card.x + 'px';
    cardDrag.el.style.top  = cardDrag.card.y + 'px';
  });
  window.addEventListener('pointerup', function(){
    if (cardDrag){ cardDrag = null; document.body.style.userSelect = ''; }
  });

  function chevSvg(open){
    return open
      ? '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"><polyline points="18 15 12 9 6 15"/></svg>'
      : '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"/></svg>';
  }

  // ---- + card ----
  document.getElementById('cardTrigger').onclick = function(e){
    e.stopPropagation();
    openTypePicker(this, function(type){
      var n = CARDS.length;
      var x = 470 + (n % 5) * 30, y = 86 + (n % 5) * 30;
      CARDS.push(newCard(type, x, y));
      if (document.querySelector('.board-empty')) renderTracks();
      renderCards();
    });
  };
  function pickerHTML(headLabel, customLabel){
    var html = '<div class="pop-head">' + headLabel + '</div>', idx = 0;
    TRACK_GROUPS.forEach(function(g){
      html += '<div class="pop-group" style="color:' + g.col + '">' + g.group + '</div>';
      g.items.forEach(function(it){
        html += '<button class="pop-pill" data-i="' + idx + '"><span class="pop-dot" style="background:' + it.col + '"></span>' + it.name + '</button>';
        idx++;
      });
    });
    html += '<div class="pop-div"></div><button class="pop-pill custom" data-custom="1"><span class="pop-dot"></span>' + customLabel + '</button>';
    return html;
  }
  function openTypePicker(anchor, cb){
    closeTrackPicker();
    var pop = document.createElement('div'); pop.className = 'track-pop'; pop.id = 'trackPop';
    pop.innerHTML = pickerHTML('What is this card?', 'Custom\u2026');
    document.body.appendChild(pop);
    pop.querySelectorAll('.pop-pill').forEach(function(b){
      b.onclick = function(ev){ ev.stopPropagation();
        var type = b.dataset.custom ? { name:'', col:'var(--t-custom)' } : { name:TRACK_LIST[+b.dataset.i].name, col:TRACK_LIST[+b.dataset.i].col };
        closeTrackPicker(); cb(type);
      };
    });
    var r = anchor.getBoundingClientRect(), w = pop.offsetWidth, h = pop.offsetHeight;
    pop.style.left = Math.max(8, Math.min(r.left, window.innerWidth - w - 8)) + 'px';
    pop.style.top = Math.max(8, Math.min(r.top - h - 8, window.innerHeight - h - 8)) + 'px';
  }

  // ---- track picker ----
  function closeTrackPicker(){ var p = document.getElementById('trackPop'); if (p) p.remove(); }
  function openTrackPicker(anchor){
    closeTrackPicker();
    var pop = document.createElement('div'); pop.className = 'track-pop'; pop.id = 'trackPop';
    pop.innerHTML = pickerHTML('Add a track', 'Custom track\u2026');
    document.body.appendChild(pop);
    pop.querySelectorAll('.pop-pill').forEach(function(b){
      b.onclick = function(e){ e.stopPropagation();
        if (b.dataset.custom) TRACKS.push({ name:'', col:'var(--t-custom)', width:248 });
        else { var t = TRACK_LIST[+b.dataset.i]; TRACKS.push({ name:t.name, col:t.col, width:248 }); }
        closeTrackPicker(); renderTracks();
      };
    });
    var r = anchor.getBoundingClientRect(), w = pop.offsetWidth, h = pop.offsetHeight;
    pop.style.left = Math.max(8, Math.min(r.left, window.innerWidth - w - 8)) + 'px';
    pop.style.top = Math.min(r.bottom + 6, window.innerHeight - h - 8) + 'px';
  }
  document.addEventListener('pointerdown', function(e){
    if (!e.target.closest('#trackPop') && !e.target.closest('#addTrack') && !e.target.closest('#cardTrigger')) closeTrackPicker();
  }, true);

  function applyTrackWidths(){
    document.querySelectorAll('.th').forEach(function(th){ th.style.width = effW(+th.dataset.ti) + 'px'; });
    document.querySelectorAll('.lane').forEach(function(lane){ lane.style.width = effW(+lane.dataset.ti) + 'px'; });
    renderGrid();
  }
  var tw = null;
  function startTrackWidth(e, ti){ e.preventDefault(); e.stopPropagation();
    tw = { ti:ti, startX:e.clientX, startW:TRACKS[ti].width }; document.body.classList.add('resizing'); }
  window.addEventListener('pointermove', function(e){
    if (!tw) return;
    TRACKS[tw.ti].width = Math.max(TRACK_MIN, tw.startW + (e.clientX - tw.startX));
    applyTrackWidths();
  });
  window.addEventListener('pointerup', function(){ if (!tw) return; tw = null; document.body.classList.remove('resizing'); });

  function confirmPop(anchor, label, onYes){
    var existing = document.getElementById('confirmPop'); if (existing) existing.remove();
    var pop = document.createElement('div'); pop.className = 'confirm-pop'; pop.id = 'confirmPop';
    pop.innerHTML = '<div class="cp-msg">' + label + '</div><div class="cp-row"><button class="cp-no">Cancel</button><button class="cp-yes">Delete</button></div>';
    document.body.appendChild(pop);
    var r = anchor.getBoundingClientRect();
    pop.style.left = Math.max(8, Math.min(r.left, window.innerWidth - pop.offsetWidth - 8)) + 'px';
    pop.style.top = Math.min(r.bottom + 6, window.innerHeight - pop.offsetHeight - 8) + 'px';
    pop.querySelector('.cp-yes').onclick = function(e){ e.stopPropagation(); pop.remove(); onYes(); };
    pop.querySelector('.cp-no').onclick = function(e){ e.stopPropagation(); pop.remove(); };
    setTimeout(function(){
      document.addEventListener('pointerdown', function h(ev){ if (!pop.contains(ev.target)){ pop.remove(); document.removeEventListener('pointerdown', h); } });
    }, 0);
  }
  function freeCard(c){
    c.pinned = false; c.homeTrack = null; c.homeScene = null;
    if (c._el){ c._el.classList.remove('pinned'); var pb = c._el.querySelector('.pin'); if (pb) pb.title = 'Pin to a scene'; }
  }
  function chapterFlatBase(ci){ var base = 0; for (var k=0;k<ci;k++) base += spineData[k].scenes.length; return base; }
  function deleteChapter(ci){
    var base = chapterFlatBase(ci), count = spineData[ci].scenes.length;
    spineData.splice(ci, 1);
    CARDS.forEach(function(c){
      if (!c.pinned || c.homeScene == null || c.homeScene < 0) return;
      if (c.homeScene >= base && c.homeScene < base + count) freeCard(c);      // card was in this chapter
      else if (c.homeScene >= base + count) c.homeScene -= count;              // card sat later — shift up
    });
    renderSpine();
  }
  function deleteScene(ci, si){
    var flat = chapterFlatBase(ci) + si;
    spineData[ci].scenes.splice(si, 1);
    CARDS.forEach(function(c){
      if (!c.pinned || c.homeScene == null || c.homeScene < 0) return;
      if (c.homeScene === flat) freeCard(c);                                   // card was in this scene
      else if (c.homeScene > flat) c.homeScene -= 1;                           // card sat later — shift up
    });
    renderSpine();
  }
  function deleteTrack(ti){
    var name = TRACKS[ti] ? TRACKS[ti].name : null;
    TRACKS.splice(ti, 1);
    CARDS.forEach(function(c){
      if (c.pinned && c.homeTrack === name){
        c.pinned = false; c.homeTrack = null; c.homeScene = null;
        if (c._el){ c._el.classList.remove('pinned'); var pb = c._el.querySelector('.pin'); if (pb) pb.title = 'Pin to a scene'; }
      }
    });
    renderTracks();
  }

  // ---- reorder tracks: drag a column left/right ----
  var reorder = null;
  function startReorder(e, ti){
    e.preventDefault(); e.stopPropagation();
    var head = document.getElementById('trackHead');
    var src = head.querySelectorAll('.th')[ti];
    var r = src.getBoundingClientRect();
    reorder = { from: ti, target: ti, grabDX: e.clientX - r.left, top: r.top };
    document.body.classList.add('reordering');
    // a lifted clone that follows the cursor
    var ghost = src.cloneNode(true); ghost.id = 'dragGhost'; ghost.classList.add('th-ghost');
    ghost.style.width = r.width + 'px'; ghost.style.height = r.height + 'px';
    ghost.style.left = r.left + 'px'; ghost.style.top = (r.top - 4) + 'px';
    document.body.appendChild(ghost);
    src.classList.add('th-src');
    var dl = document.createElement('div'); dl.id = 'dropline'; head.appendChild(dl);
  }
  window.addEventListener('pointermove', function(e){
    if (!reorder) return;
    var head = document.getElementById('trackHead');
    var ths = [].slice.call(head.querySelectorAll('.th'));
    var hr = head.getBoundingClientRect();
    var target = ths.length, x;
    for (var i=0;i<ths.length;i++){ var r = ths[i].getBoundingClientRect(); if (e.clientX < r.left + r.width/2){ target = i; break; } }
    reorder.target = target;
    if (target < ths.length) x = ths[target].getBoundingClientRect().left - hr.left;
    else x = ths.length ? (ths[ths.length-1].getBoundingClientRect().right - hr.left) : 0;
    var dl = document.getElementById('dropline'); if (dl) dl.style.left = x + 'px';
    var g = document.getElementById('dragGhost'); if (g) g.style.left = (e.clientX - reorder.grabDX) + 'px';
  });
  window.addEventListener('pointerup', function(){
    if (!reorder) return;
    var from = reorder.from, target = reorder.target;
    var item = TRACKS.splice(from, 1)[0];
    var insert = target; if (from < target) insert--;
    TRACKS.splice(insert, 0, item);
    reorder = null; document.body.classList.remove('reordering');
    var dl = document.getElementById('dropline'); if (dl) dl.remove();
    var g = document.getElementById('dragGhost'); if (g) g.remove();
    renderTracks();
  });

  renderTracks();
  renderCards();

  // ---- the spine ----
  var SC_MIN = 118, HEAD_H = 30, PAD = 8, CH_FLOOR_MIN = 44, BAND_H = 48;
  var spineData = [];
  function chapMin(chapEl){ return chapEl.querySelector('.chapter-head').offsetHeight + chapEl.querySelector('.scenes').offsetHeight + PAD; }
  function chapterHeight(ch, chapEl){ return Math.max(ch.floor, chapMin(chapEl)); }

  function renderSpine(){
    var box = document.getElementById('chapters'); box.innerHTML = '';
    var bandsBox = document.getElementById('chapBands'); bandsBox.innerHTML = '';
    spineData.forEach(function(ch, ci){
      var chap = document.createElement('div'); chap.className = 'chapter';
      var head = document.createElement('div'); head.className = 'chapter-head';
      head.style.height = BAND_H + 'px';
      chap.appendChild(head);

      var band = document.createElement('div'); band.className = 'sband';
      band.dataset.kind = 'chap'; band.dataset.ci = ci;
      band.innerHTML =
        '<span class="clabel">Ch.' + (ci+1) + '</span>' +
        '<span class="ch-rule-lead"></span>' +
        '<span class="ch-title" contenteditable="true" spellcheck="false"></span>' +
        '<span class="ch-rule"></span>' +
        '<span class="del" title="Delete this chapter">\u00d7</span>';
      var titleEl = band.querySelector('.ch-title');
      titleEl.textContent = ch.title || '';
      titleEl.oninput = function(){ ch.title = titleEl.textContent; };
      titleEl.addEventListener('keydown', function(e){ if (e.key === 'Enter'){ e.preventDefault(); titleEl.blur(); } });
      band.querySelector('.del').onclick = function(e){ e.stopPropagation(); confirmPop(this, 'Delete this chapter and its scenes?', function(){ deleteChapter(ci); }); };
      bandsBox.appendChild(band);
      var scenes = document.createElement('div'); scenes.className = 'scenes';
      ch.scenes.forEach(function(sc, si){
        var row = document.createElement('div'); row.className = 'scene'; row.style.minHeight = sc.depth + 'px';
        scenes.appendChild(row);

        var sb = document.createElement('div'); sb.className = 'scene-band';
        sb.dataset.kind = 'scene'; sb.dataset.ci = ci; sb.dataset.si = si;
        sb.innerHTML =
          '<span class="slabel">Sc.' + (si+1) + '</span>' +
          '<span class="sb-lead"></span>' +
          '<div class="sb-stack">' +
            '<span class="sc-title" contenteditable="true" spellcheck="false"></span>' +
            '<span class="sc-uline"></span>' +
          '</div>' +
          '<span class="del" title="Delete this scene">\u00d7</span>' +
          '<span class="grip" title="Drag to deepen this scene"></span>';
        var st = sb.querySelector('.sc-title'); st.textContent = sc.title || '';
        st.oninput = function(){ sc.title = st.textContent; };
        sb.querySelector('.del').onclick = function(e){ e.stopPropagation(); confirmPop(this, 'Delete this scene?', function(){ deleteScene(ci, si); }); };
        sb.querySelector('.grip').addEventListener('pointerdown', function(e){ startSceneDepth(e, row, chap, ch, sc); });
        bandsBox.appendChild(sb);
      });
      var asRow = document.createElement('div'); asRow.className = 'add-scene-row'; asRow.textContent = '+ scene';
      asRow.onclick = function(e){ e.stopPropagation(); ch.scenes.push({ depth: SC_MIN, title: '', text: '' }); renderSpine(); };
      scenes.appendChild(asRow);
      chap.appendChild(scenes);
      var filler = document.createElement('div'); filler.className = 'ch-filler'; chap.appendChild(filler);
      var cgrip = document.createElement('div'); cgrip.className = 'grip'; cgrip.title = 'Drag to deepen this chapter';
      cgrip.addEventListener('pointerdown', function(e){ startChapterDepth(e, chap, ch); });
      chap.appendChild(cgrip);
      box.appendChild(chap);
      chap.style.height = chapterHeight(ch, chap) + 'px';
    });
    var add = document.createElement('div');
    add.className = 'add-chapter'; add.textContent = '+ chapter';
    add.onclick = function(){ spineData.push({ floor: CH_FLOOR_MIN, scenes: [], title: '' }); renderSpine(); };
    box.appendChild(add);
    renderGrid();
    requestAnimationFrame(renderGrid);
  }

  var sDrag = null;
  function startSceneDepth(e, row, chap, ch, sc){ e.preventDefault(); e.stopPropagation();
    sDrag = { row:row, chap:chap, ch:ch, sc:sc, startY:e.clientY, startH:sc.depth }; document.body.classList.add('depth-resizing'); }
  var cDrag = null;
  function startChapterDepth(e, chap, ch){ e.preventDefault(); e.stopPropagation();
    cDrag = { chap:chap, ch:ch, startY:e.clientY, startFloor:ch.floor }; document.body.classList.add('depth-resizing'); }
  window.addEventListener('pointermove', function(e){
    if (sDrag){ var h = Math.max(SC_MIN, sDrag.startH + (e.clientY - sDrag.startY));
      sDrag.sc.depth = h; sDrag.row.style.minHeight = h + 'px'; sDrag.chap.style.height = chapterHeight(sDrag.ch, sDrag.chap) + 'px'; renderGrid(); return; }
    if (cDrag){ var f = Math.max(CH_FLOOR_MIN, cDrag.startFloor + (e.clientY - cDrag.startY));
      cDrag.ch.floor = f; cDrag.chap.style.height = chapterHeight(cDrag.ch, cDrag.chap) + 'px'; renderGrid(); }
  });
  window.addEventListener('pointerup', function(){ if (sDrag || cDrag){ sDrag=null; cDrag=null; document.body.classList.remove('depth-resizing'); } });
  renderSpine();

  // ---- drag the spine's right edge to widen it ----
  (function(){
    var grip = document.getElementById('grip'); var root = document.documentElement;
    var MIN = 84, MAX = 360, dragging = false;
    grip.addEventListener('pointerdown', function(e){ e.preventDefault(); dragging = true;
      document.body.classList.add('resizing'); try { grip.setPointerCapture(e.pointerId); } catch(_){} });
    window.addEventListener('pointermove', function(e){
      if(!dragging) return;
      var spine = document.getElementById('spine'); var left = spine.getBoundingClientRect().left;
      var w = Math.max(MIN, Math.min(MAX, e.clientX - left));
      root.style.setProperty('--spine', w + 'px');
    });
    window.addEventListener('pointerup', function(){ if(!dragging) return; dragging = false; document.body.classList.remove('resizing'); });
  })();
  document.getElementById('snapAll').onclick = snapAll;

  // ---- magnify the whole board + spine ----
  (function(){
    var zoom = 1, stageEl = document.querySelector('.stage'), zlabel = document.getElementById('zlabel');
    function setZoom(z){
      zoom = Math.max(0.6, Math.min(1.8, Math.round(z*10)/10));
      stageEl.style.zoom = zoom;
      zlabel.textContent = Math.round(zoom*100) + '%';
      renderGrid();
    }
    document.getElementById('zoomIn').onclick  = function(){ setZoom(zoom + 0.1); };
    document.getElementById('zoomOut').onclick = function(){ setZoom(zoom - 0.1); };
  })();
</script>
</body>
</html>
