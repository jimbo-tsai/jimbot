---
title: "The Outer Wilds Ventures Log"
---

<style>
  /* Seamlessly transitions the entire layout over 0.8 seconds */
  body, #starCanvas, header, .header, .site-header, h1, h2, h3, p, li, table, th, td, blockquote, .solar-system-wrapper {
      transition: background-color 0.8s ease, color 0.8s ease, filter 0.8s ease, border-color 0.8s ease, opacity 0.8s ease !important;
  }

  /* Timber Hearth / Nomai Surface State (Light Mode) */
  body {
      background-color: #fcf8f2 !important;
      color: #2b1a09 !important;
      margin: 0;
      padding: 0;
  }
  
  h1, h2, h3 {
      color: #a2e8ff !important; 
  }

  header, .header, .site-header {
      background-color: #f5eedf !important;
      color: #2b1a09 !important;
      border-bottom: 2px solid #d15a16;
  }

  /* Target state when scrolled past the 1/8 mark: Entering The Eye of the Universe */
  body.page-inverted {
      background-color: #0d0015 !important; /* --color-eye-vortex */
      color: #cee5e2 !important;
  }
  
  body.page-inverted h1, 
  body.page-inverted h2, 
  body.page-inverted h3 {
      color: #a0e0ff !important; /* --color-eye-lightning */
  }
  
  body.page-inverted p, 
  body.page-inverted li, 
  body.page-inverted table, 
  body.page-inverted th, 
  body.page-inverted td, 
  body.page-inverted blockquote {
      color: #cee5e2 !important;
  }

  /* REVERSE THE HEADER */
  body.page-inverted header,
  body.page-inverted .header,
  body.page-inverted .site-header {
      background-color: #0f131f !important;
      color: #a0e0ff !important; /* --color-eye-lightning */
      border-bottom: 2px solid #a0e0ff;
  }
  
  /* FIXED CANVAS FILTER */
  body.page-inverted #starCanvas {
      filter: invert(1) hue-rotate(340deg) !important;
  }

  /* ==================================================
     COMPILED TRUE-SCALE HEARTHIAN SOLAR SYSTEM SYSTEM
     ================================================== */

  .solar-system-wrapper {
      width: 100%;
      height: 1100px; 
      display: flex;
      justify-content: center;
      align-items: center;
      background: transparent !important;
      margin-top: -250px;
      position: relative;
      overflow: hidden;
  }

  .solar-syst {
      margin: 0 auto;
      width: 100%;
      height: 100%;
      position: relative;
      z-index: 2;
      background: transparent !important;
  }

  /* Primary Orbital Ring Containers */
  .hourglass-twins, .timber-hearth, .brittle-hollow, .the-interloper, .giants-deep, .dark-bramble {
      border-radius: 1000px;
      top: 50%;
      left: 50%;
      position: absolute;
      border: 1px solid rgba(97, 242, 213, 0.12) !important;
      background: transparent !important;
  }

  /* ─── THE SUN ───────────────────────────────────────────────────────────────
     Subgiant → Red Giant gradient using --color-sun-glow / --color-sun-main /
     --color-sun-giant. Box-shadow echoes those same two outer phases.
  ─────────────────────────────────────────────────────────────────────────── */
  .sun {
      position: absolute;
      top: 50%;
      left: 50%;
      border-radius: 50%;
      background: radial-gradient(
          circle at center,
          #ffffff   0%,    /* white-hot core               */
          #ffd700  20%,    /* --color-sun-glow  (corona)   */
          #ff8c00  50%,    /* --color-sun-main  (surface)  */
          #ff3300  80%,    /* --color-sun-giant (edge/halo)*/
          #4c0519 100%     /* deep shadow limb             */
      );
      height: 64px;
      width: 64px;
      margin-top: -32px;
      margin-left: -32px;
      border: 0 !important;
      /* glow: sun-main warm amber + sun-giant red expansion */
      box-shadow: 0 0 30px 10px rgba(255, 140, 0, 0.7),
                  0 0 60px 20px rgba(255,  51, 0, 0.4);
      z-index: 100;
  }

  /* ─── HOURGLASS TWINS ───────────────────────────────────────────────────── */
  .hourglass-twins {
      height: 180px;
      width: 180px;
      margin-top: -90px;
      margin-left: -90px;
      animation: orb 11.076s linear infinite;
  }

  .twins-local-orbit {
      position: absolute;
      top: 0 !important;       
      left: 50% !important;
      height: 54px;            
      width: 54px;
      margin-top: -27px;
      margin-left: -27px;
      animation: orb 2.5s linear infinite; 
      border: 1px solid rgba(97, 242, 213, 0.15) !important;
      border-radius: 50%;
  }
  
  /* Ash Twin — sand-white surface (#e5d3b3) with dark ash-grey core overlay
     (#3a3a3a). Strata lines also use core grey for consistency.
  */
  .ash-twin-body {
      position: absolute;
      top: 0;
      left: 50%;
      width: 13px;
      height: 13px;
      transform: translate(-50%, -50%);
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'%3E%3Ccircle cx='10' cy='10' r='10' fill='%23e5d3b3'/%3E%3Cpath d='M2,10 Q10,13 18,10 Q10,7 2,10' fill='%233a3a3a' opacity='0.4'/%3E%3Cpath d='M5,10 L7,8 L9,10 L11,7 L13,10' stroke='%233a3a3a' stroke-width='0.6' fill='none' opacity='0.5'/%3E%3C/svg%3E");
      background-size: contain;
  }
  
  /* Ember Twin — burnt ochre canyon rock (#a04020) body with shadowed ravine
     stone (#6b2b15) and a warm ember-glow highlight (#ff8c00).
  */
  .ember-twin-body {
      position: absolute;
      bottom: 0;
      left: 50%;
      width: 13px;
      height: 13px;
      transform: translate(-50%, -50%);
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'%3E%3Ccircle cx='10' cy='10' r='10' fill='%23a04020'/%3E%3Cpath d='M3,6 L7,5 L5,12 L2,9 Z M11,13 L17,11 L14,16 L10,14 Z' fill='%236b2b15' opacity='0.6'/%3E%3Ccircle cx='13' cy='6' r='1.5' fill='%23ff8c00' opacity='0.4'/%3E%3C/svg%3E");
      background-size: contain;
  }

  /* ─── TIMBER HEARTH ─────────────────────────────────────────────────────── */
  .timber-hearth {
      height: 310px;
      width: 310px;
      margin-top: -155px;
      margin-left: -155px;
      animation: orb 25.025s linear infinite;
  }

  /* Timber Hearth — Hearthian pine forests (#2a5a3b) over a deep freshwater
     ocean (#3b6e8c). Polar ice caps and cloud streak remain white.
  */
  .timber-hearth-body {
      position: absolute;
      top: 0;
      left: 50%;
      width: 26px;
      height: 26px;
      transform: translate(-50%, -50%);
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 40 40'%3E%3Ccircle cx='20' cy='20' r='20' fill='%233b6e8c'/%3E%3Cpath d='M12,10 C16,8 22,12 20,18 C18,24 12,28 8,24 C4,20 8,12 12,10 Z M28,15 C32,12 36,18 34,24 C32,30 26,32 24,26 C22,20 24,18 28,15 Z M15,30 C20,32 25,28 22,24 C19,20 12,25 15,30 Z' fill='%232a5a3b'/%3E%3Ccircle cx='20' cy='2' r='4' fill='%23f8fafc' opacity='0.7'/%3E%3Ccircle cx='20' cy='38' r='3' fill='%23f8fafc' opacity='0.7'/%3E%3Cpath d='M6,16 Q15,8 28,12 T36,28' stroke='%23ffffff' stroke-width='2' fill='none' opacity='0.5' stroke-linecap='round'/%3E%3C/svg%3E");
      background-size: contain;
  }

  .attlerock-orbit {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 50px;
      height: 50px;
      margin-top: -25px;
      margin-left: -25px;
      animation: orb 6.2s linear infinite;
      border-radius: 50%;
  }

  /* Attlerock — barren dusty lunar-grey regolith (#8e8e93) with darker
     crater shadows (#3a3a3a).
  */
  .attlerock-body {
      position: absolute;
      top: 0;
      left: 50%;
      width: 8px;
      height: 8px;
      transform: translate(-50%, -50%);
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'%3E%3Ccircle cx='10' cy='10' r='10' fill='%238e8e93'/%3E%3Ccircle cx='6' cy='7' r='2' fill='%233a3a3a' opacity='0.5'/%3E%3Ccircle cx='13' cy='14' r='2.5' fill='%233a3a3a' opacity='0.5'/%3E%3C/svg%3E");
      background-size: contain;
  }

  /* ─── BRITTLE HOLLOW ────────────────────────────────────────────────────── */
  .brittle-hollow {
      height: 450px;
      width: 450px;
      margin-top: -225px;
      margin-left: -225px;
      animation: orb 39.794s linear infinite;
  }

  /* Brittle Hollow — fractured crust (#3c2d42) surrounds the black-hole
     singularity void (#120024). Crust fragment shards share the crust colour.
  */
  .brittle-hollow-body {
      position: absolute;
      top: 0;
      left: 50%;
      width: 28px;
      height: 28px;
      transform: translate(-50%, -50%);
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 40 40'%3E%3Ccircle cx='20' cy='20' r='20' fill='%23000000'/%3E%3Ccircle cx='20' cy='20' r='16' fill='%233c2d42' opacity='0.8'/%3E%3Ccircle cx='20' cy='20' r='10' fill='%23120024'/%3E%3Cpath d='M5,12 L12,7 L15,14 L7,17 Z M28,6 L35,11 L31,18 L24,13 Z M12,28 L19,34 L27,31 L21,24 Z M30,26 L34,32 L28,35 Z' fill='%233c2d42' stroke='%234d3d5c' stroke-width='1'/%3E%3C/svg%3E");
      background-size: contain;
  }

  .hollows-lantern-orbit {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 56px;
      height: 56px;
      margin-top: -28px;
      margin-left: -28px;
      animation: orb 4.1s linear infinite;
      border-radius: 50%;
  }

  /* Hollow's Lantern — volcanic obsidian surface (#1c1c1c) with blazing
     basaltic magma pools (#ff4500) and an orange-red secondary lava glow.
  */
  .hollows-lantern-body {
      position: absolute;
      top: 0;
      left: 50%;
      width: 9px;
      height: 9px;
      transform: translate(-50%, -50%);
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'%3E%3Ccircle cx='10' cy='10' r='10' fill='%231c1c1c'/%3E%3Ccircle cx='7' cy='11' r='3' fill='%23ff4500'/%3E%3Ccircle cx='14' cy='6' r='2' fill='%23ff8c00'/%3E%3C/svg%3E");
      background-size: contain;
  }

  /* ─── THE INTERLOPER ────────────────────────────────────────────────────── */
  .the-interloper {
      height: 560px;
      width: 560px;
      margin-top: -410px; 
      margin-left: -120px; 
      animation: orb 47.781s linear infinite;
  }

  /* The Interloper — ice-blue-white nucleus (#e0faff) with a pale stardust
     cyan vapour trail (#a5d6e1) fading into deep space.
  */
  .interloper-body {
      position: absolute;
      top: 0;
      left: 50%;
      height: 80px;
      width: 40px;
      margin-top: -60px;
      margin-left: -20px;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 40 80'%3E%3Cdefs%3E%3ClinearGradient id='tail' x1='0%25' y1='100%25' x2='0%25' y2='0%25'%3E%3Cstop offset='0%25' stop-color='%23e0faff' stop-opacity='0.9'/%3E%3Cstop offset='20%25' stop-color='%23a5d6e1' stop-opacity='0.6'/%3E%3Cstop offset='60%25' stop-color='%230284c7' stop-opacity='0.2'/%3E%3Cstop offset='100%25' stop-color='%230f172a' stop-opacity='0'/%3E%3C/linearGradient%3E%3CradialGradient id='glow' cx='50%25' cy='50%25' r='50%25'%3E%3Cstop offset='0%25' stop-color='%23e0faff'/%3E%3Cstop offset='50%25' stop-color='%23a5d6e1' stop-opacity='1'/%3E%3Cstop offset='100%25' stop-color='%23a5d6e1' stop-opacity='0'/%3E%3C/radialGradient%3E%3C/defs%3E%3Cpath d='M16,60 L4,0 Q20,18 36,0 L24,60 Z' fill='url(%23tail)'/%3E%3Ccircle cx='20' cy='60' r='5' fill='url(%23glow)'/%3E%3C/svg%3E");
      background-size: contain;
      background-repeat: no-repeat;
  }

  /* ─── GIANT'S DEEP ──────────────────────────────────────────────────────── */
  .giants-deep {
      height: 680px;
      width: 680px;
      margin-top: -340px;
      margin-left: -340px;
      animation: orb 66.142s linear infinite;
  }

  /* Giant's Deep — heavy sub-surface ocean (#004f53) base, swirling jade-green
     cloud layer (#228b75) outer arc, and seafoam cyclone streams (#56a895)
     inner vortex and storm-eye circles.
  */
  .giants-deep-body {
      position: absolute;
      top: 0;
      left: 50%;
      width: 38px;
      height: 38px;
      transform: translate(-50%, -50%);
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 60 60'%3E%3Ccircle cx='30' cy='30' r='30' fill='%23004f53'/%3E%3Cpath d='M30,5 A25,25 0 1,0 55,30' stroke='%23228b75' stroke-width='4' fill='none' opacity='0.7' stroke-linecap='round'/%3E%3Cpath d='M10,30 A20,20 0 1,1 30,50' stroke='%2356a895' stroke-width='5' fill='none' opacity='0.6' stroke-linecap='round'/%3E%3Ccircle cx='22' cy='18' r='5' fill='%2356a895' opacity='0.8'/%3E%3Ccircle cx='42' cy='38' r='6' fill='%2356a895' opacity='0.8'/%3E%3C/svg%3E");
      background-size: contain;
  }

  /* ─── DARK BRAMBLE ──────────────────────────────────────────────────────── */
  .dark-bramble {
      height: 890px;
      width: 890px;
      margin-top: -445px;
      margin-left: -445px;
      animation: orb 87.516s linear infinite;
  }

  /* Dark Bramble — thick misty fog (#acaeab) radial shroud over gnarled dark
     bark-brown vines (#3e3129). The central node nest glows with a menacing
     deep red hint (#110000). Shard fragments use the vine palette.
  */
  .dark-bramble-body {
      position: absolute;
      top: 0;
      left: 50%;
      height: 84px;
      width: 84px;
      margin-top: -42px;
      margin-left: -42px;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Cdefs%3E%3CradialGradient id='fog' cx='50%25' cy='50%25' r='50%25'%3E%3Cstop offset='0%25' stop-color='%23ffffff' stop-opacity='1'/%3E%3Cstop offset='25%25' stop-color='%23acaeab' stop-opacity='0.6'/%3E%3Cstop offset='60%25' stop-color='%233e3129' stop-opacity='0.3'/%3E%3Cstop offset='100%25' stop-color='%230f172a' stop-opacity='0'/%3E%3C/radialGradient%3E%3C/defs%3E%3Ccircle cx='50' cy='50' r='45' fill='url(%23fog)'/%3E%3Ccircle cx='50' cy='50' r='10' fill='%23110000' stroke='%233e3129' stroke-width='1.5'/%3E%3Cpath d='M22,48 Q42,32 52,52 T82,48' stroke='%233e3129' stroke-width='2' fill='none' stroke-linecap='round'/%3E%3Cpath d='M48,12 Q54,36 44,62 T32,88' stroke='%232e2420' stroke-width='1.8' fill='none' stroke-linecap='round'/%3E%3Cpath d='M12,56 Q48,52 86,46' stroke='%233e3129' stroke-width='1.5' fill='none' stroke-linecap='round'/%3E%3Cpath d='M32,41 Q28,26 22,22' stroke='%233e3129' stroke-width='1' fill='none' stroke-linecap='round'/%3E%3Cpath d='M42,44 Q46,30 58,26' stroke='%233e3129' stroke-width='1.2' fill='none' stroke-linecap='round'/%3E%3Cpath d='M56,50 Q62,66 70,76' stroke='%233e3129' stroke-width='1.2' fill='none' stroke-linecap='round'/%3E%3Cpath d='M50,26 Q66,24 74,16' stroke='%232e2420' stroke-width='1' fill='none' stroke-linecap='round'/%3E%3Cpath d='M46,46 Q28,52 22,64' stroke='%232e2420' stroke-width='1.1' fill='none' stroke-linecap='round'/%3E%3Cpath d='M42,68 Q54,78 64,86' stroke='%232e2420' stroke-width='1' fill='none' stroke-linecap='round'/%3E%3Cpolygon points='23,34 34,25 32,40 19,37' fill='%233e3129' stroke='%231a100c' stroke-width='0.6'/%3E%3Cpolygon points='72,24 86,29 78,44 64,35' fill='%232e2420' stroke='%230f172a' stroke-width='0.6'/%3E%3Cpolygon points='17,68 31,60 28,74 14,72' fill='%232e2420' stroke='%230f172a' stroke-width='0.6'/%3E%3Cpolygon points='65,74 81,66 74,82 60,78' fill='%233e3129' stroke='%231a100c' stroke-width='0.6'/%3E%3Cpolygon points='45,18 55,12 52,22 42,20' fill='%232e2420' stroke='%230f172a' stroke-width='0.5'/%3E%3Cpolygon points='82,50 92,54 86,62 78,56' fill='%233e3129' stroke='%231a100c' stroke-width='0.5'/%3E%3Cpolygon points='48,82 58,88 52,94 42,88' fill='%232e2420' stroke='%230f172a' stroke-width='0.5'/%3E%3Cpolygon points='12,44 22,40 18,52 8,48' fill='%233e3129' stroke='%231a100c' stroke-width='0.5'/%3E%3Cpolygon points='35,68 42,62 46,70 38,74' fill='%232e2420' stroke='%230f172a' stroke-width='0.5'/%3E%3C/svg%3E");
      background-size: contain;
      background-repeat: no-repeat;
      z-index: 5;
  }

  /* Structural Normalizer across child nodes */
  .solar-syst div[class$="-body"], 
  .solar-syst div[class$="-orbit"] {
      border: none;
  }

  /* Core Orbital Motion */
  @keyframes orb {
      from { transform: rotate(0deg); }
      to   { transform: rotate(-360deg); }
  }
