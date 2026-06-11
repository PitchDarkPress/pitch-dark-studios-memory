
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InkySwot — site map</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&family=Crimson+Pro:wght@300;400;600&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg2:#18120d; --bg0:#0a0806; --ink:#e8e0d0; --ink2:#b0a090; --ink3:#706050;
    --gold:#c9923a; --gold2:#e8b060; --rule:#221709; --rule2:#352815;
    --char:#cf7f57; --loc:#5fa898; --obj:#7a9bd0; --theme:#a07d9a; --evt:#c9923a;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  *{scrollbar-width:thin;scrollbar-color:var(--rule2) transparent;}
  *::-webkit-scrollbar{width:8px;}
  *::-webkit-scrollbar-thumb{background:var(--rule2);border-radius:5px;}
  *::-webkit-scrollbar-thumb:hover{background:var(--gold);}
  body{background:#000;font-family:'JetBrains Mono',monospace;padding:24px;display:flex;justify-content:center;}

  .bay{width:260px;height:660px;background:var(--bg2);border-left:1px solid var(--rule);position:relative;}
  .bay-head{height:38px;display:flex;align-items:center;padding:0 16px;border-bottom:1px solid var(--rule);
    font-size:11px;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);}
  .scroll{position:absolute;top:38px;left:0;right:0;bottom:0;overflow-y:auto;}
  .tree{position:relative;width:100%;}
  svg{position:absolute;inset:0;width:100%;pointer-events:none;}

  /* spine node (right) — the sections */
  .snode{position:absolute;right:16px;height:30px;border:1px solid var(--rule2);border-radius:3px;
    background:var(--bg0);transform:translateY(-50%);display:flex;align-items:center;padding:0 11px;
    font-size:9px;letter-spacing:.1em;text-transform:uppercase;color:var(--ink2);cursor:pointer;
    transition:border-color .35s,color .35s,box-shadow .35s;white-space:nowrap;z-index:6;}
  .snode:hover{border-color:var(--gold);color:var(--ink);}
  .snode.live{border-color:var(--gold2);color:var(--gold2);box-shadow:0 0 12px rgba(232,176,96,.4);}
  .snode .caret{margin-left:7px;font-size:8px;color:var(--ink3);transition:color .25s;}
  .snode.open .caret{color:var(--gold2);}

  .grpcap{position:absolute;right:16px;font-size:8px;letter-spacing:.18em;text-transform:uppercase;
    color:var(--gold);opacity:.8;transform:translateY(-50%);}

  /* leaf box (left) — hidden until its section is hovered */
  .leaf{position:absolute;left:14px;height:26px;border:1px solid var(--rule2);border-radius:3px;
    background:var(--bg0);display:flex;align-items:center;padding:0 9px;gap:6px;
    font-family:'Crimson Pro',serif;font-size:12px;color:var(--ink2);cursor:pointer;white-space:nowrap;max-width:150px;
    opacity:0;transform:translateY(-50%) translateX(14px);pointer-events:none;
    transition:opacity .3s ease,transform .3s cubic-bezier(.3,.1,.2,1),border-color .35s,color .35s,box-shadow .35s;}
  .leaf.shown{opacity:1;transform:translateY(-50%) translateX(0);pointer-events:auto;}
  .leaf:hover{border-color:var(--gold);color:var(--ink);}
  .leaf .nm{overflow:hidden;text-overflow:ellipsis;}
  .leaf .ct{font-family:'JetBrains Mono',monospace;font-size:8px;color:var(--ink3);margin-left:auto;
    border:1px solid var(--rule2);border-radius:8px;padding:0 5px;}
  .leaf .ct.zero{opacity:.4;}
  .leaf.flash{box-shadow:0 0 12px currentColor;}

  /* wires hidden until shown */
  .wire,.arrow{opacity:0;transition:opacity .3s ease,stroke .35s;}
  .wire.shown,.arrow.shown{opacity:1;}

  .bloom{position:absolute;left:14px;background:var(--bg0);border:1px solid;border-radius:3px;padding:4px 9px;
    font-family:'Crimson Pro',serif;font-size:11px;transform:translateY(-50%) translateX(-6px);opacity:0;
    transition:opacity .3s,transform .3s;pointer-events:none;white-space:nowrap;z-index:8;}
  .bloom.show{opacity:1;transform:translateY(-50%) translateX(0);}
  .bloom .bk{font-family:'JetBrains Mono',monospace;font-size:7px;letter-spacing:.1em;text-transform:uppercase;margin-right:5px;}

  .hint{position:absolute;left:0;right:0;bottom:0;padding:8px 14px;font-size:8px;letter-spacing:.12em;
    text-transform:uppercase;color:var(--ink3);text-align:center;background:linear-gradient(transparent,var(--bg2) 60%);}
