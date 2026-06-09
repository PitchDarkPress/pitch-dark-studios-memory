
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Plot Mapping — the board</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Crimson+Pro:ital,wght@0,400;0,500;0,600;1,400&family=JetBrains+Mono:wght@400;500;600&display=swap');

  :root{
    --bg:#0a0806;
    --panel:#0f0d0a;
    --ink:#e8e0d0;
    --mute:#8a8170;
    --faint:#5a5345;
    --gold:#c9923a;
    --gold-bright:#e8b060;
    --rule:#2a2620;
    --rule-soft:#1c1915;

    --c-event:#b08a6a;
    --c-location:#5fa898;
    --c-character:#cba36a;
    --c-object:#a88f6a;
    --c-theme:#a07d9a;
  }

  *{box-sizing:border-box;margin:0;padding:0;}

  html,body{height:100%;}
  body{
    background:var(--bg);
    color:var(--ink);
    font-family:'Crimson Pro',serif;
    overflow:hidden;
  }

  .topbar{
    height:46px;
    display:flex;align-items:center;
    padding:0 22px;
    border-bottom:1px solid var(--rule);
    background:linear-gradient(180deg,#13110d,#0c0a07);
    gap:18px;
    position:relative;z-index:5;
  }
  .wordmark{
    font-family:'JetBrains Mono',monospace;
    font-size:13px;letter-spacing:.22em;
    color:var(--gold);text-transform:uppercase;font-weight:600;
  }
  .crumb{
    font-family:'JetBrains Mono',monospace;
    font-size:10px;letter-spacing:.18em;
    color:var(--faint);text-transform:uppercase;
  }
  .topbar .right{margin-left:auto;display:flex;gap:20px;align-items:center;}
  .switch{
    font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.16em;
    color:var(--mute);text-transform:uppercase;display:flex;align-items:center;gap:8px;
  }
  .switch .dot{width:7px;height:7px;border-radius:50%;background:var(--gold);box-shadow:0 0 8px var(--gold);}

  .board-wrap{
    position:absolute;inset:46px 0 0 0;
    overflow:auto;
  }
  .board{
    min-width:1180px;
    padding:0 0 80px 0;
  }

  .track-head{
    display:grid;
    grid-template-columns:230px repeat(6,1fr);
    position:sticky;top:0;z-index:4;
    background:linear-gradient(180deg,#100e0a,#0c0a07);
    border-bottom:1px solid var(--rule);
  }
  .th-corner{
    padding:14px 20px 12px;
    border-right:1px solid var(--rule);
    display:flex;flex-direction:column;justify-content:flex-end;
  }
  .th-corner .label{
    font-family:'JetBrains Mono',monospace;font-size:10px;
    letter-spacing:.2em;color:var(--faint);text-transform:uppercase;
  }
  .th-corner .sub{
    font-size:15px;color:var(--mute);font-style:italic;margin-top:2px;
  }
  .th{
    padding:14px 16px 12px;
    border-right:1px solid var(--rule-soft);
    display:flex;flex-direction:column;justify-content:flex-end;gap:3px;
  }
  .th .name{
    font-family:'JetBrains Mono',monospace;font-size:11px;
    letter-spacing:.16em;text-transform:uppercase;font-weight:500;
  }
  .th .count{
    font-family:'JetBrains Mono',monospace;font-size:9px;
    letter-spacing:.14em;color:var(--faint);
  }
  .th .chev{font-size:11px;color:var(--faint);margin-top:2px;}

  .stave{
    display:grid;
    grid-template-columns:230px repeat(6,1fr);
    border-bottom:1px solid var(--rule);
    background:rgba(154,143,176,.05);
  }
  .stave-label{
    grid-column:1 / -1;
    padding:13px 20px 11px;
    display:flex;align-items:baseline;gap:14px;
  }
  .stave-label .kick{
    font-family:'JetBrains Mono',monospace;font-size:10px;
    letter-spacing:.24em;text-transform:uppercase;color:var(--c-character);
    font-weight:600;
  }
  .stave-label .ttl{
    font-size:18px;color:var(--ink);font-weight:500;
  }
  .stave-label .ln{
    flex:1;height:1px;background:linear-gradient(90deg,#9a8fb0,transparent);
    align-self:center;opacity:.5;
  }

  .scene{
    display:grid;
    grid-template-columns:230px repeat(6,1fr);
    border-bottom:1px solid var(--rule-soft);
    min-height:96px;
  }
  .scene:hover{background:rgba(201,146,58,.022);}

  .spine{
    position:sticky;left:0;z-index:3;
    border-right:1px solid var(--rule);
    padding:16px 20px;
    background:linear-gradient(90deg,#0e0c09 80%,#0c0a07);
    display:flex;flex-direction:column;gap:5px;
  }
  .spine .kick{
    font-family:'JetBrains Mono',monospace;font-size:9.5px;
    letter-spacing:.2em;text-transform:uppercase;color:var(--gold);
  }
  .spine .ttl{
    font-size:19px;color:var(--ink);line-height:1.15;font-weight:500;
  }
  .spine .meta{
    font-family:'JetBrains Mono',monospace;font-size:9px;
    letter-spacing:.12em;color:var(--faint);margin-top:auto;
    display:flex;gap:10px;
  }

  .cell{
    border-right:1px solid var(--rule-soft);
    padding:12px 13px;
    display:flex;flex-direction:column;gap:9px;
  }

  .note{position:relative;padding-left:0;}
  .note .nt-sub{
    font-family:'JetBrains Mono',monospace;font-size:9.5px;
    letter-spacing:.1em;text-transform:uppercase;font-weight:500;
    margin-bottom:3px;
  }
  .note .nt-desc{
    font-size:14.5px;color:var(--mute);line-height:1.28;
  }
  .note .nt-end{
    height:2px;width:26px;margin-top:7px;border-radius:1px;opacity:.85;
  }

  .t-event .nt-sub{color:var(--c-event);}
  .t-event .nt-end{background:var(--c-event);}
  .t-location .nt-sub{color:var(--c-location);}
  .t-location .nt-end{background:var(--c-location);}
  .t-character .nt-sub{color:var(--c-character);}
  .t-character .nt-end{background:var(--c-character);}
  .t-object .nt-sub{color:var(--c-object);}
  .t-object .nt-end{background:var(--c-object);}
  .t-theme .nt-sub{color:var(--c-theme);}
  .t-theme .nt-end{background:var(--c-theme);}

  .curve-cell{
    border-right:1px solid var(--rule-soft);
    position:relative;padding:0;overflow:hidden;
  }
  .curve-cell svg{display:block;width:100%;height:100%;}

  .footer-note{
    position:fixed;bottom:0;left:0;right:0;
    padding:9px 22px;
    background:linear-gradient(180deg,transparent,#0a0806 40%);
    font-family:'JetBrains Mono',monospace;font-size:9.5px;
    letter-spacing:.14em;color:var(--faint);text-transform:uppercase;
    text-align:center;z-index:6;pointer-events:none;
  }
</style>
</head>
<body>

  <div class="topbar">
    <span class="wordmark">InkySwot</span>
    <span class="crumb">A Christmas Carol · Plot Mapping</span>
    <div class="right">
      <span class="switch"><span class="dot"></span>the board</span>
      <span class="crumb">a look</span>
    </div>
  </div>

  <div class="board-wrap">
    <div class="board">

      <div class="track-head">
        <div class="th-corner">
          <span class="label">The Spine</span>
          <span class="sub">scenes ↓</span>
        </div>
        <div class="th"><span class="name" style="color:var(--c-event)">Events</span><span class="count">what happens</span><span class="chev">⌄</span></div>
        <div class="th"><span class="name" style="color:var(--c-location)">Locations</span><span class="count">where</span><span class="chev">⌄</span></div>
        <div class="th"><span class="name" style="color:var(--c-character)">Characters</span><span class="count">who</span><span class="chev">⌄</span></div>
        <div class="th"><span class="name" style="color:var(--c-object)">Objects</span><span class="count">things</span><span class="chev">⌄</span></div>
        <div class="th"><span class="name" style="color:var(--c-theme)">Themes</span><span class="count">motifs</span><span class="chev">⌄</span></div>
        <div class="th"><span class="name" style="color:var(--gold)">Tension</span><span class="count">the curve</span><span class="chev">⌄</span></div>
      </div>

      <div class="stave">
        <div class="stave-label">
          <span class="kick">Stave One</span>
          <span class="ttl">Marley's Ghost</span>
          <span class="ln"></span>
        </div>
      </div>

      <div class="scene">
        <div class="spine">
          <span class="kick">Scene One</span>
          <span class="ttl">The Counting-House</span>
          <span class="meta"><span>3 events</span><span>·</span><span>p.1</span></span>
        </div>
        <div class="cell t-event">
          <div class="note"><div class="nt-sub">Fred's Visit</div><div class="nt-desc">The nephew calls with Christmas cheer. "Bah! Humbug!"</div><div class="nt-end"></div></div>
          <div class="note"><div class="nt-sub">The Charity Men</div><div class="nt-desc">Two gentlemen seek alms. Are there no prisons?</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-location">
          <div class="note"><div class="nt-sub">The Counting-House</div><div class="nt-desc">Cold, fog and frost. A small fire; the clerk's smaller still.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-character">
          <div class="note"><div class="nt-sub">Ebenezer Scrooge</div><div class="nt-desc">Tight-fisted, solitary. A squeezing, grasping old sinner.</div><div class="nt-end"></div></div>
          <div class="note"><div class="nt-sub">Bob Cratchit</div><div class="nt-desc">The clerk, in his dismal little cell, copying letters.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-object"></div>
        <div class="cell t-theme">
          <div class="note"><div class="nt-sub">Cold &amp; Warmth</div><div class="nt-desc">External cold mirrors the inner.</div><div class="nt-end"></div></div>
        </div>
        <div class="curve-cell">
          <svg viewBox="0 0 100 96" preserveAspectRatio="none">
            <path d="M0,72 C25,68 40,60 60,58 S90,52 100,50" fill="none" stroke="var(--gold)" stroke-width="1.4" opacity="0.85"/>
          </svg>
        </div>
      </div>

      <div class="scene">
        <div class="spine">
          <span class="kick">Scene Two</span>
          <span class="ttl">The Door-Knocker</span>
          <span class="meta"><span>2 events</span><span>·</span><span>p.2</span></span>
        </div>
        <div class="cell t-event">
          <div class="note"><div class="nt-sub">The Face in the Knocker</div><div class="nt-desc">Marley's face, with a dismal light about it.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-location">
          <div class="note"><div class="nt-sub">Scrooge's Chambers</div><div class="nt-desc">Gloomy rooms in a lowering pile of building.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-character">
          <div class="note"><div class="nt-sub">Ebenezer Scrooge</div><div class="nt-desc">Home through the fog to his gloomy suite of rooms.</div><div class="nt-end"></div></div>
          <div class="note"><div class="nt-sub">Jacob Marley</div><div class="nt-desc">Dead these seven years. His face upon the knocker.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-object">
          <div class="note"><div class="nt-sub">The Door-Knocker</div><div class="nt-desc">An ordinary knocker — but for the face.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-theme">
          <div class="note"><div class="nt-sub">The Supernatural</div><div class="nt-desc">The first crack in the rational world.</div><div class="nt-end"></div></div>
        </div>
        <div class="curve-cell">
          <svg viewBox="0 0 100 96" preserveAspectRatio="none">
            <path d="M0,50 C20,48 35,40 55,34 S85,22 100,26" fill="none" stroke="var(--gold)" stroke-width="1.4" opacity="0.85"/>
          </svg>
        </div>
      </div>

      <div class="scene">
        <div class="spine">
          <span class="kick">Scene Three</span>
          <span class="ttl">Marley's Ghost</span>
          <span class="meta"><span>4 events</span><span>·</span><span>p.3</span></span>
        </div>
        <div class="cell t-event">
          <div class="note"><div class="nt-sub">The Chain</div><div class="nt-desc">"I wear the chain I forged in life."</div><div class="nt-end"></div></div>
          <div class="note"><div class="nt-sub">The Warning</div><div class="nt-desc">Three Spirits will haunt him.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-location">
          <div class="note"><div class="nt-sub">Scrooge's Chambers</div><div class="nt-desc">By firelight, the bells ring of their own accord.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-character">
          <div class="note"><div class="nt-sub">Jacob Marley</div><div class="nt-desc">In pigtail, waistcoat, tights — and a chain of cash-boxes.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-object">
          <div class="note"><div class="nt-sub">The Chain of Cash-Boxes</div><div class="nt-desc">Forged link by link, yard by yard.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-theme">
          <div class="note"><div class="nt-sub">Redemption</div><div class="nt-desc">The chance Marley never had, offered.</div><div class="nt-end"></div></div>
        </div>
        <div class="curve-cell">
          <svg viewBox="0 0 100 96" preserveAspectRatio="none">
            <path d="M0,26 C20,22 30,14 50,12 S80,18 100,30" fill="none" stroke="var(--gold)" stroke-width="1.4" opacity="0.85"/>
          </svg>
        </div>
      </div>

      <div class="stave">
        <div class="stave-label">
          <span class="kick">Stave Two</span>
          <span class="ttl">The First of the Three Spirits</span>
          <span class="ln"></span>
        </div>
      </div>

      <div class="scene">
        <div class="spine">
          <span class="kick">Scene One</span>
          <span class="ttl">The Ghost of Christmas Past</span>
          <span class="meta"><span>2 events</span><span>·</span><span>p.4</span></span>
        </div>
        <div class="cell t-event">
          <div class="note"><div class="nt-sub">The Spirit Appears</div><div class="nt-desc">A light springs up; the hour bell tolls one.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-location">
          <div class="note"><div class="nt-sub">Scrooge's Bedroom</div><div class="nt-desc">The curtains of his bed drawn aside by a hand.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-character">
          <div class="note"><div class="nt-sub">Ghost of Christmas Past</div><div class="nt-desc">A strange figure — like a child, yet like an old man.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-object">
          <div class="note"><div class="nt-sub">The Cap</div><div class="nt-desc">A great extinguisher, held under its arm.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-theme">
          <div class="note"><div class="nt-sub">Memory</div><div class="nt-desc">The past as a living, walkable place.</div><div class="nt-end"></div></div>
        </div>
        <div class="curve-cell">
          <svg viewBox="0 0 100 96" preserveAspectRatio="none">
            <path d="M0,30 C20,40 35,46 55,44 S85,38 100,40" fill="none" stroke="var(--gold)" stroke-width="1.4" opacity="0.85"/>
          </svg>
        </div>
      </div>

      <div class="scene">
        <div class="spine">
          <span class="kick">Scene Two</span>
          <span class="ttl">Old Fezziwig's Ball</span>
          <span class="meta"><span>3 events</span><span>·</span><span>p.5</span></span>
        </div>
        <div class="cell t-event">
          <div class="note"><div class="nt-sub">The Ball</div><div class="nt-desc">Fiddle, dancing, cake and negus.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-location">
          <div class="note"><div class="nt-sub">Fezziwig's Warehouse</div><div class="nt-desc">Cleared for the dance; warm, bright, full.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-character">
          <div class="note"><div class="nt-sub">Fezziwig</div><div class="nt-desc">A jovial old master; the power to make happy.</div><div class="nt-end"></div></div>
          <div class="note"><div class="nt-sub">Young Scrooge</div><div class="nt-desc">An apprentice, light of heart, not yet hardened.</div><div class="nt-end"></div></div>
        </div>
        <div class="cell t-object"></div>
        <div class="cell t-theme">
          <div class="note"><div class="nt-sub">Generosity</div><div class="nt-desc">Small kindness, vast in its effect.</div><div class="nt-end"></div></div>
        </div>
        <div class="curve-cell">
          <svg viewBox="0 0 100 96" preserveAspectRatio="none">
            <path d="M0,40 C20,52 35,60 55,62 S85,54 100,48" fill="none" stroke="var(--gold)" stroke-width="1.4" opacity="0.85"/>
          </svg>
        </div>
      </div>

    </div>
  </div>

  <div class="footer-note">Plot Mapping · the board · EVENTS · LOCATIONS · CHARACTERS · OBJECTS · THEMES · TENSION · a still picture (old colours)</div>

</body>
</html>
