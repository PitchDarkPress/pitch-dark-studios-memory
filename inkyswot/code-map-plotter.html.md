<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InkySwot — Plot Mapping</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&family=JetBrains+Mono:wght@300;400;500&family=Crimson+Pro:ital,wght@0,300;0,400;0,600;1,400&display=swap" rel="stylesheet">
<style>
  :root {
    --bg:#0f0d0a; --dot:#221a14; --panel:#18120d;
    --text:#e8e0d0; --text2:#b0a090; --muted:#706050;
    --gold:#c9923a; --gold-bright:#e8b060;
    --border:#221709; --border2:#352815; --danger:#c43a2a;
    --mono:'JetBrains Mono',monospace; --body:'Crimson Pro',Georgia,serif; --head:'Playfair Display',serif;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  html, body { height: 100%; }
  body { font-family: var(--body); background: var(--bg); color: var(--text); overflow: hidden; user-select: none; }
  #app { display: flex; flex-direction: column; height: 100vh; }

  header { display: flex; align-items: center; justify-content: space-between;
    padding: 12px 22px; background: var(--panel); border-bottom: 1px solid var(--border2); z-index: 1000; }
  .brand { display: flex; align-items: baseline; gap: 12px; }
  .wordmark { font-family: var(--head); font-weight: 900; font-size: 22px; color: var(--text); letter-spacing: .5px; }
  .screen-title { font-family: var(--body); font-style: italic; font-weight: 400; font-size: 16px; color: var(--text2); }
  .screen-title::before { content: "·"; margin-right: 10px; color: var(--muted); }
  .map-title { font-family: var(--head); font-weight: 900; font-size: 15px; color: var(--text);
    background: transparent; border: none; border-bottom: 1px solid transparent; outline: none;
    padding: 1px 4px; margin-left: 4px; min-width: 130px; max-width: 300px;
    user-select: text; -webkit-user-select: text; transition: border-color .15s, color .15s; }
  .map-title::placeholder { color: var(--muted); font-weight: 400; font-style: italic; font-family: var(--body); font-size: 15px; }
  .map-title:hover { border-bottom-color: var(--border2); }
  .map-title:focus { border-bottom-color: var(--gold); color: var(--gold-bright); }
  .actions { display: flex; align-items: center; gap: 8px; }
  button { font-family: var(--mono); cursor: pointer; border: none; color: inherit; background: transparent; }
  .tb { font-size: 12px; font-weight: 400; letter-spacing: .4px; padding: 7px 12px; border-radius: 5px;
    display: inline-flex; align-items: center; gap: 7px; transition: all .15s;
    background: #120d08; border: 1px solid var(--border2); color: var(--text2); }
  .tb:hover { color: var(--text); border-color: var(--muted); }
  .tb svg { width: 14px; height: 14px; }
  .tb.disabled { opacity: .35; pointer-events: none; }
  .tb-toggle.active { background: #120d08; border-color: var(--gold); color: var(--gold-bright); }
  .tb-clear:hover { color: var(--danger); border-color: var(--danger); }
  .tb-add { background: var(--gold); border-color: var(--gold); color: #0a0806; font-weight: 500; }
  .tb-add:hover { background: var(--gold-bright); border-color: var(--gold-bright); color: #0a0806; }
  .tb-transfer .badge { background: var(--gold); color: #0a0806; border-radius: 99px; font-size: 10px; padding: 1px 6px; font-weight: 500; }
  .tb-transfer.has:hover { border-color: var(--gold); color: var(--gold-bright); }
  .sep { width: 1px; height: 22px; background: var(--border2); margin: 0 4px; }

  #zoom { display: flex; align-items: stretch; height: 32px; background: #120d08;
    border: 1px solid var(--border2); border-radius: 5px; overflow: hidden; }
  #zoom button { width: 30px; font-family: var(--mono); font-size: 15px; color: var(--text2);
    display: flex; align-items: center; justify-content: center; }
  #zoom button:hover { color: var(--gold-bright); background: #1d150d; }
  #zoom #zoomReset { width: 50px; font-size: 11px; letter-spacing: .5px;
    border-left: 1px solid var(--border2); border-right: 1px solid var(--border2); }
  #zoom #zoomResetBtn svg { width: 13px; height: 13px; }

  /* section help — top-right pill + slide-in guide */
  .tb-help { background: transparent; border: 2px solid var(--gold); border-radius: 3px; color: var(--gold-bright);
    font-family: var(--mono); font-weight: 500; font-size: 12px; letter-spacing: .8px; height: 34px; padding: 0 12px;
    display: inline-flex; align-items: center; gap: 7px; transition: all .15s; }
  .tb-help:hover { background: var(--gold); color: #0a0806; }
  .tb-help .q { font-family: var(--head); font-weight: 900; font-size: 15px; line-height: 1; }
  .help-scrim { position: fixed; inset: 0; z-index: 5500; background: rgba(8,6,4,.4); opacity: 0; transition: opacity .25s; }
  .help-scrim.show { opacity: 1; }
  .help-panel { position: fixed; top: 0; right: 0; height: 100%; width: 360px; max-width: 86vw; background: var(--panel);
    border-left: 2px solid var(--gold); box-shadow: -12px 0 40px rgba(0,0,0,.55); z-index: 5600;
    transform: translateX(100%); transition: transform .28s ease; display: flex; flex-direction: column; }
  .help-panel.show { transform: translateX(0); }
  .help-head { display: flex; align-items: flex-start; justify-content: space-between; gap: 12px;
    padding: 20px 22px 14px; border-bottom: 1px solid var(--border2); }
  .help-kicker { font-family: var(--mono); font-size: 10px; letter-spacing: 2px; text-transform: uppercase; color: var(--gold); margin-bottom: 4px; }
  .help-head h2 { font-family: var(--head); font-weight: 900; font-size: 24px; color: var(--text); }
  .help-close { font-family: var(--mono); font-size: 22px; color: var(--muted); line-height: 1; }
  .help-close:hover { color: var(--text); }
  .help-body { overflow: auto; padding: 18px 22px 28px; }
  .help-tag { font-family: var(--body); font-style: italic; font-size: 16px; color: var(--text2); margin-bottom: 18px; }
  .help-body h3 { font-family: var(--mono); font-size: 10px; letter-spacing: 1.6px; text-transform: uppercase;
    color: var(--gold-bright); margin: 18px 0 7px; }
  .help-body p { font-family: var(--body); font-size: 15px; line-height: 1.5; color: var(--text); margin-bottom: 6px; }
  .help-body ul { list-style: none; display: flex; flex-direction: column; gap: 9px; margin-top: 4px; }
  .help-body li { font-family: var(--body); font-size: 15px; line-height: 1.45; color: var(--text); padding-left: 18px; position: relative; }
  .help-body li::before { content: "\203A"; position: absolute; left: 2px; color: var(--gold); font-family: var(--mono); }
  .help-foot { margin-top: 22px; padding-top: 14px; border-top: 1px solid var(--border2);
    font-family: var(--mono); font-size: 11px; color: var(--muted); }

  #board { position: relative; flex: 1; overflow: hidden; background: var(--bg); }
  #board.connect-mode { cursor: crosshair; }
  #board.connect-mode .note { cursor: pointer !important; }
  #board.connect-mode .note textarea { pointer-events: none; }
  #board.threading { cursor: crosshair; }
  #world { position: absolute; inset: 0; transform-origin: 0 0; pointer-events: none; z-index: 100; }
  #lines { position: absolute; inset: 0; width: 100%; height: 100%; overflow: visible; pointer-events: none; }
  #lines path.vis { fill: none; stroke: var(--gold); stroke-width: 2; stroke-linecap: round; }
  #lines path.hit { fill: none; stroke: transparent; stroke-width: 16; pointer-events: stroke; cursor: pointer; }
  #lines .link:hover path.vis { stroke: var(--danger) !important; }
  #lines .pins line { stroke: var(--gold); stroke-width: 1.2; stroke-dasharray: 2 5; opacity: .38; }
  .thread-temp { fill: none; stroke: var(--gold-bright); stroke-width: 2; stroke-dasharray: 5 6; stroke-linecap: round; pointer-events: none; }
  .empty { position: absolute; inset: 0; display: flex; flex-direction: column; align-items: center;
    justify-content: center; color: var(--muted); gap: 14px; pointer-events: none; z-index: 0; }
  .empty .glyph { font-family: var(--head); font-size: 46px; color: var(--border2); }
  .empty p { font-family: var(--mono); font-size: 12px; letter-spacing: .5px; }
  .hint { position: absolute; bottom: 120px; left: 50%; transform: translateX(-50%);
    background: var(--gold); color: #0a0806; font-family: var(--mono); font-size: 12px; padding: 8px 16px;
    border-radius: 99px; z-index: 2000; pointer-events: none; box-shadow: 0 6px 18px rgba(0,0,0,.4); }
  .pan-hint { position: absolute; left: 22px; bottom: 20px; z-index: 150; font-family: var(--mono);
    font-size: 10px; letter-spacing: .5px; color: var(--muted); pointer-events: none; }

  /* chapter dividers — toggle button (always reachable) + optional drag grip */
  #dividers { position: absolute; inset: 0; z-index: 70; pointer-events: none; }
  .divider { position: absolute; width: 0; border-left: 1px dashed var(--gold); opacity: .45; pointer-events: none; }
  .divider-toggle { position: absolute; transform: translateX(-50%); width: 22px; height: 22px;
    border-radius: 6px; background: var(--panel); border: 1px solid var(--gold); color: var(--gold-bright);
    display: flex; align-items: center; justify-content: center; cursor: pointer; pointer-events: auto;
    box-shadow: 0 2px 6px rgba(0,0,0,.5); }
  .divider-toggle:hover { background: var(--gold); color: #0a0806; }
  .divider-toggle svg { width: 12px; height: 12px; }
  .divider-grip { position: absolute; transform: translate(-50%, 50%); width: 14px; height: 14px;
    border-radius: 50%; background: var(--gold); border: 1px solid var(--gold-bright); cursor: ns-resize;
    pointer-events: auto; box-shadow: 0 2px 5px rgba(0,0,0,.5); }
  .divider-grip:hover { background: var(--gold-bright); }

  .note { position: absolute; width: 230px; z-index: 110; touch-action: none; pointer-events: auto; transition: width .12s; }
  .note.expanded { width: 290px; }
  .note.selected .note-card { box-shadow: 0 0 0 2px var(--gold-bright), 0 8px 22px rgba(0,0,0,.5); }
  .note.selected .note-tab { box-shadow: 0 0 0 2px var(--gold-bright); }
  .note.thread-target .note-front, .note.thread-target .note-back { box-shadow: 0 0 0 2px var(--gold-bright), 0 8px 22px rgba(0,0,0,.5); }
  .note-tab { display: inline-flex; align-items: baseline; height: 22px; margin-left: 12px; padding: 0 12px;
    border: 1px solid; border-bottom: none; border-radius: 8px 8px 0 0; cursor: grab;
    box-shadow: 0 -3px 8px rgba(0,0,0,.22); position: relative; z-index: 3; }
  .note-tab:active { cursor: grabbing; }
  .tab-label { font-family: var(--mono); font-size: 9.5px; font-weight: 500; letter-spacing: 1.2px; text-transform: uppercase; line-height: 1; }
  .note-tab .dt-dot { font-family: var(--mono); font-size: 14px; font-weight: 700; line-height: 1; margin-left: 1px; }

  /* flip — front sits flat (crisp) at rest; 3D context only while flipped */
  .note-flip { perspective: 1400px; }
  .note-flip-inner { position: relative; transition: transform .55s cubic-bezier(.4,.15,.2,1); }
  .note-flip-inner.d3 { transform-style: preserve-3d; }
  .note.flipped .note-flip-inner { transform: rotateY(180deg); }
  .note-face { backface-visibility: hidden; -webkit-backface-visibility: hidden; }
  .note-front { position: relative; }
  .note-back { position: absolute; inset: 0; transform: rotateY(180deg); background: #0c0a07;
    border: 1px solid var(--border2); border-radius: 0 0 4px 4px; box-shadow: 0 6px 16px rgba(0,0,0,.45);
    padding: 8px 10px 10px; display: flex; flex-direction: column; }
  .dt-head { font-family: var(--mono); font-size: 9.5px; font-weight: 500; letter-spacing: 1.6px;
    text-transform: uppercase; color: var(--gold); margin-bottom: 6px; }
  .dt-body { flex: 1; width: 100%; min-height: 56px; background: transparent; border: none; resize: none;
    outline: none; font-family: var(--body); font-size: 15px; line-height: 1.3; color: var(--text2);
    user-select: text; -webkit-user-select: text; overflow: auto; }
  .dt-body::placeholder { color: var(--muted); font-style: italic; }
  .dt-hint { font-family: var(--mono); font-size: 8.5px; letter-spacing: .6px; color: var(--muted); margin-top: 6px; opacity: .65; }

  .note-card { border-radius: 0 0 4px 4px; padding: 8px 10px 10px; border: 1px solid; position: relative;
    box-shadow: 0 6px 16px rgba(0,0,0,.45); min-height: 110px; }
  .note-top { display: flex; align-items: center; justify-content: flex-end; gap: 6px; margin-bottom: 6px; min-height: 18px; }
  .note-ctrl { display: flex; align-items: center; gap: 3px; }
  .note-ico { width: 18px; height: 18px; border-radius: 4px; display: flex; align-items: center;
    justify-content: center; background: transparent; opacity: .45; transition: all .12s; color: inherit; }
  .note:hover .note-ico { opacity: .8; }
  .note-ico:hover { opacity: 1 !important; background: rgba(0,0,0,.25); }
  .note-ico.del:hover { background: var(--danger); color: #fff; }
  .note-exp { display: inline-flex; align-items: center; gap: 4px; font-family: var(--mono); font-size: 8.5px;
    font-weight: 500; letter-spacing: .8px; text-transform: uppercase; opacity: .8; padding: 2px 6px;
    border-radius: 4px; border: 1px solid currentColor; background: transparent; white-space: nowrap; }
  .note-exp:hover { opacity: 1; }
  .note-exp svg { width: 10px; height: 10px; }
  .note-ico svg { width: 12px; height: 12px; }
  .note textarea.body { width: 100%; min-height: 56px; height: auto; overflow: hidden; background: transparent;
    border: none; resize: none; outline: none; font-family: var(--body); font-weight: 400; font-size: 15px;
    line-height: 1.3; user-select: text; -webkit-user-select: text; color: inherit; }
  .note textarea.body::placeholder { opacity: .4; font-style: italic; }

  .note-fields { margin-top: 10px; flex-direction: column; gap: 8px; }
  .field { display: flex; flex-direction: column; gap: 3px; }
  .field label { font-family: var(--mono); font-size: 9px; letter-spacing: 1.2px; text-transform: uppercase; color: #706050; }
  .field input, .field select, .field textarea {
    background: #0c0a07; border: 1px solid #352815; color: #e8e0d0; font-family: var(--body);
    font-size: 14px; border-radius: 3px; padding: 6px 8px; outline: none; width: 100%; }
  .field input:focus, .field select:focus, .field textarea:focus { border-color: #c9923a; }
  .field textarea { resize: none; min-height: 38px; line-height: 1.3; overflow: hidden; }
  .field select { appearance: none; -webkit-appearance: none; background-color: #0c0a07; cursor: pointer;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%23c9923a' stroke-width='3' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'/%3E%3C/svg%3E");
    background-repeat: no-repeat; background-position: right 9px center; padding-right: 26px; }
  .field select option { background: #18120d; color: #e8e0d0; }
  .note-foot { display: flex; align-items: center; justify-content: space-between; margin-top: 6px; min-height: 16px; }
  .foot-right { display: flex; align-items: center; gap: 7px; }
  .copy-count { font-family: var(--mono); font-size: 9px; letter-spacing: .6px; opacity: .7; }
  .chap-pill { font-family: var(--mono); font-size: 9px; letter-spacing: .6px; display: inline-flex; align-items: center;
    gap: 3px; background: rgba(201,146,58,.16); color: var(--gold-bright); border: 1px solid rgba(201,146,58,.4);
    border-radius: 99px; padding: 1px 4px 1px 7px; }
  .chap-pill button { font-size: 11px; line-height: 1; color: var(--gold-bright); opacity: .7; padding: 0 1px; }
  .chap-pill button:hover { opacity: 1; }
  .flag-badge { width: 16px; height: 16px; border-radius: 50%; background: var(--gold); color: #0a0806;
    display: flex; align-items: center; justify-content: center; font-size: 10px; }
  .flag-badge.sent { background: transparent; border: 1px solid var(--gold); color: var(--gold-bright); }

  .label-box { position: absolute; z-index: 80; transform: translate(-50%, -50%); pointer-events: none;
    display: inline-flex; align-items: center; gap: 1px; background: var(--panel);
    border: 1px solid var(--border2); border-radius: 7px; padding: 2px 3px; box-shadow: 0 2px 8px rgba(0,0,0,.5); }
  .label-box > * { pointer-events: auto; }
  .label-grip { width: 13px; align-self: stretch; cursor: grab; color: var(--muted); font-size: 10px;
    display: flex; align-items: center; justify-content: center; opacity: 0; transition: opacity .12s; }
  .label-box:hover .label-grip { opacity: 1; }
  .label-box textarea { border: none; outline: none; background: transparent; text-align: center;
    font-family: var(--mono); font-size: 10.5px; letter-spacing: .4px; color: var(--gold-bright);
    min-width: 26px; resize: none; overflow: hidden; line-height: 1.3; padding: 0; }
  .label-box textarea::placeholder { color: var(--muted); }
  .label-dir, .label-del, .label-color { width: 17px; height: 17px; border-radius: 5px; font-size: 11px;
    display: flex; align-items: center; justify-content: center; background: transparent; opacity: 0; transition: all .12s; }
  .label-box:hover .label-dir, .label-box:hover .label-del, .label-box:hover .label-color { opacity: 1; }
  .label-dir { color: var(--text2); } .label-dir:hover, .label-color:hover { background: var(--border2); }
  .color-dot { width: 10px; height: 10px; border-radius: 50%; display: block; }
  .label-del { color: var(--muted); } .label-del:hover { background: var(--danger); color: #fff; }

  .type-pop { position: fixed; z-index: 5000; background: var(--panel); border: 1px solid var(--border2);
    border-radius: 8px; padding: 6px; display: flex; flex-direction: column; gap: 2px; box-shadow: 0 12px 32px rgba(0,0,0,.6); min-width: 168px; }
  .type-pop .pop-head { font-family: var(--mono); font-size: 9px; letter-spacing: 1.2px; text-transform: uppercase; color: var(--muted); padding: 4px 6px 6px; }
  .type-pill { display: flex; align-items: center; gap: 9px; padding: 6px 8px; border-radius: 5px; background: transparent; font-family: var(--mono); font-size: 12px; color: var(--text); text-align: left; }
  .type-pill:hover { background: #120d08; }
  .type-dot { width: 13px; height: 13px; border-radius: 3px; border: 1px solid; flex: none; }

  .timeline { position: absolute; left: 0; right: 0; bottom: 0; height: 96px; background: var(--panel);
    border-top: 1px solid var(--gold); display: flex; flex-direction: column; z-index: 60; box-shadow: 0 -8px 24px rgba(0,0,0,.4); }
  .tl-head { display: flex; align-items: center; justify-content: space-between; padding: 6px 14px; border-bottom: 1px solid var(--border2); }
  .tl-left { display: flex; align-items: baseline; gap: 12px; }
  .tl-title { font-family: var(--mono); font-size: 10px; letter-spacing: 2px; text-transform: uppercase; color: var(--gold); }
  .tl-hint { font-family: var(--mono); font-size: 9.5px; letter-spacing: .4px; color: var(--muted); }
  .tl-add { font-family: var(--mono); font-size: 11px; color: var(--text2); display: inline-flex; align-items: center; gap: 5px; }
  .tl-add:hover { color: var(--gold-bright); }
  .chapters { flex: 1; display: flex; }
  .chapter { flex: 1; border-right: 1px dashed var(--border2); position: relative; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 4px; }
  .chapter:last-child { border-right: none; }
  .chapter .tick { width: 1px; height: 12px; background: var(--gold); opacity: .5; }
  .chapter .clabel { font-family: var(--mono); font-size: 11px; letter-spacing: .5px; color: var(--text2); }
  .chapter .crm { position: absolute; top: 4px; right: 6px; font-size: 11px; color: var(--muted); opacity: 0; }
  .chapter:hover .crm { opacity: 1; } .chapter .crm:hover { color: var(--danger); }
  .chapter.drop-target { background: rgba(201,146,58,.18); box-shadow: inset 0 3px 0 var(--gold); }

  .ada { position: absolute; right: 22px; bottom: 20px; z-index: 200; display: flex; flex-direction: column; align-items: flex-end; gap: 8px; }
  .ada-bubble { width: 46px; height: 46px; border-radius: 50%; background: #140f09; border: 1px solid var(--border2);
    display: flex; align-items: center; justify-content: center; font-family: var(--head); font-size: 18px; color: var(--muted); position: relative; transition: all .25s; }
  .ada-bubble .zzz { position: absolute; top: -6px; right: -4px; font-family: var(--mono); font-size: 9px; color: var(--muted); }
  .ada.watch .ada-bubble { color: var(--gold-bright); border-color: var(--gold); box-shadow: 0 0 0 3px rgba(201,146,58,.15), 0 0 18px rgba(201,146,58,.25); }
  .ada.watch .ada-bubble::after { content: ""; position: absolute; inset: -1px; border-radius: 50%; border: 1px solid var(--gold); animation: pulse 2.4s infinite; }
  @keyframes pulse { 0%{transform:scale(1);opacity:.6} 100%{transform:scale(1.5);opacity:0} }
  .ada-tip { background: var(--panel); border: 1px solid var(--border2); border-radius: 7px; padding: 7px 11px; font-family: var(--mono); font-size: 10.5px; color: var(--text2); white-space: nowrap; box-shadow: 0 6px 18px rgba(0,0,0,.5); }
  .ada-panel { background: var(--panel); border: 1px solid var(--gold); border-radius: 9px; padding: 10px; width: 230px; box-shadow: 0 10px 30px rgba(0,0,0,.6); }
  .ada-panel .ap-head { display: flex; align-items: center; justify-content: space-between; margin-bottom: 7px; }
  .ada-panel .ap-name { font-family: var(--mono); font-size: 10px; letter-spacing: 1.4px; text-transform: uppercase; color: var(--gold); }
  .ada-panel .ap-close { color: var(--muted); font-size: 13px; } .ada-panel .ap-close:hover { color: var(--text); }
  .ada-panel input { width: 100%; background: #0c0a07; border: 1px solid var(--border2); border-radius: 5px; padding: 8px; font-family: var(--body); font-size: 14px; color: var(--text); outline: none; }
  .ada-panel input:focus { border-color: var(--gold); }
  .ada-panel input::placeholder { color: var(--muted); font-style: italic; }

  .overlay { position: fixed; inset: 0; background: rgba(8,6,4,.7); z-index: 6000; display: flex; align-items: center; justify-content: center; }
  .modal { background: var(--panel); border: 1px solid var(--border2); border-radius: 12px; padding: 22px 24px; width: 380px; box-shadow: 0 20px 60px rgba(0,0,0,.7); }
  .modal h3 { font-family: var(--head); font-weight: 900; font-size: 19px; margin-bottom: 4px; }
  .modal .sub { font-family: var(--body); font-style: italic; color: var(--text2); font-size: 15px; margin-bottom: 14px; }
  .modal .breakdown { font-family: var(--mono); font-size: 12px; color: var(--text2); display: flex; flex-direction: column; gap: 6px; margin-bottom: 18px; max-height: 260px; overflow: auto; }
  .modal .breakdown .row { display: flex; align-items: center; gap: 8px; border-bottom: 1px solid var(--border); padding-bottom: 6px; }
  .modal .breakdown .row .type-dot { width: 11px; height: 11px; }
  .modal .breakdown .row span.txt { color: var(--text); }
  .modal .mbtns { display: flex; gap: 8px; justify-content: flex-end; }
  .modal .mbtns .tb-add { padding: 8px 16px; }
  .toast { position: fixed; bottom: 28px; left: 50%; transform: translateX(-50%); background: var(--gold); color: #0a0806;
    font-family: var(--mono); font-size: 12px; padding: 10px 18px; border-radius: 99px; z-index: 7000; box-shadow: 0 8px 24px rgba(0,0,0,.5); }
  svg { display: block; }
</style>
</head>
<body>
<div id="app">
  <header>
    <div class="brand">
      <span class="wordmark">InkySwot</span>
      <span class="screen-title">Plot Mapping</span>
      <input id="mapTitle" class="map-title" type="text" placeholder="Name your project…" spellcheck="false" />
    </div>
    <div class="actions">
      <button class="tb tb-undo disabled" id="undo">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 7v6h6"></path><path d="M21 17a9 9 0 0 0-9-9 9 9 0 0 0-6 2.3L3 13"></path></svg>
        Undo
      </button>
      <button class="tb tb-clear" id="clear">Clear</button>
      <button class="tb tb-toggle" id="timelineBtn">Timeline</button>
      <button class="tb tb-transfer" id="transfer">Transfer All <span class="badge" id="transferBadge" style="display:none">0</span></button>
      <div class="sep"></div>
      <button class="tb tb-toggle" id="connect">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>
        Connect
      </button>
      <button class="tb tb-add" id="add" data-opener>
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
        Add Note
      </button>
      <div class="sep"></div>
      <div id="zoom">
        <button id="zoomOut" title="Zoom out">&minus;</button>
        <button id="zoomReset" title="Reset view (100%)">100%</button>
        <button id="zoomIn" title="Zoom in">+</button>
        <button id="zoomResetBtn" title="Reset to 100%"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 3-6.7L3 8"></path><path d="M3 3v5h5"></path></svg></button>
      </div>
      <div class="sep"></div>
      <button class="tb tb-help" id="sectionHelp" title="What does this section do?">SECTION <span class="q">?</span></button>
    </div>
  </header>
  <div id="board">
    <div id="world"><svg id="lines"></svg></div>
    <div class="empty" id="empty">
      <div class="glyph">✦</div>
      <p>DOUBLE-CLICK ANYWHERE TO BEGIN MAPPING</p>
    </div>
    <div class="pan-hint">↑ ↓ ← → to move around</div>
  </div>
</div>

<script>
  const TYPES = [
    { key:"character", name:"Character",   bg:"#c9923a", border:"#e8b060", light:true, lab:"#3a2808" },
    { key:"location",  name:"Location",    bg:"#1a4a4a", border:"#2a6b6b", lab:"#6fc4c4" },
    { key:"plot",      name:"Plot Thread", bg:"#2a1a4a", border:"#4a3a7a", lab:"#a892e0" },
    { key:"event",     name:"Event",       bg:"#4a1a1a", border:"#7a3a3a", lab:"#dd9090" },
    { key:"object",    name:"Object",      bg:"#1a3a2a", border:"#2a5a3a", lab:"#73c79a" },
    { key:"subplot",   name:"Subplot",     bg:"#1a2a4a", border:"#3a4a7a", lab:"#8ba6ec" },
    { key:"free",      name:"Free Note",   bg:"#221a14", border:"#352815", lab:"#b0a090" },
  ];
  const FIELDS = {
    character: [
      { key:"name", label:"Name", kind:"text" },
      { key:"role", label:"Role", kind:"select", options:["Protagonist","Antagonist","Supporting Character","Minor Character","Other"] },
      { key:"desc", label:"Description", kind:"textarea" },
    ],
    location: [
      { key:"name", label:"Name", kind:"text" },
      { key:"ltype", label:"Type", kind:"select", options:["City","Town","Building","Wilderness","Region","Other"] },
      { key:"desc", label:"Description", kind:"textarea" },
    ],
    plot: [
      { key:"title", label:"Title", kind:"text" },
      { key:"ptype", label:"Type", kind:"select", options:["Main Plot","Mystery","Conflict","Quest","Revelation","Other"] },
      { key:"summary", label:"Summary", kind:"textarea" },
    ],
    event: [
      { key:"title", label:"Title", kind:"text" },
      { key:"etype", label:"Type", kind:"select", options:["Story Event","Turning Point","Revelation","Climax","Historical","Other"] },
    ],
    object: [
      { key:"name", label:"Name", kind:"text" },
      { key:"category", label:"Category", kind:"select", options:["Weapon","Document","Vehicle","Jewellery","Magical Artefact","Other"] },
      { key:"desc", label:"Description", kind:"textarea" },
    ],
    subplot: [
      { key:"title", label:"Title", kind:"text" },
      { key:"summary", label:"Summary", kind:"textarea" },
    ],
  };
  const LINE_COLORS = ["#c9923a", "#2a6b6b", "#4a3a7a", "#7a3a3a", "#2a5a3a", "#3a4a7a"];
  const DIR_ORDER = ["forward", "backward", "both", "none"];
  const DIR_ICON = { forward:"\u2192", backward:"\u2190", both:"\u21C4", none:"\u2014" };
  const NOTE_W = 230, HOP = 7, TL_H = 96, WORLD_W = 6000, WORLD_H = 4000, BASE = 1.2;
  const SVGNS = "http://www.w3.org/2000/svg";

  const board = document.getElementById("board");
  const world = document.getElementById("world");
  const linesSvg = document.getElementById("lines");
  const empty = document.getElementById("empty");
  const connectBtn = document.getElementById("connect");
  const timelineBtn = document.getElementById("timelineBtn");
  const transferBtn = document.getElementById("transfer");
  const transferBadge = document.getElementById("transferBadge");
  const undoBtn = document.getElementById("undo");
  const zoomReset = document.getElementById("zoomReset");
  const mapTitle = document.getElementById("mapTitle");

  let state = { notes: [], links: [], chapters: [{ id: cid() }, { id: cid() }, { id: cid() }], z: 1, dividers: [], title: "" };

  let connectMode = false, pendingLink = null;
  let dragId = null, offX = 0, offY = 0, labelDrag = null, pendingDrag = null;
  let dragMoved = false, labelMoved = false;
  let dividerDrag = null;
  let tabPending = null, threadDrag = null;
  let timelineVisible = true, adaState = "sleep";
  let scale = BASE, panX = 0, panY = 0;
  const noteEls = {}, labelEls = {};

  const history = [];
  function snapshot() {
    history.push(JSON.stringify({ notes: state.notes, links: state.links, chapters: state.chapters, z: state.z, dividers: state.dividers, title: state.title }));
    if (history.length > 60) history.shift();
    updateUndo();
  }
  function undo() {
    if (!history.length) return;
    const o = JSON.parse(history.pop());
    state.notes = o.notes; state.links = o.links; state.chapters = o.chapters; state.z = o.z;
    state.dividers = o.dividers || []; state.title = o.title || "";
    mapTitle.value = state.title;
    render(); renderLines(); renderTimeline(); renderDividers(); updateCounts(); updateUndo();
  }
  function updateUndo() { undoBtn.classList.toggle("disabled", history.length === 0); }

  function uid() { return Date.now() + "_" + Math.random().toString(36).slice(2, 7); }
  function cid() { return "ch_" + Math.random().toString(36).slice(2, 7); }
  function byId(id) { return state.notes.find(n => n.id === id); }
  function typeOf(key) { return TYPES.find(t => t.key === key) || TYPES[6]; }
  function clamp(v, lo, hi) { return Math.max(lo, Math.min(hi, v)); }
  function noteH(note) { const el = noteEls[note.id]; return el ? el.offsetHeight : 120; }
  function noteW(note) { const el = noteEls[note.id]; return el ? el.offsetWidth : (note.expanded ? 290 : NOTE_W); }
  function center(note) { return note ? { x: note.x + noteW(note) / 2, y: note.y + noteH(note) / 2 } : null; }
  // screen pointer -> world coords (accounts for pan + zoom)
  function worldPt(cx, cy) { const r = board.getBoundingClientRect(); return { x: (cx - r.left - panX) / scale, y: (cy - r.top - panY) / scale }; }
  function edgePoint(note, tx, ty) {
    const cx = note.x + noteW(note) / 2, cy = note.y + noteH(note) / 2;
    const dx = tx - cx, dy = ty - cy;
    if (dx === 0 && dy === 0) return { x: cx, y: cy };
    const hw = noteW(note) / 2, hh = noteH(note) / 2;
    const sx = dx !== 0 ? hw / Math.abs(dx) : Infinity;
    const sy = dy !== 0 ? hh / Math.abs(dy) : Infinity;
    const t = Math.min(sx, sy), len = Math.hypot(dx, dy) || 1, GAP = 5;
    return { x: cx + dx * t + (dx / len) * GAP, y: cy + dy * t + (dy / len) * GAP };
  }
  function linkEnds(link) {
    const na = byId(link.a), nb = byId(link.b);
    if (!na || !nb) return null;
    const ca = center(na), cb = center(nb);
    return { a: edgePoint(na, cb.x, cb.y), b: edgePoint(nb, ca.x, ca.y) };
  }

  function noteSummary(note) {
    const t = typeOf(note.type), f = FIELDS[note.type] || [];
    const fld = note.fields || {};
    const textField = f.find(x => x.kind === "text");
    const selField = f.find(x => x.kind === "select");
    let primary = textField ? (fld[textField.key] || "") : "";
    if (!primary) primary = (note.text || "").split("\n")[0].trim();
    if (!primary) primary = "Untitled";
    const parts = [primary, t.name];
    if (selField) parts.push(fld[selField.key] || selField.options[0]);
    return parts.join(" — ");
  }

  /* ---------------- zoom + pan ---------------- */
  function applyTransform() { world.style.transform = "translate(" + panX + "px," + panY + "px) scale(" + scale + ")"; }
  function updatePins() {
    const pins = linesSvg.querySelector(".pins"); if (!pins) return;
    pins.innerHTML = "";
    if (!timelineVisible) return;
    const stripTopWorld = (board.clientHeight - TL_H - panY) / scale, n = state.chapters.length;
    state.notes.forEach(note => {
      if (note.chapter == null) return;
      const idx = state.chapters.findIndex(c => c.id === note.chapter); if (idx < 0) return;
      const chWorldX = ((idx + 0.5) * (board.clientWidth / n) - panX) / scale;
      const ln = document.createElementNS(SVGNS, "line");
      ln.setAttribute("x1", note.x + noteW(note) / 2); ln.setAttribute("y1", note.y + noteH(note));
      ln.setAttribute("x2", chWorldX); ln.setAttribute("y2", stripTopWorld);
      pins.appendChild(ln);
    });
  }
  function pan(dx, dy) { panX += dx; panY += dy; applyTransform(); updatePins(); }
  function setZoom(z) {
    const ns = clamp(z, 0.36, 2.4);
    const cx = board.clientWidth / 2, cy = board.clientHeight / 2;
    const wx = (cx - panX) / scale, wy = (cy - panY) / scale;
    scale = ns;
    panX = cx - wx * scale; panY = cy - wy * scale;
    applyTransform(); zoomReset.textContent = Math.round(scale / BASE * 100) + "%"; updatePins();
  }
  function resetView() { scale = BASE; panX = 0; panY = 0; applyTransform(); zoomReset.textContent = "100%"; updatePins(); }

  /* ---------------- type picker ---------------- */
  function closePicker() { const p = document.getElementById("typePop"); if (p) p.remove(); }
  function openPicker(clientX, clientY, cb) {
    closePicker();
    const pop = document.createElement("div"); pop.className = "type-pop"; pop.id = "typePop";
    const head = document.createElement("div"); head.className = "pop-head"; head.textContent = "Choose a type"; pop.appendChild(head);
    TYPES.forEach(t => {
      const b = document.createElement("button"); b.className = "type-pill";
      const dot = document.createElement("span"); dot.className = "type-dot"; dot.style.background = t.bg; dot.style.borderColor = t.border;
      const lab = document.createElement("span"); lab.textContent = t.name;
      b.appendChild(dot); b.appendChild(lab);
      b.onclick = (e) => { e.stopPropagation(); cb(t.key); closePicker(); };
      pop.appendChild(b);
    });
    document.body.appendChild(pop);
    const w = pop.offsetWidth, h = pop.offsetHeight;
    pop.style.left = clamp(clientX, 8, window.innerWidth - w - 8) + "px";
    pop.style.top = clamp(clientY, 8, window.innerHeight - h - 8) + "px";
  }
  document.addEventListener("pointerdown", (e) => {
    if (!e.target.closest("#typePop") && !e.target.closest("[data-opener]")) closePicker();
  }, true);

  /* ---------------- notes ---------------- */
  function createNote(typeKey, x, y) {
    snapshot();
    state.z++;
    const visX = -panX / scale, visY = -panY / scale;
    const vw = board.clientWidth / scale, vh = board.clientHeight / scale;
    let nx = (x == null) ? visX + 40 + Math.random() * Math.max(20, vw - 300) : x;
    let ny = (y == null) ? visY + 40 + Math.random() * Math.max(20, vh - (timelineVisible ? TL_H / scale : 0) - 220) : y;
    nx = clamp(nx, 0, WORLD_W - NOTE_W); ny = clamp(ny, 0, WORLD_H - 130);
    state.notes.push({ id: uid(), type: typeKey, text: "", fields: {}, expanded: false, x: nx, y: ny, z: state.z, chapter: null, flagged: false, sent: false, dark: "", flipped: false, group: null });
    render(); applyGeometry(); updateCounts();
  }

  function buildFields(note) {
    const wrap = document.createElement("div");
    wrap.className = "note-fields";
    wrap.style.display = note.expanded ? "flex" : "none";
    const defs = FIELDS[note.type] || [];
    if (!note.fields) note.fields = {};
    defs.forEach(f => {
      const field = document.createElement("div"); field.className = "field";
      const lab = document.createElement("label"); lab.textContent = f.label; field.appendChild(lab);
      let ctl;
      if (f.kind === "select") {
        ctl = document.createElement("select");
        f.options.forEach(opt => { const o = document.createElement("option"); o.value = opt; o.textContent = opt; ctl.appendChild(o); });
        ctl.value = note.fields[f.key] || f.options[0];
        ctl.onfocus = () => snapshot();
        ctl.onchange = () => { note.fields[f.key] = ctl.value; pushFront(note); };
      } else if (f.kind === "textarea") {
        ctl = document.createElement("textarea"); ctl.rows = 1; ctl.value = note.fields[f.key] || "";
        const grow = () => { ctl.style.height = "auto"; ctl.style.height = ctl.scrollHeight + "px"; };
        ctl.onfocus = () => snapshot();
        ctl.oninput = () => { note.fields[f.key] = ctl.value; grow(); pushFront(note); applyGeometry(); };
        requestAnimationFrame(grow);
      } else {
        ctl = document.createElement("input"); ctl.type = "text"; ctl.value = note.fields[f.key] || "";
        ctl.onfocus = () => snapshot();
        ctl.oninput = () => { note.fields[f.key] = ctl.value; pushFront(note); };
      }
      ctl.dataset.fk = f.key;
      ctl.onpointerdown = (e) => e.stopPropagation();
      field.appendChild(ctl); wrap.appendChild(field);
    });
    return wrap;
  }

  function setDot(note) {
    const el = noteEls[note.id]; if (!el) return;
    const dot = el.querySelector(".dt-dot"); if (!dot) return;
    dot.style.color = (note.dark && note.dark.trim()) ? "#e23b2b" : "inherit";
  }
  function flipNote(note) {
    const el = noteEls[note.id]; if (!el) return;
    const inner = el.querySelector(".note-flip-inner");
    note.flipped = !note.flipped;
    if (note.flipped) {
      inner.classList.add("d3");
      requestAnimationFrame(() => el.classList.add("flipped"));
      const b = el.querySelector(".dt-body"); if (b) setTimeout(() => b.focus(), 360);
    } else {
      el.classList.remove("flipped");
      const onEnd = () => { inner.classList.remove("d3"); inner.removeEventListener("transitionend", onEnd); };
      inner.addEventListener("transitionend", onEnd);
    }
  }

  /* copies — front shared across the set, back is each copy's own */
  function frontGroup(note) { return note.group ? state.notes.filter(n => n.group === note.group) : [note]; }
  function pushFront(note) {
    if (!note.group) return;
    frontGroup(note).forEach(m => {
      if (m === note) return;
      m.type = note.type;
      m.text = note.text;
      m.fields = JSON.parse(JSON.stringify(note.fields || {}));
      const el = noteEls[m.id]; if (!el) return;
      const body = el.querySelector(".note-front textarea.body");
      if (body) { body.value = m.text; body.style.height = "auto"; body.style.height = body.scrollHeight + "px"; }
      el.querySelectorAll(".note-front .field [data-fk]").forEach(ctl => { const v = m.fields[ctl.dataset.fk]; if (v != null) ctl.value = v; });
    });
    applyGeometry();
  }
  function copyNote(note) {
    snapshot();
    if (!note.group) note.group = "g_" + uid();
    state.z++;
    const copy = {
      id: uid(), type: note.type, text: note.text,
      fields: JSON.parse(JSON.stringify(note.fields || {})),
      expanded: note.expanded, x: clamp(note.x + 26, 0, WORLD_W - NOTE_W), y: clamp(note.y + 26, 0, WORLD_H - 130),
      z: state.z, chapter: null, flagged: false, sent: false, dark: "", flipped: false, group: note.group
    };
    const idx = state.notes.findIndex(n => n.id === note.id);
    state.notes.splice(idx + 1, 0, copy);
    render(); applyGeometry(); updateCounts();
  }

  function render() {
    Object.values(noteEls).forEach(el => el.remove());
    for (const k in noteEls) delete noteEls[k];
    empty.style.display = state.notes.length === 0 ? "flex" : "none";

    state.notes.forEach(note => {
      const t = typeOf(note.type);
      const textCol = t.light ? "#2a1c08" : "#e8e0d0";
      const labelCol = t.lab || (t.light ? "#4a3208" : t.border);
      const hasFields = !!FIELDS[note.type];

      const el = document.createElement("div");
      el.className = "note" + (note.expanded && hasFields ? " expanded" : "");
      el.style.left = note.x + "px"; el.style.top = note.y + "px"; el.style.zIndex = 100 + note.z;

      // tab — now the type label; full-stop dot turns red for Dark Thoughts; click flips, drag pulls a thread
      const tab = document.createElement("div");
      tab.className = "note-tab";
      tab.style.background = t.bg; tab.style.borderColor = t.border; tab.style.color = labelCol;
      tab.title = "Click to flip · drag to connect";
      const dtCol = (note.dark && note.dark.trim()) ? '#e23b2b' : 'inherit';
      tab.innerHTML = '<span class="tab-label">' + t.name.toUpperCase() + '</span><span class="dt-dot" style="color:' + dtCol + '">.</span>';
      tab.addEventListener("pointerdown", (e) => {
        if (connectMode) return;
        e.preventDefault(); e.stopPropagation();
        tabPending = { note, sx: e.clientX, sy: e.clientY };
      });
      el.appendChild(tab);

      const flip = document.createElement("div"); flip.className = "note-flip";
      const inner = document.createElement("div"); inner.className = "note-flip-inner";

      // front face — the idea
      const front = document.createElement("div");
      front.className = "note-card note-face note-front";
      front.style.background = t.bg; front.style.borderColor = t.border; front.style.color = textCol;

      const top = document.createElement("div"); top.className = "note-top";
      const ctrl = document.createElement("div"); ctrl.className = "note-ctrl";

      let fieldsWrap = null;
      if (hasFields) {
        const exp = document.createElement("button");
        exp.className = "note-exp" + (note.expanded ? " on" : ""); exp.style.color = textCol;
        exp.title = note.expanded ? "Collapse details" : "Expand details";
        const expHTML = (up) => '<span>Details</span>' + (up
          ? '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"><polyline points="18 15 12 9 6 15"/></svg>'
          : '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"/></svg>');
        exp.innerHTML = expHTML(note.expanded);
        exp.onclick = (e) => {
          e.stopPropagation();
          note.expanded = !note.expanded;
          el.classList.toggle("expanded", note.expanded);
          exp.innerHTML = expHTML(note.expanded);
          exp.title = note.expanded ? "Collapse details" : "Expand details";
          fieldsWrap.style.display = note.expanded ? "flex" : "none";
          requestAnimationFrame(applyGeometry);
        };
        ctrl.appendChild(exp);
      }

      const cp = document.createElement("button");
      cp.className = "note-ico"; cp.style.color = textCol;
      cp.title = "Make a copy — for another chapter";
      cp.innerHTML = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="9" y="9" width="11" height="11" rx="2"></rect><path d="M5 15V5a2 2 0 0 1 2-2h10"></path></svg>';
      cp.onclick = (e) => { e.stopPropagation(); copyNote(note); };
      const send = document.createElement("button");
      send.className = "note-ico"; send.style.color = textCol;
      send.title = note.flagged ? "Unflag for transfer" : "Send to InkySwot";
      send.innerHTML = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="22" y1="2" x2="11" y2="13"></line><polygon points="22 2 15 22 11 13 2 9 22 2"></polygon></svg>';
      send.onclick = (e) => { e.stopPropagation(); snapshot(); note.flagged = !note.flagged; if (note.flagged) note.sent = false; render(); updateCounts(); };
      const del = document.createElement("button");
      del.className = "note-ico del"; del.style.color = textCol; del.title = "Delete";
      del.innerHTML = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="5" y1="5" x2="19" y2="19"/><line x1="19" y1="5" x2="5" y2="19"/></svg>';
      del.onclick = (e) => {
        e.stopPropagation(); snapshot();
        const grp = note.group;
        state.notes = state.notes.filter(x => x.id !== note.id);
        state.links = state.links.filter(l => l.a !== note.id && l.b !== note.id);
        if (grp) { const rem = state.notes.filter(n => n.group === grp); if (rem.length === 1) rem[0].group = null; }
        render(); renderLines(); updateCounts();
      };
      ctrl.appendChild(cp); ctrl.appendChild(send); ctrl.appendChild(del);
      top.appendChild(ctrl);

      const ta = document.createElement("textarea");
      ta.className = "body"; ta.value = note.text; ta.style.color = textCol; ta.placeholder = "Write your idea…";
      const grow = () => { ta.style.height = "auto"; ta.style.height = ta.scrollHeight + "px"; };
      ta.onfocus = () => snapshot();
      ta.oninput = () => { note.text = ta.value; grow(); pushFront(note); applyGeometry(); };
      requestAnimationFrame(grow);

      fieldsWrap = hasFields ? buildFields(note) : null;

      const foot = document.createElement("div"); foot.className = "note-foot";
      const chSlot = document.createElement("div");
      if (note.chapter != null) {
        const idx = state.chapters.findIndex(c => c.id === note.chapter);
        if (idx >= 0) {
          const pill = document.createElement("span"); pill.className = "chap-pill"; pill.innerHTML = "Ch." + (idx + 1);
          const x = document.createElement("button"); x.innerHTML = "&times;"; x.title = "Unpin";
          x.onclick = (e) => { e.stopPropagation(); snapshot(); note.chapter = null; render(); applyGeometry(); };
          pill.appendChild(x); chSlot.appendChild(pill);
        }
      }
      const flagSlot = document.createElement("div"); flagSlot.className = "foot-right";
      if (note.flagged || note.sent) {
        const badge = document.createElement("span");
        badge.className = "flag-badge" + (note.sent ? " sent" : ""); badge.innerHTML = "&#10003;";
        badge.title = note.sent ? "Transferred to InkySwot" : "Flagged — ready to transfer";
        flagSlot.appendChild(badge);
      }
      const members = frontGroup(note);
      if (members.length > 1) {
        const pos = members.findIndex(m => m.id === note.id) + 1;
        const cc = document.createElement("span"); cc.className = "copy-count"; cc.style.color = labelCol;
        cc.textContent = pos + " of " + members.length;
        flagSlot.appendChild(cc);
      }
      foot.appendChild(chSlot); foot.appendChild(flagSlot);

      front.appendChild(top); front.appendChild(ta);
      if (fieldsWrap) front.appendChild(fieldsWrap);
      front.appendChild(foot);

      // back face — Dark Thoughts
      const back = document.createElement("div");
      back.className = "note-face note-back";
      const dh = document.createElement("div"); dh.className = "dt-head"; dh.textContent = "Dark Thoughts";
      const dta = document.createElement("textarea"); dta.className = "dt-body"; dta.value = note.dark || ""; dta.placeholder = "Your eyes only…";
      dta.onfocus = () => snapshot();
      dta.oninput = () => { note.dark = dta.value; setDot(note); };
      dta.onpointerdown = (e) => e.stopPropagation();
      const dhint = document.createElement("div"); dhint.className = "dt-hint"; dhint.textContent = "Click the tab to turn it back over";
      back.appendChild(dh); back.appendChild(dta); back.appendChild(dhint);

      inner.appendChild(front); inner.appendChild(back);
      flip.appendChild(inner); el.appendChild(flip);
      if (note.flipped) { el.classList.add("flipped"); inner.classList.add("d3"); }

      el.addEventListener("pointerdown", (e) => {
        if (e.target.closest("button") || e.target.closest(".note-fields") || e.target.closest(".note-tab")) return;
        if (connectMode) {
          e.preventDefault();
          const p = worldPt(e.clientX, e.clientY);
          pendingDrag = { note, el, sx: e.clientX, sy: e.clientY, offX: p.x - note.x, offY: p.y - note.y, moved: false };
          try { el.setPointerCapture(e.pointerId); } catch (_) {}
          return;
        }
        if (e.target.tagName === "TEXTAREA") return;
        e.preventDefault();
        state.z++; note.z = state.z; el.style.zIndex = 100 + note.z;
        const p = worldPt(e.clientX, e.clientY);
        offX = p.x - note.x; offY = p.y - note.y;
        dragId = note.id; dragMoved = false; el.style.cursor = "grabbing";
        try { el.setPointerCapture(e.pointerId); } catch (_) {}
      });
      el.style.cursor = "grab";
      noteEls[note.id] = el;
      world.appendChild(el);
    });
  }

  /* ---------------- thread-pull from the tab ---------------- */
  function startThreadTemp() {
    let tmp = document.getElementById("threadTemp");
    if (!tmp) { tmp = document.createElementNS(SVGNS, "path"); tmp.id = "threadTemp"; tmp.setAttribute("class", "thread-temp"); linesSvg.appendChild(tmp); }
  }
  function updateThreadTemp(a, p) {
    const tmp = document.getElementById("threadTemp");
    if (tmp) tmp.setAttribute("d", "M " + a.x.toFixed(1) + " " + a.y.toFixed(1) + " L " + p.x.toFixed(1) + " " + p.y.toFixed(1));
  }
  function removeThreadTemp() { const tmp = document.getElementById("threadTemp"); if (tmp) tmp.remove(); }
  function noteUnder(cx, cy) {
    const elAt = document.elementFromPoint(cx, cy); if (!elAt) return null;
    const n = elAt.closest(".note"); if (!n) return null;
    for (const id in noteEls) if (noteEls[id] === n) return id;
    return null;
  }

  /* ---------------- connections ---------------- */
  function segInt(p1, p2, p3, p4) {
    const d1x = p2.x - p1.x, d1y = p2.y - p1.y, d2x = p4.x - p3.x, d2y = p4.y - p3.y;
    const den = d1x * d2y - d1y * d2x; if (Math.abs(den) < 1e-6) return null;
    const t = ((p3.x - p1.x) * d2y - (p3.y - p1.y) * d2x) / den;
    const u = ((p3.x - p1.x) * d1y - (p3.y - p1.y) * d1x) / den;
    if (t > 0.05 && t < 0.95 && u > 0.05 && u < 0.95) return { x: p1.x + t * d1x, y: p1.y + t * d1y, t };
    return null;
  }
  function buildD(link, i) {
    const e = linkEnds(link); if (!e) return "";
    const a = e.a, b = e.b, cr = [];
    state.links.forEach((o, j) => {
      if (j >= i || o === link) return;
      if (o.a === link.a || o.a === link.b || o.b === link.a || o.b === link.b) return;
      const eo = linkEnds(o); if (!eo) return;
      const p = segInt(a, b, eo.a, eo.b); if (p) cr.push(p);
    });
    cr.sort((x, y) => x.t - y.t);
    const len = Math.hypot(b.x - a.x, b.y - a.y) || 1, dx = (b.x - a.x) / len, dy = (b.y - a.y) / len;
    let d = `M ${a.x.toFixed(1)} ${a.y.toFixed(1)}`;
    cr.forEach(p => { d += ` L ${(p.x - dx * HOP).toFixed(1)} ${(p.y - dy * HOP).toFixed(1)} A ${HOP} ${HOP} 0 0 1 ${(p.x + dx * HOP).toFixed(1)} ${(p.y + dy * HOP).toFixed(1)}`; });
    d += ` L ${b.x.toFixed(1)} ${b.y.toFixed(1)}`;
    return d;
  }
  function setMarkers(path, dir, cidx) {
    dir = dir || "forward"; cidx = cidx || 0;
    path.removeAttribute("marker-start"); path.removeAttribute("marker-end");
    if (dir === "forward" || dir === "both") path.setAttribute("marker-end", "url(#ar-" + cidx + ")");
    if (dir === "backward" || dir === "both") path.setAttribute("marker-start", "url(#ar-" + cidx + ")");
  }
  function deleteLink(id) { snapshot(); state.links = state.links.filter(l => l.id !== id); renderLines(); }

  function renderLines() {
    let defs = "<defs>";
    LINE_COLORS.forEach((c, i) => {
      defs += '<marker id="ar-' + i + '" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6.5" markerHeight="6.5" orient="auto-start-reverse"><path d="M0,1 L9,5 L0,9" fill="none" stroke="' + c + '" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></marker>';
    });
    defs += "</defs>";
    linesSvg.innerHTML = defs + '<g class="pins"></g>';
    Object.values(labelEls).forEach(e => e.remove());
    for (const k in labelEls) delete labelEls[k];

    state.links.forEach((link, i) => {
      const cidx = link.cidx || 0;
      const g = document.createElementNS(SVGNS, "g"); g.setAttribute("class", "link");
      const hit = document.createElementNS(SVGNS, "path"); hit.setAttribute("class", "hit"); hit.dataset.linkId = link.id;
      hit.addEventListener("click", () => deleteLink(link.id));
      const titleEl = document.createElementNS(SVGNS, "title"); titleEl.textContent = "Click to delete connection"; hit.appendChild(titleEl);
      const path = document.createElementNS(SVGNS, "path"); path.setAttribute("class", "vis"); path.dataset.linkId = link.id;
      path.style.stroke = LINE_COLORS[cidx]; setMarkers(path, link.dir, cidx);
      g.appendChild(hit); g.appendChild(path); linesSvg.appendChild(g);

      const box = document.createElement("div"); box.className = "label-box";
      const grip = document.createElement("div");
      grip.className = "label-grip"; grip.innerHTML = "&#8942;&#8942;"; grip.title = "Slide along line";
      grip.addEventListener("pointerdown", (e) => { e.preventDefault(); e.stopPropagation(); labelDrag = { id: link.id }; labelMoved = false; });
      const input = document.createElement("textarea");
      input.rows = 1; input.value = link.label || ""; input.placeholder = "label";
      const sizeLab = () => {
        const lines = input.value.split("\n");
        const longest = Math.max(6, ...lines.map(l => l.length));
        input.style.width = Math.min(longest + 1, 22) + "ch";
        input.style.height = "auto"; input.style.height = input.scrollHeight + "px";
      };
      input.onfocus = () => snapshot();
      input.oninput = () => { link.label = input.value; sizeLab(); };
      input.onpointerdown = (e) => e.stopPropagation();
      requestAnimationFrame(sizeLab);
      const dirBtn = document.createElement("button");
      dirBtn.className = "label-dir"; dirBtn.textContent = DIR_ICON[link.dir || "forward"]; dirBtn.title = "Arrow direction";
      dirBtn.onclick = (e) => { e.stopPropagation(); snapshot(); link.dir = DIR_ORDER[(DIR_ORDER.indexOf(link.dir || "forward") + 1) % DIR_ORDER.length]; dirBtn.textContent = DIR_ICON[link.dir]; setMarkers(path, link.dir, link.cidx || 0); };
      const colorBtn = document.createElement("button");
      colorBtn.className = "label-color"; colorBtn.title = "Line colour";
      const dot = document.createElement("span"); dot.className = "color-dot"; dot.style.background = LINE_COLORS[cidx]; colorBtn.appendChild(dot);
      colorBtn.onclick = (e) => { e.stopPropagation(); snapshot(); link.cidx = ((link.cidx || 0) + 1) % LINE_COLORS.length; dot.style.background = LINE_COLORS[link.cidx]; path.style.stroke = LINE_COLORS[link.cidx]; setMarkers(path, link.dir, link.cidx); };
      const del = document.createElement("button");
      del.className = "label-del"; del.innerHTML = "&times;"; del.title = "Remove connection";
      del.onclick = (e) => { e.stopPropagation(); deleteLink(link.id); };
      box.appendChild(grip); box.appendChild(input); box.appendChild(dirBtn); box.appendChild(colorBtn); box.appendChild(del);
      labelEls[link.id] = box; world.appendChild(box);
    });
    applyGeometry();
  }
  function applyGeometry() {
    state.links.forEach((link, i) => {
      const d = buildD(link, i);
      linesSvg.querySelectorAll('path[data-link-id="' + link.id + '"]').forEach(p => p.setAttribute("d", d));
      const e = linkEnds(link), box = labelEls[link.id];
      if (e && box) {
        const t = (link.lpos == null) ? 0.5 : link.lpos;
        box.style.left = (e.a.x + (e.b.x - e.a.x) * t) + "px";
        box.style.top = (e.a.y + (e.b.y - e.a.y) * t) + "px";
      }
    });
    const pins = linesSvg.querySelector(".pins");
    if (pins) {
      pins.innerHTML = "";
      if (timelineVisible) {
        const stripTopWorld = (board.clientHeight - TL_H - panY) / scale;
        const n = state.chapters.length;
        state.notes.forEach(note => {
          if (note.chapter == null) return;
          const idx = state.chapters.findIndex(c => c.id === note.chapter);
          if (idx < 0) return;
          const chWorldX = ((idx + 0.5) * (board.clientWidth / n) - panX) / scale;
          const ln = document.createElementNS(SVGNS, "line");
          ln.setAttribute("x1", note.x + noteW(note) / 2); ln.setAttribute("y1", note.y + noteH(note));
          ln.setAttribute("x2", chWorldX); ln.setAttribute("y2", stripTopWorld);
          pins.appendChild(ln);
        });
      }
    }
  }

  /* ---------------- chapter dividers ---------------- */
  function renderDividers() {
    let layer = document.getElementById("dividers");
    if (!layer) { layer = document.createElement("div"); layer.id = "dividers"; board.appendChild(layer); }
    layer.innerHTML = "";
    if (!timelineVisible) return;
    const n = state.chapters.length;
    if (!state.dividers) state.dividers = [];
    while (state.dividers.length < n - 1) state.dividers.push(0);
    if (state.dividers.length > n - 1) state.dividers.length = Math.max(0, n - 1);
    if (n < 2) return;
    const colW = board.clientWidth / n;
    const stripTop = board.clientHeight - TL_H;
    const chevUp = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"><polyline points="18 15 12 9 6 15"/></svg>';
    const chevDown = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"/></svg>';
    for (let i = 0; i < n - 1; i++) {
      const h = clamp(state.dividers[i] || 0, 0, stripTop);
      const x = (i + 1) * colW;
      const up = h > 2;

      const line = document.createElement("div");
      line.className = "divider"; line.dataset.i = i;
      line.style.left = x + "px"; line.style.bottom = TL_H + "px"; line.style.height = h + "px";
      layer.appendChild(line);

      const toggle = document.createElement("button");
      toggle.className = "divider-toggle"; toggle.dataset.i = i;
      toggle.style.left = x + "px"; toggle.style.bottom = (TL_H - 11) + "px";
      toggle.title = up ? "Lower this divider" : "Raise this divider to the top";
      toggle.innerHTML = up ? chevDown : chevUp;
      toggle.onclick = (ev) => { ev.stopPropagation(); snapshot(); state.dividers[i] = up ? 0 : stripTop; renderDividers(); updateUndo(); };
      layer.appendChild(toggle);

      if (up) {
        const grip = document.createElement("div");
        grip.className = "divider-grip"; grip.dataset.i = i;
        grip.style.left = x + "px"; grip.style.bottom = (TL_H + h) + "px";
        grip.title = "Drag to set the height";
        grip.addEventListener("pointerdown", (ev) => {
          ev.preventDefault(); ev.stopPropagation();
          snapshot();
          dividerDrag = { index: i };
          try { grip.setPointerCapture(ev.pointerId); } catch (_) {}
        });
        layer.appendChild(grip);
      }
    }
  }

  /* ---------------- connect interactions ---------------- */
  function showHint(text) {
    let h = document.querySelector(".hint");
    if (text === null) { if (h) h.remove(); return; }
    if (!h) { h = document.createElement("div"); h.className = "hint"; board.appendChild(h); }
    h.textContent = text;
  }
  function handleConnectClick(note, el) {
    if (pendingLink == null) { pendingLink = note.id; el.classList.add("selected"); showHint("Now click another note to connect"); }
    else if (pendingLink === note.id) { pendingLink = null; el.classList.remove("selected"); showHint("Click a note to start a connection"); }
    else {
      const exists = state.links.some(l => (l.a === pendingLink && l.b === note.id) || (l.b === pendingLink && l.a === note.id));
      if (!exists) { snapshot(); state.links.push({ id: uid(), a: pendingLink, b: note.id, label: "", dir: "forward", cidx: 0, lpos: 0.5 }); renderLines(); }
      if (noteEls[pendingLink]) noteEls[pendingLink].classList.remove("selected");
      pendingLink = null; showHint("Click a note to start a connection");
    }
  }

  window.addEventListener("pointermove", (e) => {
    if (dividerDrag) {
      const rect = board.getBoundingClientRect();
      const stripTop = board.clientHeight - TL_H;
      const h = clamp(stripTop - (e.clientY - rect.top), 0, stripTop);
      state.dividers[dividerDrag.index] = h;
      const layer = document.getElementById("dividers");
      const line = layer && layer.querySelector('.divider[data-i="' + dividerDrag.index + '"]');
      const grip = layer && layer.querySelector('.divider-grip[data-i="' + dividerDrag.index + '"]');
      if (line) line.style.height = h + "px";
      if (grip) grip.style.bottom = (TL_H + h) + "px";
      return;
    }
    if (tabPending && !threadDrag && Math.hypot(e.clientX - tabPending.sx, e.clientY - tabPending.sy) > 5) {
      threadDrag = { fromId: tabPending.note.id };
      startThreadTemp(); board.classList.add("threading");
    }
    if (threadDrag) {
      const from = byId(threadDrag.fromId);
      if (from) { const p = worldPt(e.clientX, e.clientY); updateThreadTemp(edgePoint(from, p.x, p.y), p); }
      const overId = noteUnder(e.clientX, e.clientY);
      document.querySelectorAll(".note.thread-target").forEach(x => x.classList.remove("thread-target"));
      if (overId && overId !== threadDrag.fromId && noteEls[overId]) noteEls[overId].classList.add("thread-target");
      return;
    }
    if (pendingDrag && !pendingDrag.moved && dragId == null) {
      if (Math.hypot(e.clientX - pendingDrag.sx, e.clientY - pendingDrag.sy) > 5) {
        pendingDrag.moved = true;
        const n = pendingDrag.note;
        state.z++; n.z = state.z; pendingDrag.el.style.zIndex = 100 + n.z;
        offX = pendingDrag.offX; offY = pendingDrag.offY;
        dragId = n.id; dragMoved = false; pendingDrag.el.style.cursor = "grabbing";
      }
    }
    if (dragId != null) {
      const note = byId(dragId); if (!note) return;
      if (!dragMoved) { snapshot(); dragMoved = true; }
      const p = worldPt(e.clientX, e.clientY);
      note.x = clamp(p.x - offX, 0, WORLD_W - noteW(note));
      note.y = clamp(p.y - offY, 0, WORLD_H - 30);
      const el = noteEls[note.id];
      if (el) { el.style.left = note.x + "px"; el.style.top = note.y + "px"; }
      document.querySelectorAll(".chapter.drop-target").forEach(c => c.classList.remove("drop-target"));
      if (timelineVisible) {
        const noteBottomScreen = (note.y + noteH(note)) * scale + panY;
        if (noteBottomScreen > board.clientHeight - TL_H - 6) {
          const cxScreen = (note.x + noteW(note) / 2) * scale + panX;
          const idx = clamp(Math.floor(cxScreen / (board.clientWidth / state.chapters.length)), 0, state.chapters.length - 1);
          const colEl = document.querySelectorAll(".chapter")[idx];
          if (colEl) colEl.classList.add("drop-target");
        }
      }
      applyGeometry();
    } else if (labelDrag) {
      const link = state.links.find(l => l.id === labelDrag.id); if (!link) return;
      const e2 = linkEnds(link); if (!e2) return;
      if (!labelMoved) { snapshot(); labelMoved = true; }
      const a = e2.a, b = e2.b, p = worldPt(e.clientX, e.clientY);
      const vx = b.x - a.x, vy = b.y - a.y, l2 = vx * vx + vy * vy || 1;
      link.lpos = clamp(((p.x - a.x) * vx + (p.y - a.y) * vy) / l2, 0.12, 0.88);
      applyGeometry();
    }
  });

  window.addEventListener("pointerup", (e) => {
    if (dividerDrag) { dividerDrag = null; renderDividers(); updateUndo(); }
    if (threadDrag) {
      const overId = noteUnder(e.clientX, e.clientY);
      document.querySelectorAll(".note.thread-target").forEach(x => x.classList.remove("thread-target"));
      if (overId && overId !== threadDrag.fromId) {
        const a = threadDrag.fromId, b = overId;
        const exists = state.links.some(l => (l.a === a && l.b === b) || (l.a === b && l.b === a));
        if (!exists) { snapshot(); state.links.push({ id: uid(), a, b, label: "", dir: "forward", cidx: 0, lpos: 0.5 }); renderLines(); }
      }
      removeThreadTemp(); board.classList.remove("threading");
      threadDrag = null; tabPending = null; return;
    }
    if (tabPending) { flipNote(tabPending.note); tabPending = null; }
    if (pendingDrag) {
      if (!pendingDrag.moved) handleConnectClick(pendingDrag.note, pendingDrag.el);
      else if (pendingDrag.el) pendingDrag.el.style.cursor = "grab";
      pendingDrag = null;
    }
    if (dragId != null) {
      const note = byId(dragId);
      const dragEl = noteEls[dragId]; if (dragEl) dragEl.style.cursor = "grab";
      document.querySelectorAll(".chapter.drop-target").forEach(c => c.classList.remove("drop-target"));
      if (note && timelineVisible) {
        const stripTopScreen = board.clientHeight - TL_H;
        const noteBottomScreen = (note.y + noteH(note)) * scale + panY;
        if (noteBottomScreen > stripTopScreen - 6) {
          const cxScreen = (note.x + noteW(note) / 2) * scale + panX;
          const idx = clamp(Math.floor(cxScreen / (board.clientWidth / state.chapters.length)), 0, state.chapters.length - 1);
          note.chapter = state.chapters[idx].id;
          note.y = Math.max(0, (stripTopScreen - panY) / scale - noteH(note) - 10);
          render();
        }
      }
      dragId = null; applyGeometry(); updateUndo();
    }
    if (labelDrag) { labelDrag = null; updateUndo(); }
  });

  /* ---------------- timeline ---------------- */
  function renderTimeline() {
    let tl = document.querySelector(".timeline");
    if (!timelineVisible) { if (tl) tl.remove(); const a = board.querySelector(".ada"); if (a) a.style.bottom = "20px"; applyGeometry(); return; }
    if (!tl) {
      tl = document.createElement("div"); tl.className = "timeline";
      tl.innerHTML = '<div class="tl-head"><div class="tl-left"><span class="tl-title">Timeline</span><span class="tl-hint">Drag a note onto a chapter to pin it</span></div><button class="tl-add" id="addChapter">+ Add chapter</button></div><div class="chapters"></div>';
      board.appendChild(tl);
      tl.querySelector("#addChapter").onclick = () => { snapshot(); state.chapters.push({ id: cid() }); renderTimeline(); renderDividers(); applyGeometry(); };
    }
    const row = tl.querySelector(".chapters"); row.innerHTML = "";
    state.chapters.forEach((ch, i) => {
      const col = document.createElement("div"); col.className = "chapter";
      col.innerHTML = '<div class="tick"></div><div class="clabel">Ch.' + (i + 1) + '</div>';
      if (state.chapters.length > 1) {
        const rm = document.createElement("button"); rm.className = "crm"; rm.innerHTML = "&times;"; rm.title = "Remove chapter";
        rm.onclick = () => { snapshot(); state.notes.forEach(n => { if (n.chapter === ch.id) n.chapter = null; }); state.chapters = state.chapters.filter(c => c.id !== ch.id); renderTimeline(); renderDividers(); render(); applyGeometry(); };
        col.appendChild(rm);
      }
      row.appendChild(col);
    });
    const ada = board.querySelector(".ada"); if (ada) ada.style.bottom = (TL_H + 16) + "px";
    applyGeometry();
  }

  /* ---------------- transfer ---------------- */
  function updateCounts() {
    const n = state.notes.filter(x => x.flagged && !x.sent).length;
    transferBadge.textContent = n; transferBadge.style.display = n ? "inline-block" : "none";
    transferBtn.classList.toggle("has", n > 0);
  }
  function openTransfer() {
    const flagged = state.notes.filter(n => n.flagged && !n.sent);
    if (!flagged.length) { toast("No notes flagged. Use the ✈ icon on a note first."); return; }
    const ov = document.createElement("div"); ov.className = "overlay";
    let rows = "";
    flagged.forEach(n => {
      const t = typeOf(n.type);
      rows += '<div class="row"><span class="type-dot" style="background:' + t.bg + ';border-color:' + t.border + '"></span><span class="txt">' + noteSummary(n).replace(/</g, "&lt;") + '</span></div>';
    });
    ov.innerHTML = '<div class="modal"><h3>Transfer to InkySwot</h3><div class="sub">' + flagged.length + ' note' + (flagged.length > 1 ? "s" : "") + ' ready to transfer</div><div class="breakdown">' + rows + '</div><div class="mbtns"><button class="tb" id="tCancel">Cancel</button><button class="tb tb-add" id="tConfirm">Transfer ' + flagged.length + '</button></div></div>';
    document.body.appendChild(ov);
    ov.addEventListener("click", (e) => { if (e.target === ov) ov.remove(); });
    ov.querySelector("#tCancel").onclick = () => ov.remove();
    ov.querySelector("#tConfirm").onclick = () => {
      snapshot();
      flagged.forEach(n => { n.flagged = false; n.sent = true; });
      ov.remove(); render(); updateCounts();
      toast("Transferred " + flagged.length + " note" + (flagged.length > 1 ? "s" : "") + " to InkySwot");
    };
  }
  function toast(msg) {
    const t = document.createElement("div"); t.className = "toast"; t.textContent = msg; document.body.appendChild(t);
    setTimeout(() => { t.style.transition = "opacity .4s"; t.style.opacity = "0"; setTimeout(() => t.remove(), 400); }, 2200);
  }

  /* ---------------- Ada ---------------- */
  function buildAda() { const ada = document.createElement("div"); ada.className = "ada"; ada.setAttribute("data-opener", ""); board.appendChild(ada); renderAda(); }
  function renderAda() {
    const ada = board.querySelector(".ada");
    ada.className = "ada " + (adaState === "watch" || adaState === "ask" ? "watch" : "");
    ada.innerHTML = "";
    if (adaState === "ask") {
      const panel = document.createElement("div"); panel.className = "ada-panel";
      panel.innerHTML = '<div class="ap-head"><span class="ap-name">Ada</span><button class="ap-close">&times;</button></div>';
      const inp = document.createElement("input"); inp.placeholder = "Ask Ada about your plot…"; panel.appendChild(inp); ada.appendChild(panel);
      panel.querySelector(".ap-close").onclick = () => { adaState = "watch"; renderAda(); };
      inp.onpointerdown = (e) => e.stopPropagation();
      setTimeout(() => inp.focus(), 0);
    } else {
      if (adaState === "watch") { const tip = document.createElement("div"); tip.className = "ada-tip"; tip.textContent = "Ada is watching. Click to ask for help."; ada.appendChild(tip); }
      const bubble = document.createElement("div"); bubble.className = "ada-bubble";
      bubble.innerHTML = adaState === "watch" ? "A" : 'A<span class="zzz">z<sup>z</sup></span>';
      bubble.title = adaState === "watch" ? "Ada is watching" : "Ada is sleeping — click to wake";
      ada.appendChild(bubble);
    }
    ada.style.bottom = (timelineVisible ? TL_H + 16 : 20) + "px";
    ada.onclick = (e) => { if (e.target.closest(".ada-panel")) return; if (adaState === "sleep") adaState = "watch"; else if (adaState === "watch") adaState = "ask"; renderAda(); };
  }

  /* ---------------- toolbar ---------------- */
  undoBtn.onclick = undo;
  document.getElementById("add").onclick = (e) => { const r = e.currentTarget.getBoundingClientRect(); openPicker(r.right - 168, r.bottom + 6, (key) => createNote(key)); };
  document.getElementById("clear").onclick = () => {
    if (!state.notes.length && !state.links.length) return;
    snapshot(); state.notes = []; state.links = []; render(); renderLines(); updateCounts();
  };
  connectBtn.onclick = () => {
    connectMode = !connectMode;
    connectBtn.classList.toggle("active", connectMode);
    board.classList.toggle("connect-mode", connectMode);
    if (connectMode) showHint("Click a note to start a connection");
    else { if (pendingLink != null && noteEls[pendingLink]) noteEls[pendingLink].classList.remove("selected"); pendingLink = null; showHint(null); }
  };
  timelineBtn.onclick = () => { timelineVisible = !timelineVisible; timelineBtn.classList.toggle("active", timelineVisible); renderTimeline(); renderDividers(); renderAda(); };
  transferBtn.onclick = openTransfer;

  document.getElementById("zoomIn").onclick = () => setZoom(scale * 1.2);
  document.getElementById("zoomOut").onclick = () => setZoom(scale / 1.2);
  zoomReset.onclick = resetView;
  document.getElementById("zoomResetBtn").onclick = resetView;
  board.addEventListener("wheel", (e) => {
    if (!(e.ctrlKey || e.metaKey)) return;
    e.preventDefault();
    setZoom(scale * (e.deltaY < 0 ? 1.1 : 1 / 1.1));
  }, { passive: false });

  board.addEventListener("dblclick", (e) => {
    if (connectMode) return;
    if (e.target.closest(".note") || e.target.closest(".timeline") || e.target.closest(".ada") || e.target.closest(".label-box") || e.target.closest("#dividers")) return;
    const p = worldPt(e.clientX, e.clientY);
    openPicker(e.clientX, e.clientY, (key) => createNote(key, p.x - NOTE_W / 2, p.y - 18));
  });

  const panKeys = new Set();
  let panRAF = null, panSpeed = 0;
  const ARROWS = { ArrowUp: 1, ArrowDown: 1, ArrowLeft: 1, ArrowRight: 1 };
  function panTick() {
    let ux = 0, uy = 0;
    if (panKeys.has("ArrowLeft")) ux += 1;
    if (panKeys.has("ArrowRight")) ux -= 1;
    if (panKeys.has("ArrowUp")) uy -= 1;
    if (panKeys.has("ArrowDown")) uy += 1;
    if (ux || uy) {
      panSpeed = Math.min(5, panSpeed + 0.25);
      const len = Math.hypot(ux, uy) || 1;
      panX += (ux / len) * panSpeed; panY += (uy / len) * panSpeed;
      applyTransform(); updatePins();
      panRAF = requestAnimationFrame(panTick);
    } else { panSpeed = 0; panRAF = null; }
  }
  document.addEventListener("keydown", (e) => {
    if (e.target.closest("textarea, input, select")) return;
    if ((e.metaKey || e.ctrlKey) && e.key.toLowerCase() === "z") { e.preventDefault(); undo(); return; }
    if (ARROWS[e.key]) {
      e.preventDefault(); panKeys.add(e.key);
      if (!panRAF) panRAF = requestAnimationFrame(panTick);
    }
  });
  document.addEventListener("keyup", (e) => { if (ARROWS[e.key]) panKeys.delete(e.key); });
  window.addEventListener("blur", () => panKeys.clear());

  window.addEventListener("resize", () => { applyGeometry(); renderDividers(); });

  /* ---------------- map title ---------------- */
  mapTitle.value = state.title || "";
  mapTitle.onfocus = () => snapshot();
  mapTitle.oninput = () => { state.title = mapTitle.value; };

  /* ---------------- section help ---------------- */
  const SECTION_HELP = {
    title: "Plot Mapping",
    tagline: "Your story's corkboard — think here before you commit.",
    blocks: [
      { h: "What it is", p: "A free-form board for sketching a story out loud. Pin down characters, locations, plot threads, events, objects and subplots, then draw the connections between them. Nothing here is final — it's a thinking space, not the finished article." },
      { h: "How to use it", list: [
        "Double-click anywhere on the board to drop a new note.",
        "Grab a note by its body to move it about.",
        "Click a note's tab to flip it to its Dark Thoughts — your private side, never exported.",
        "Drag from the tab to another note to tie a thread between them.",
        "Copy a note (the copy icon) to place the same beat in more than one chapter.",
        "Drag a note down onto a chapter in the Timeline to pin it there.",
        "Flag a note with the paper-plane icon, then Transfer All to send your ideas into InkySwot proper."
      ] },
      { h: "A tip", p: "Make a mess first. Get everything out of your head and onto the board, then tidy, group and connect. The shape of the story usually shows up once it's all in front of you." }
    ],
    footer: "Looking for the full guide? It lives in Help — Manual."
  };
  function ensureHelp() {
    if (document.getElementById("helpPanel")) return;
    const scrim = document.createElement("div"); scrim.className = "help-scrim"; scrim.id = "helpScrim"; scrim.onclick = closeHelp;
    const panel = document.createElement("div"); panel.className = "help-panel"; panel.id = "helpPanel";
    document.body.appendChild(scrim); document.body.appendChild(panel);
  }
  function openHelp() {
    ensureHelp();
    const panel = document.getElementById("helpPanel"), scrim = document.getElementById("helpScrim"), d = SECTION_HELP;
    let html = '<div class="help-head"><div><div class="help-kicker">Section guide</div><h2>' + d.title + '</h2></div><button class="help-close" id="helpClose">&times;</button></div><div class="help-body">';
    if (d.tagline) html += '<p class="help-tag">' + d.tagline + '</p>';
    d.blocks.forEach(b => {
      html += '<h3>' + b.h + '</h3>';
      if (b.p) html += '<p>' + b.p + '</p>';
      if (b.list) { html += '<ul>'; b.list.forEach(li => html += '<li>' + li + '</li>'); html += '</ul>'; }
    });
    if (d.footer) html += '<p class="help-foot">' + d.footer + '</p>';
    html += '</div>';
    panel.innerHTML = html;
    panel.querySelector("#helpClose").onclick = closeHelp;
    requestAnimationFrame(() => { scrim.classList.add("show"); panel.classList.add("show"); });
  }
  function closeHelp() {
    const panel = document.getElementById("helpPanel"), scrim = document.getElementById("helpScrim");
    if (panel) panel.classList.remove("show");
    if (scrim) scrim.classList.remove("show");
  }
  document.getElementById("sectionHelp").onclick = openHelp;
  document.addEventListener("keydown", (e) => { if (e.key === "Escape") closeHelp(); });

  timelineBtn.classList.add("active");
  render(); renderLines(); buildAda(); renderTimeline(); renderDividers(); updateCounts(); updateUndo();
  applyTransform(); zoomReset.textContent = "100%";
</script>
</body>
</html>