</style>

<script>
(function() {
    const checkScroll = (e) => {
        const target = (e && e.target && e.target.scrollHeight) ? e.target : (document.scrollingElement || document.documentElement);
        
        const scrollTop = target.scrollTop;
        const maxScroll = target.scrollHeight - target.clientHeight;
        
        if (maxScroll <= 0) return;

        if ((scrollTop / maxScroll) >= 0.125) {
            document.body.classList.add('page-inverted');
        } else {
            document.body.classList.remove('page-inverted');
        }
    };

    window.addEventListener('scroll', checkScroll, true);
    window.addEventListener('DOMContentLoaded', () => setTimeout(checkScroll, 100));
})();
</script>

<div style="height: 20000px;"></div>

<div class="solar-system-wrapper">
  <div class="solar-syst">
    <div class="sun"></div>
    
<div class="hourglass-twins">
<div class="twins-local-orbit">
    <div class="ash-twin-body"></div>
    <div class="ember-twin-body"></div>
</div>
</div>

<div class="timber-hearth">
<div class="timber-hearth-body">
    <div class="attlerock-orbit">
        <div class="attlerock-body"></div>
    </div>
</div>
</div>

<div class="brittle-hollow">
<div class="brittle-hollow-body">
    <div class="hollows-lantern-orbit">
        <div class="hollows-lantern-body"></div>
    </div>
</div>
</div>

<div class="the-interloper">
<div class="interloper-body"></div>
</div>

<div class="giants-deep">
<div class="giants-deep-body"></div>
</div>

<div class="dark-bramble">
<div class="dark-bramble-body"></div>
</div>
</div>
</div>