</style>
</head>
<body>
  <div class="bay">
    <div class="bay-head">Site Map</div>
    <div class="scroll">
      <div class="tree" id="tree"><svg id="svg"></svg></div>
    </div>
    <div class="hint">hover a section to open its branches</div>
  </div>

<script>
  const NS='http://www.w3.org/2000/svg';
  const C={Character:'var(--char)',Location:'var(--loc)',Object:'var(--obj)',Theme:'var(--theme)',Event:'var(--evt)'};

  const MAP=[
    {group:'Main Menu', sections:[
      {n:'Overview', leaves:[]},
      {n:'Synopsis', leaves:[{n:'Events & Timeline',ct:7}]},
      {n:'Chapters', leaves:[{n:'Chapters',ct:5},{n:'Scenes',ct:25}]},
      {n:'DCW', leaves:[]},
    ]},
    {group:'World Building', sections:[
      {n:'Cast', leaves:[{n:'Characters',ct:5,c:'Character'},{n:'Relationships',ct:3},{n:'Language',ct:2},{n:'Factions',ct:0}]},
      {n:'World', leaves:[{n:'Locations',ct:3,c:'Location'},{n:'Buildings',ct:2},{n:'Objects',ct:1,c:'Object'},{n:'Rules & Lore',ct:0}]},
    ]},
    {group:'Notes', sections:[
      {n:'Library', leaves:[{n:'Research',ct:4},{n:'Scratchpad',ct:6},{n:'Sandbox',ct:1}]},
    ]},
  ];

  const tree=document.getElementById('tree'),svg=document.getElementById('svg');
  const W=260, SPINE_X=W-16-34, LEAF_RX=14+150;
  const GROUP_GAP=24, SEC_GAP=20, LEAF_STEP=34, PAD=22;

  let y=PAD, prevSpineY=null;
  const sections=[], allLeaves=[];

  MAP.forEach(g=>{
    const gc=document.createElement('div');gc.className='grpcap';gc.style.top=y+'px';gc.textContent=g.group;
    tree.appendChild(gc);
    y+=GROUP_GAP;

    g.sections.forEach(sec=>{
      const secY=y;

      if(prevSpineY!=null){
        const p=document.createElementNS(NS,'path');
        p.setAttribute('d',`M ${SPINE_X} ${prevSpineY} V ${secY}`);
        p.setAttribute('fill','none');p.setAttribute('stroke','rgba(201,146,58,.3)');p.setAttribute('stroke-width','1');
        svg.appendChild(p);
      }

      const sEl=document.createElement('div');sEl.className='snode';sEl.style.top=secY+'px';
      sEl.innerHTML=sec.n+(sec.leaves.length?'<span class="caret">▸</span>':'');
      tree.appendChild(sEl);
      const secRec={el:sEl,y:secY,name:sec.n,leaves:[]};
      sections.push(secRec);

      // leaves are laid out BELOW the section node, revealed on hover
      sec.leaves.forEach((L,li)=>{
        const ly=secY + 40 + li*LEAF_STEP;
        const midx=SPINE_X-20;
        const path=document.createElementNS(NS,'path');
        path.setAttribute('class','wire');
        path.setAttribute('d',`M ${SPINE_X} ${secY+15} V ${ly} H ${LEAF_RX}`);
        path.setAttribute('fill','none');path.setAttribute('stroke','rgba(201,146,58,.3)');path.setAttribute('stroke-width','1');
        svg.appendChild(path);
        const ar=document.createElementNS(NS,'path');
        ar.setAttribute('class','arrow');
        ar.setAttribute('d',`M ${LEAF_RX+5} ${ly-3} L ${LEAF_RX} ${ly} L ${LEAF_RX+5} ${ly+3}`);
        ar.setAttribute('fill','none');ar.setAttribute('stroke','rgba(201,146,58,.3)');ar.setAttribute('stroke-width','1');
        svg.appendChild(ar);

        const lEl=document.createElement('div');lEl.className='leaf';lEl.style.top=ly+'px';
        lEl.innerHTML='<span class="nm">'+L.n+'</span><span class="ct'+(L.ct===0?' zero':'')+'">'+L.ct+'</span>';
        tree.appendChild(lEl);
        secRec.leaves.push({el:lEl,y:ly,name:L.n,wire:path,arrow:ar});
        allLeaves.push({el:lEl,y:ly,name:L.n,wire:path,arrow:ar});
      });

      prevSpineY=secY;
      // advance: section + (its leaf block, collapsed when closed leaves only a small gap)
      y = secY + SEC_GAP + 18;
    });
    y += GROUP_GAP;
  });

  tree.style.height=(y+PAD)+'px';
  svg.setAttribute('height',(y+PAD));

  /* ---- hover reveal: one section at a time ---- */
  let pinned=null; // hovering wins; live walk continues underneath
  function openSection(sec){
    sections.forEach(s=>{
      const on = s===sec;
      s.el.classList.toggle('open',on);
      s.leaves.forEach(L=>{
        L.el.classList.toggle('shown',on);
        L.wire.classList.toggle('shown',on);
        L.arrow.classList.toggle('shown',on);
      });
    });
  }
  function closeAll(){
    sections.forEach(s=>{
      s.el.classList.remove('open');
      s.leaves.forEach(L=>{L.el.classList.remove('shown');L.wire.classList.remove('shown');L.arrow.classList.remove('shown');});
    });
  }
  sections.forEach(sec=>{
    sec.el.addEventListener('mouseenter',()=>{pinned=sec;openSection(sec);});
    sec.el.addEventListener('mouseleave',()=>{ setTimeout(()=>{ if(pinned===sec){/* keep open while over leaves */} },10); });
    // keep open while pointer is over the leaf column near this section
    sec.leaves.forEach(L=>{
      L.el.addEventListener('mouseenter',()=>{pinned=sec;openSection(sec);});
    });
  });
  // close when leaving the tree entirely
  tree.addEventListener('mouseleave',()=>{pinned=null;closeAll();});

  /* ---- the life (runs whether or not a branch is open) ---- */
  let si=0;
  function step(){
    sections.forEach((s,j)=>s.el.classList.toggle('live',j===si));
    si=(si+1)%sections.length;
  }
  step();setInterval(step,2600);

  // demo: every so often, auto-open a section so the reveal is visible without a mouse
  const demoOrder=[4,5,2]; let di=0;
  function demoHover(){
    if(pinned) return; // don't fight a real hover
    const sec=sections[demoOrder[di%demoOrder.length]];
    openSection(sec);
    setTimeout(()=>{ if(!pinned) closeAll(); },1900);
    di++;
  }
  setTimeout(demoHover,1200);setInterval(demoHover,3200);

  // blooms still fire on the live walk (off whichever leaf, briefly opening it)
  const adds=[['Cast','Characters','Character','Scrooge'],['World','Locations','Location','Counting-House'],
              ['Cast','Characters','Character','Tiny Tim'],['World','Objects','Object','The Chain']];
  let ai=0;
  function bloom(){
    if(pinned) {ai++;return;}
    const [secName,leafName,kind,name]=adds[ai%adds.length];
    const sec=sections.find(s=>s.name===secName);
    const L=sec&&sec.leaves.find(x=>x.name===leafName);
    if(L){
      openSection(sec);
      const c=C[kind]||'var(--gold2)';
      const b=document.createElement('div');b.className='bloom';b.style.top=L.y+'px';b.style.left='150px';
      b.style.borderColor=c;b.innerHTML='<span class="bk" style="color:'+c+'">+'+kind+'</span>'+name;
      tree.appendChild(b);requestAnimationFrame(()=>b.classList.add('show'));
      L.el.style.color=c;L.el.style.borderColor=c;L.el.classList.add('flash');
      setTimeout(()=>{
        b.classList.remove('show');setTimeout(()=>b.remove(),350);
        L.el.classList.remove('flash');L.el.style.color='';L.el.style.borderColor='';
        if(!pinned) closeAll();
      },1700);
    }
    ai++;
  }
  setTimeout(bloom,2600);setInterval(bloom,3200);
</script>
</body>
</html>