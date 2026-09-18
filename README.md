<!DOCTYPE html>
<!-- saved from url=(0090)https://8000-cs-836306445512-default.cs-asia-southeast1-kelp.cloudshell.dev/ui/?authuser=0 -->
<html lang="en"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<title>TerraCarbon — Live Ops</title>
<link rel="stylesheet" href="./TerraCarbon — Live Ops_files/leaflet.css">
<style>
  :root { color-scheme: dark; }
  body { margin:0; font-family: -apple-system, Segoe UI, Roboto, sans-serif; background:#0d1117; color:#e6edf3; }
  header { padding:20px 28px; border-bottom:1px solid #21262d; }
  header h1 { margin:0; font-size:20px; }
  header p { margin:4px 0 0; color:#8b949e; font-size:13px; }
  main { padding:20px 28px; display:grid; gap:20px; }
  .kpis { display:grid; grid-template-columns: repeat(auto-fit, minmax(160px,1fr)); gap:12px; }
  .kpi { background:#161b22; border:1px solid #21262d; border-radius:10px; padding:14px 16px; }
  .kpi .val { font-size:26px; font-weight:600; }
  .kpi .label { color:#8b949e; font-size:12px; text-transform:uppercase; letter-spacing:.04em; }
  .grid2 { display:grid; grid-template-columns: 1.3fr 1fr; gap:20px; }
  @media (max-width: 900px) { .grid2 { grid-template-columns: 1fr; } }
  .card { background:#161b22; border:1px solid #21262d; border-radius:10px; padding:16px; }
  .card h2 { margin:0 0 12px; font-size:14px; color:#c9d1d9; text-transform:uppercase; letter-spacing:.04em; }
  table { width:100%; border-collapse: collapse; font-size:13px; }
  th, td { text-align:left; padding:6px 8px; border-bottom:1px solid #21262d; }
  th { color:#8b949e; font-weight:500; }
  .sev-crit { color:#f85149; font-weight:600; }
  .sev-warn { color:#d29922; font-weight:600; }
  .sev-info { color:#58a6ff; font-weight:600; }
  .badge { padding:2px 8px; border-radius:20px; font-size:11px; }
  .badge.active { background:#3d1e1e; color:#f85149; }
  .badge.acknowledged { background:#3d331e; color:#d29922; }
  .badge.resolved { background:#1e3d24; color:#3fb950; }
  button { background:#21262d; border:1px solid #30363d; color:#e6edf3; padding:4px 10px; border-radius:6px; font-size:12px; cursor:pointer; margin-right:4px; }
  button:hover { background:#30363d; }
  .precaution { font-size:12px; color:#8b949e; margin-top:6px; white-space:pre-wrap; }
  .status-dot { display:inline-block; width:8px; height:8px; border-radius:50%; margin-right:6px; }
  .dot-normal { background:#3fb950; } .dot-watch { background:#d29922; } .dot-alert { background:#f85149; }
  #map { height: 340px; border-radius: 8px; }
  .leaflet-popup-content-wrapper { background:#161b22; color:#e6edf3; }
  .leaflet-popup-tip { background:#161b22; }
</style>
</head>
<body>
<header>
  <h1>TerraCarbon — Live Agent Observability</h1>
  <p>Satellite + ground sensor fusion · Root Orchestrator Agent · Drone swarm control · auto-refreshing every 5s</p>
</header>
<main>
  <div class="kpis" id="kpis"><div class="kpi"><div class="val">15</div><div class="label">Active Alerts</div></div><div class="kpi"><div class="val">12.1</div><div class="label">Avg ppm</div></div><div class="kpi"><div class="val">10/10</div><div class="label">Sensors Online</div></div><div class="kpi"><div class="val">5</div><div class="label">Satellite Passes</div></div></div>

  <div class="card">
    <h2>Site Map</h2>
    <div id="map" class="leaflet-container leaflet-touch leaflet-retina leaflet-fade-anim leaflet-grab leaflet-touch-drag leaflet-touch-zoom" tabindex="0" style="position: relative; outline-style: none;"><div class="leaflet-pane leaflet-map-pane" style="transform: translate3d(0px, 0px, 0px);"><div class="leaflet-pane leaflet-tile-pane"><div class="leaflet-layer " style="z-index: 1; opacity: 1;"><div class="leaflet-tile-container leaflet-zoom-animated" style="z-index: 12; transform: translate3d(0px, 0px, 0px) scale(1);"><img alt="" src="./TerraCarbon — Live Ops_files/960@2x.png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(320px, -95px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/960@2x(1).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(576px, -95px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/961@2x.png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(320px, 161px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/961@2x(1).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(576px, 161px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/960@2x(2).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(64px, -95px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/960@2x(3).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(832px, -95px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/961@2x(2).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(64px, 161px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/961@2x(3).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(832px, 161px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/960@2x(4).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(-192px, -95px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/960@2x(5).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(1088px, -95px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/961@2x(4).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(-192px, 161px, 0px); opacity: 1;"><img alt="" src="./TerraCarbon — Live Ops_files/961@2x(5).png" class="leaflet-tile leaflet-tile-loaded" style="width: 256px; height: 256px; transform: translate3d(1088px, 161px, 0px); opacity: 1;"></div><div class="leaflet-tile-container leaflet-zoom-animated" style="z-index: 11; transform: translate3d(0px, 0px, 0px) scale(0.5);"></div></div></div><div class="leaflet-pane leaflet-overlay-pane"><svg pointer-events="none" class="leaflet-zoom-animated" width="1410" height="408" viewBox="-117 -34 1410 408" style="transform: translate3d(-117px, -34px, 0px);"><g><path class="leaflet-interactive" stroke="#f85149" stroke-opacity="1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" fill="#f85149" fill-opacity="0.7" fill-rule="evenodd" d="M431,229a10,10 0 1,0 20,0 a10,10 0 1,0 -20,0 "></path><path class="leaflet-interactive" stroke="#f85149" stroke-opacity="1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" fill="#f85149" fill-opacity="0.7" fill-rule="evenodd" d="M564,94a10,10 0 1,0 20,0 a10,10 0 1,0 -20,0 "></path><path class="leaflet-interactive" stroke="#f85149" stroke-opacity="1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" fill="#f85149" fill-opacity="0.7" fill-rule="evenodd" d="M461,256a10,10 0 1,0 20,0 a10,10 0 1,0 -20,0 "></path></g></svg></div><div class="leaflet-pane leaflet-shadow-pane"></div><div class="leaflet-pane leaflet-marker-pane"></div><div class="leaflet-pane leaflet-tooltip-pane"></div><div class="leaflet-pane leaflet-popup-pane"></div><div class="leaflet-proxy leaflet-zoom-animated" style="transform: translate3d(374283px, 246025px, 0px) scale(1024);"></div></div><div class="leaflet-control-container"><div class="leaflet-top leaflet-left"><div class="leaflet-control-zoom leaflet-bar leaflet-control"><a class="leaflet-control-zoom-in" href="https://8000-cs-836306445512-default.cs-asia-southeast1-kelp.cloudshell.dev/ui/?authuser=0#" title="Zoom in" role="button" aria-label="Zoom in" aria-disabled="false"><span aria-hidden="true">+</span></a><a class="leaflet-control-zoom-out" href="https://8000-cs-836306445512-default.cs-asia-southeast1-kelp.cloudshell.dev/ui/?authuser=0#" title="Zoom out" role="button" aria-label="Zoom out" aria-disabled="false"><span aria-hidden="true">−</span></a></div></div><div class="leaflet-top leaflet-right"></div><div class="leaflet-bottom leaflet-left"></div><div class="leaflet-bottom leaflet-right"><div class="leaflet-control-attribution leaflet-control"><a href="https://leafletjs.com/" title="A JavaScript library for interactive maps"><svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="12" height="8" viewBox="0 0 12 8" class="leaflet-attribution-flag"><path fill="#4C7BE1" d="M0 0h12v4H0z"></path><path fill="#FFD500" d="M0 4h12v3H0z"></path><path fill="#E0BC00" d="M0 7h12v1H0z"></path></svg> Leaflet</a> <span aria-hidden="true">|</span> OpenStreetMap, CARTO</div></div></div></div>
  </div>

  <div class="grid2">
    <div class="card">
      <h2>Active Alerts</h2>
      <div id="alerts"><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-warn">[WARN]</span> Elevated concentration — Wellhead A-12 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Permian Basin · Ground sensor readings trending upward over the last 3 hours.</div><div style="margin-top:8px;"><button onclick="act(&#39;0Nitt3iCYeisICl0QQqy&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;0Nitt3iCYeisICl0QQqy&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Wellhead B-05 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Perur Storage Terminal · Reading of 9.56 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;1hw5AnTaiBTriRJBCRQL&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;1hw5AnTaiBTriRJBCRQL&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Pipeline Jct. 9B <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Pichanur Compressor Station · Reading of 7.82 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;87kJ7o0TJHxF4rhSXGJN&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;87kJ7o0TJHxF4rhSXGJN&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Compressor Sta. 4 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Pichanur Compressor Station · Reading of 7.24 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;BsFpTCRETlRSk67TiZu5&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;BsFpTCRETlRSk67TiZu5&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Flare stack inefficiency detected <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Anadarko Basin · Combustion efficiency model flags incomplete flaring.</div><div style="margin-top:8px;"><button onclick="act(&#39;CxtdSAKVbIz8vdf1o7QZ&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;CxtdSAKVbIz8vdf1o7QZ&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Metering Sta. 2 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Pichanur Compressor Station · Reading of 7.14 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;D0q6ZjO8fJxbzI0rZxmZ&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;D0q6ZjO8fJxbzI0rZxmZ&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-warn">[WARN]</span> Sensor cluster degraded — Valve Cluster V-7 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Bakken Field 3 · Signal strength dropped below 60% across 4 sensors.</div><div style="margin-top:8px;"><button onclick="act(&#39;GYbyffdN3WpCquPo2CIY&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;GYbyffdN3WpCquPo2CIY&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Wellhead A-12 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Pichanur Compressor Station · Reading of 11.31 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;N9vLqz6xxUtILHOIera8&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;N9vLqz6xxUtILHOIera8&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-warn">[WARN]</span> Elevated methane — Valve Cluster V-7 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Pichanur Compressor Station · Reading of 4.12 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;PHrKbFol7AW12GboLjur&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;PHrKbFol7AW12GboLjur&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Flare Stack F-2 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Pichanur Compressor Station · Reading of 6.4 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;cYi9EyECap9POAno3P7U&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;cYi9EyECap9POAno3P7U&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Confirmed high-rate leak — Pipeline Jct. 9B <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Marcellus North · Sensor and satellite fusion confirms a leak rate of 34.2 kg/hr, 94% model confidence.</div><div style="margin-top:8px;"><button onclick="act(&#39;iXVsDzphR9LeN4MGdyAp&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;iXVsDzphR9LeN4MGdyAp&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Separator S-6 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Coimbatore North Refinery · Reading of 12.75 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;lfVreQPt8PFMmJrzKtss&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;lfVreQPt8PFMmJrzKtss&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-info">[INFO]</span> Satellite pass anomaly under review <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Eagle Ford East · Concentration reading above baseline but below alert threshold.</div><div style="margin-top:8px;"><button onclick="act(&#39;ljtoQVO3lqCNN3BT7hfb&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;ljtoQVO3lqCNN3BT7hfb&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Pipeline Jct. 14 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Coimbatore North Refinery · Reading of 14.16 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;ssGZp8Ec1uE1R2BbAcMe&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;ssGZp8Ec1uE1R2BbAcMe&#39;,&#39;resolve&#39;)">Resolve</button></div></div><div style="border-bottom:1px solid #21262d; padding:10px 0;"><div><span class="sev-crit">[CRIT]</span> Elevated methane — Storage Tank T-3 <span class="badge active">active</span></div><div style="color:#8b949e; font-size:12px; margin-top:2px;">Perur Storage Terminal · Reading of 13.16 ppm detected, agent-confirmed above threshold.</div><div class="precaution">1) Evacuate personnel within 50m of the sensor location. 2) Eliminate ignition sources nearby (no open flame, switching, vehicles). 3) Ventilate any enclosed spaces near the site. 4) Route to site safety engineer for dual-signature isolation per HITL protocol. 5) Keep monitoring until ppm returns to baseline for 3 consecutive readings.</div><div style="margin-top:8px;"><button onclick="act(&#39;tlm0PEbif4l7JoWjVdeh&#39;,&#39;acknowledge&#39;)">Acknowledge</button><button onclick="act(&#39;tlm0PEbif4l7JoWjVdeh&#39;,&#39;resolve&#39;)">Resolve</button></div></div></div>
    </div>
    <div class="card">
      <h2>Sensor Network</h2>
      <table id="sensors"><thead><tr><th></th><th>Sensor</th><th>Site</th><th>ppm</th><th>Battery</th></tr></thead><tbody><tr><td><span class="status-dot dot-alert"></span></td><td>Compressor Sta. 4</td><td>Pichanur Compressor Station</td><td>5.91</td><td>78%</td></tr><tr><td><span class="status-dot dot-alert"></span></td><td>Pipeline Jct. 9B</td><td>Pichanur Compressor Station</td><td>12.13</td><td>40%</td></tr><tr><td><span class="status-dot dot-watch"></span></td><td>Pipeline Jct. 14</td><td>Coimbatore North Refinery</td><td>2.97</td><td>99%</td></tr><tr><td><span class="status-dot dot-alert"></span></td><td>Valve Cluster V-7</td><td>Pichanur Compressor Station</td><td>7.07</td><td>45%</td></tr><tr><td><span class="status-dot dot-watch"></span></td><td>Separator S-6</td><td>Coimbatore North Refinery</td><td>3</td><td>90%</td></tr><tr><td><span class="status-dot dot-alert"></span></td><td>Wellhead B-05</td><td>Perur Storage Terminal</td><td>29.59</td><td>65%</td></tr><tr><td><span class="status-dot dot-alert"></span></td><td>Storage Tank T-3</td><td>Perur Storage Terminal</td><td>9.93</td><td>62%</td></tr><tr><td><span class="status-dot dot-alert"></span></td><td>Wellhead A-12</td><td>Pichanur Compressor Station</td><td>18.21</td><td>68%</td></tr><tr><td><span class="status-dot dot-alert"></span></td><td>Metering Sta. 2</td><td>Pichanur Compressor Station</td><td>10.25</td><td>54%</td></tr><tr><td><span class="status-dot dot-alert"></span></td><td>Flare Stack F-2</td><td>Pichanur Compressor Station</td><td>22.12</td><td>60%</td></tr></tbody></table>
    </div>
  </div>
</main>

<script src="./TerraCarbon — Live Ops_files/leaflet.js.download"></script>
<script>
var SITE_COORDS = {
  "Pichanur Compressor Station": [10.9601, 76.8998],
  "Coimbatore North Refinery":   [11.0510, 76.9910],
  "Perur Storage Terminal":      [10.9420, 76.9200]
};

var map = L.map('map', { scrollWheelZoom: false }).setView([11.0, 77.0], 11);
L.tileLayer('https://{s}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}{r}.png', {
  attribution: 'OpenStreetMap, CARTO',
  maxZoom: 12
}).addTo(map);

var siteMarkers = {};

function colorForSeverity(sev) {
  if (sev === 'crit') return '#f85149';
  if (sev === 'warn') return '#d29922';
  return '#3fb950';
}

async function j(path, opts) {
  const r = await fetch(path, opts);
  return r.json();
}

function sevClass(sev) {
  if (sev === 'crit') return 'sev-crit';
  if (sev === 'warn') return 'sev-warn';
  return 'sev-info';
}

function updateMap(alerts, sensors) {
  var siteSeverity = {};
  alerts.filter(function(a){ return a.status !== 'resolved'; }).forEach(function(a){
    var s = a.site;
    var rank = { crit: 3, warn: 2, info: 1 }[a.sev] || 1;
    var current = { crit: 3, warn: 2, info: 1 }[siteSeverity[s]] || 0;
    if (rank > current) siteSeverity[s] = a.sev;
  });

  var sensorCountBySite = {};
  sensors.forEach(function(s){
    sensorCountBySite[s.site] = (sensorCountBySite[s.site] || 0) + 1;
  });

  Object.keys(SITE_COORDS).forEach(function(name) {
    var coord = SITE_COORDS[name];
    var sev = siteSeverity[name];
    var color = sev ? colorForSeverity(sev) : '#3fb950';
    var count = sensorCountBySite[name] || 0;
    var label = sev ? ('Active ' + sev.toUpperCase() + ' alert') : 'Normal';

    if (siteMarkers[name]) {
      siteMarkers[name].setStyle({ color: color, fillColor: color });
      siteMarkers[name].setPopupContent('<b>' + name + '</b><br>' + label + '<br>' + count + ' sensors');
    } else {
      var marker = L.circleMarker(coord, {
        radius: 10, color: color, fillColor: color, fillOpacity: 0.7, weight: 2
      }).addTo(map);
      marker.bindPopup('<b>' + name + '</b><br>' + label + '<br>' + count + ' sensors');
      siteMarkers[name] = marker;
    }
  });
}

async function refresh() {
  try {
    const kpis = await j('/dashboard/kpis');
    document.getElementById('kpis').innerHTML =
      '<div class="kpi"><div class="val">' + kpis.active_alerts + '</div><div class="label">Active Alerts</div></div>' +
      '<div class="kpi"><div class="val">' + kpis.avg_reading_ppm + '</div><div class="label">Avg ppm</div></div>' +
      '<div class="kpi"><div class="val">' + kpis.sensors_online + '/' + kpis.sensors_total + '</div><div class="label">Sensors Online</div></div>' +
      '<div class="kpi"><div class="val">' + kpis.satellite_passes_today + '</div><div class="label">Satellite Passes</div></div>';

    const alerts = await j('/alerts');
    const sensors = await j('/sensors');

    updateMap(alerts, sensors);

    const active = alerts.filter(function(a){ return a.status !== 'resolved'; });
    document.getElementById('alerts').innerHTML = active.length ? active.map(function(a) {
      return '<div style="border-bottom:1px solid #21262d; padding:10px 0;">' +
        '<div><span class="' + sevClass(a.sev) + '">[' + (a.sev||'info').toUpperCase() + ']</span> ' + (a.title || a.desc || 'Alert') +
          ' <span class="badge ' + a.status + '">' + a.status + '</span></div>' +
        '<div style="color:#8b949e; font-size:12px; margin-top:2px;">' + (a.site || '') + (a.desc ? ' · ' + a.desc : '') + '</div>' +
        (a.precaution_measures ? '<div class="precaution">' + a.precaution_measures + '</div>' : '') +
        '<div style="margin-top:8px;">' +
          (a.status === 'active' ? '<button onclick="act(\'' + a.id + '\',\'acknowledge\')">Acknowledge</button>' : '') +
          (a.status !== 'resolved' ? '<button onclick="act(\'' + a.id + '\',\'resolve\')">Resolve</button>' : '') +
        '</div></div>';
    }).join('') : '<p style="color:#8b949e;">No active alerts.</p>';

    document.querySelector('#sensors tbody').innerHTML = sensors.map(function(s) {
      return '<tr><td><span class="status-dot dot-' + (s.status||'normal') + '"></span></td>' +
      '<td>' + s.name + '</td><td>' + s.site + '</td><td>' + s.reading_ppm + '</td><td>' + s.battery_pct + '%</td></tr>';
    }).join('');
  } catch (e) {
    console.error('refresh failed', e);
  }
}

async function act(id, action) {
  await j('/alerts/' + id + '/' + action, { method: 'POST' });
  refresh();
}

refresh();
setInterval(refresh, 5000);
</script>


</body></html>[TerraCarbon — Live Ops (1).html](https://github.com/user-attachments/files/32387044/TerraCarbon.Live.Ops.1.html)
