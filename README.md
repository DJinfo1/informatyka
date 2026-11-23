[index.html](https://github.com/user-attachments/files/35291577/index.html)
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
  <title>КодТест — Контрольний тест з інформатики (8 клас)</title>
  <style>
    :root {
      --bg: #f8fafc;
      --surface: #ffffff;
      --text: #0f172a;
      --muted: #475569;
      --border: #e2e8f0;
      --sky: #0284c7;
      --sky-dark: #0369a1;
      --sky-soft: #f0f9ff;
      --emerald: #059669;
      --emerald-soft: #ecfdf5;
      --red: #dc2626;
      --red-soft: #fef2f2;
      --amber: #d97706;
      --amber-soft: #fffbeb;
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
    }
    .topbar {
      position: sticky;
      top: 0;
      z-index: 20;
      background: rgba(255, 255, 255, 0.95);
      backdrop-filter: blur(8px);
      border-bottom: 1px solid var(--border);
      padding: 12px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
    }
    .brand {
      font-weight: 800;
      font-size: 18px;
      letter-spacing: -0.02em;
    }
    .status-line {
      font-size: 13px;
      font-weight: 600;
      color: var(--muted);
      display: flex;
      align-items: center;
      gap: 14px;
      font-variant-numeric: tabular-nums;
    }
    .container {
      max-width: 760px;
      margin: 24px auto 96px;
      padding: 0 16px;
    }
    .card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 18px;
      padding: 28px;
    }
    .kicker {
      font-size: 12px;
      font-weight: 600;
      color: var(--sky-dark);
      margin: 0 0 8px;
    }
    h1 {
      font-size: 24px;
      line-height: 1.25;
      margin: 0 0 12px;
      font-weight: 800;
    }
    h2 {
      font-size: 19px;
      line-height: 1.35;
      margin: 0 0 16px;
      font-weight: 700;
    }
    p.desc {
      color: var(--muted);
      font-size: 15px;
      margin: 0 0 20px;
    }
    .grid-2 {
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 12px;
      margin-bottom: 16px;
    }
    @media (max-width: 600px) {
      .grid-2 { grid-template-columns: 1fr; }
      .card { padding: 20px; }
      h1 { font-size: 21px; }
      h2 { font-size: 17px; }
    }
    label.field-label {
      display: block;
      font-size: 12px;
      font-weight: 700;
      color: #334155;
      margin-bottom: 6px;
    }
    input[type="text"], textarea {
      width: 100%;
      padding: 12px 14px;
      font-size: 15px;
      font-family: inherit;
      border: 1px solid #cbd5e1;
      border-radius: 12px;
      background: #f8fafc;
      color: var(--text);
      outline: none;
    }
    input[type="text"]:focus, textarea:focus {
      border-color: var(--sky);
      background: #ffffff;
      box-shadow: 0 0 0 3px rgba(2, 132, 199, 0.14);
    }
    .rules-box {
      background: var(--amber-soft);
      border: 1px solid #fde68a;
      border-radius: 14px;
      padding: 16px 18px;
      margin: 16px 0 20px;
      font-size: 13px;
      color: #78350f;
    }
    .rules-box strong { display: block; margin-bottom: 6px; font-size: 14px; }
    .rules-box ul { margin: 0; padding-left: 18px; }
    .rules-box li { margin-bottom: 4px; }
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      min-height: 48px;
      padding: 12px 22px;
      border-radius: 12px;
      border: 1px solid transparent;
      font-size: 15px;
      font-weight: 700;
      font-family: inherit;
      cursor: pointer;
      transition: background 0.15s ease, transform 0.1s ease;
    }
    .btn:active { transform: scale(0.99); }
    .btn:disabled { opacity: 0.45; cursor: not-allowed; }
    .btn-primary { background: var(--sky); color: #fff; }
    .btn-primary:hover:not(:disabled) { background: var(--sky-dark); }
    .btn-success { background: var(--emerald); color: #fff; }
    .btn-success:hover:not(:disabled) { background: #047857; }
    .btn-secondary { background: #f1f5f9; color: #1e293b; border-color: #cbd5e1; }
    .btn-secondary:hover:not(:disabled) { background: #e2e8f0; }
    .btn-full { width: 100%; }
    .btn-sm {
      min-height: 42px;
      padding: 8px 14px;
      font-size: 13px;
      white-space: nowrap;
    }

    /* QR Code Card */
    .qr-card {
      background: #f1f5f9;
      border: 1px solid #cbd5e1;
      border-radius: 14px;
      padding: 16px;
      margin-bottom: 20px;
      text-align: center;
    }
    .qr-header {
      display: flex;
      align-items: center;
      gap: 12px;
      text-align: left;
      margin-bottom: 10px;
    }
    .qr-box {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: #ffffff;
      padding: 10px;
      border-radius: 12px;
      border: 1px solid var(--border);
      box-shadow: 0 2px 8px rgba(0,0,0,0.04);
      margin: 6px auto 12px;
      max-width: 220px;
    }
    .qr-box svg {
      width: 100%;
      height: auto;
      max-width: 180px;
      display: block;
    }
    .qr-input-row {
      display: flex;
      gap: 8px;
      align-items: center;
      max-width: 520px;
      margin: 0 auto;
    }
    .qr-hint {
      font-size: 12px;
      color: var(--muted);
      margin: 8px 0 0;
      line-height: 1.4;
    }

    /* Modal Overlay */
    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(15, 23, 42, 0.75);
      backdrop-filter: blur(4px);
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 16px;
    }
    .modal-card {
      background: #ffffff;
      border-radius: 18px;
      max-width: 480px;
      width: 100%;
      padding: 22px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.25);
      border: 2px solid var(--amber);
      animation: popIn 0.2s ease-out;
      text-align: left;
    }
    @keyframes popIn {
      from { transform: scale(0.93); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }
    .modal-badge {
      display: inline-block;
      background: var(--amber-soft);
      color: #92400e;
      font-weight: 800;
      font-size: 12px;
      padding: 4px 10px;
      border-radius: 8px;
      border: 1px solid #fde68a;
      letter-spacing: 0.04em;
    }
    .modal-rule-note {
      background: #fef2f2;
      border: 1px solid #fecaca;
      border-radius: 10px;
      padding: 12px;
      font-size: 13px;
      color: #991b1b;
      margin-top: 12px;
      line-height: 1.45;
    }

    .progress-bar {
      width: 100%;
      height: 5px;
      background: #e2e8f0;
      border-radius: 99px;
      overflow: hidden;
      margin-bottom: 18px;
    }
    .progress-fill {
      height: 100%;
      background: var(--sky);
      transition: width 0.2s ease;
    }
    .options-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
      user-select: none;
    }
    .option-btn {
      width: 100%;
      min-height: 52px;
      padding: 14px 16px;
      text-align: left;
      background: #fff;
      border: 1px solid #cbd5e1;
      border-radius: 12px;
      display: flex;
      align-items: flex-start;
      gap: 12px;
      cursor: pointer;
      font-size: 15px;
      font-family: inherit;
      color: #1e293b;
      transition: all 0.12s ease;
    }
    .option-btn:hover { background: #f8fafc; }
    .option-btn.selected {
      background: var(--sky-soft);
      border-color: var(--sky);
      color: #0f172a;
      font-weight: 600;
    }
    .option-letter {
      width: 28px;
      height: 28px;
      border-radius: 8px;
      border: 1px solid #cbd5e1;
      background: #f8fafc;
      color: #475569;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-family: ui-monospace, monospace;
      font-size: 13px;
      font-weight: 700;
      flex-shrink: 0;
    }
    .option-btn.selected .option-letter {
      background: var(--sky);
      border-color: var(--sky);
      color: #fff;
    }
    .open-part {
      background: #f8fafc;
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 14px;
      margin-bottom: 12px;
    }
    .open-part label {
      display: block;
      font-size: 13px;
      font-weight: 700;
      margin-bottom: 8px;
      color: #1e293b;
    }
    .bottom-nav {
      position: fixed;
      bottom: 0;
      left: 0;
      right: 0;
      z-index: 20;
      background: rgba(255, 255, 255, 0.96);
      backdrop-filter: blur(8px);
      border-top: 1px solid var(--border);
      padding: 12px 16px;
    }
    .bottom-nav-inner {
      max-width: 760px;
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
    }
    .map-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 16px;
      padding-top: 16px;
      border-top: 1px solid #f1f5f9;
    }
    .map-dot {
      width: 36px;
      height: 36px;
      border-radius: 9px;
      border: 1px solid #cbd5e1;
      background: #f8fafc;
      font-family: ui-monospace, monospace;
      font-weight: 700;
      font-size: 13px;
      cursor: pointer;
    }
    .map-dot.answered { background: var(--emerald-soft); border-color: #6ee7b7; color: #065f46; }
    .map-dot.current { background: var(--sky); border-color: var(--sky); color: #fff; }
    .alert-banner {
      background: var(--amber-soft);
      border: 1px solid #fcd34d;
      color: #78350f;
      border-radius: 12px;
      padding: 12px 14px;
      font-size: 13px;
      font-weight: 600;
      margin-bottom: 14px;
    }
    .annul-card {
      border-color: #fecaca;
      text-align: center;
    }
    .big-score {
      font-size: 40px;
      font-weight: 800;
      font-family: ui-monospace, monospace;
      margin: 12px 0;
      font-variant-numeric: tabular-nums;
    }
    .score-red { color: var(--red); }
    .score-green { color: var(--emerald); }
    .summary-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      background: #f8fafc;
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 16px;
      text-align: left;
      margin: 18px 0;
    }
    .err-msg { color: var(--red); font-size: 13px; font-weight: 600; margin: 8px 0 0; }
    canvas#fireworks {
      position: fixed;
      inset: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 50;
    }
    .hidden { display: none !important; }
  </style>
  <script>
  var qrcode=function(){function i(t,r){function a(t,r){g=function(t){for(var r=new Array(t),e=0;e<t;e+=1){r[e]=new Array(t);for(var n=0;n<t;n+=1)r[e][n]=null}return r}(l=4*u+17),e(0,0),e(l-7,0),e(0,l-7),i(),o(),v(t,r),7<=u&&h(t),null==n&&(n=w(u,f,c)),d(n,r)}var u=t,f=y[r],g=null,l=0,n=null,c=[],s={},e=function(t,r){for(var e=-1;e<=7;e+=1)if(!(t+e<=-1||l<=t+e))for(var n=-1;n<=7;n+=1)r+n<=-1||l<=r+n||(g[t+e][r+n]=0<=e&&e<=6&&(0==n||6==n)||0<=n&&n<=6&&(0==e||6==e)||2<=e&&e<=4&&2<=n&&n<=4)},o=function(){for(var t=8;t<l-8;t+=1)null==g[t][6]&&(g[t][6]=t%2==0);for(var r=8;r<l-8;r+=1)null==g[6][r]&&(g[6][r]=r%2==0)},i=function(){for(var t=B.getPatternPosition(u),r=0;r<t.length;r+=1)for(var e=0;e<t.length;e+=1){var n=t[r],o=t[e];if(null==g[n][o])for(var i=-2;i<=2;i+=1)for(var a=-2;a<=2;a+=1)g[n+i][o+a]=-2==i||2==i||-2==a||2==a||0==i&&0==a}},h=function(t){for(var r=B.getBCHTypeNumber(u),e=0;e<18;e+=1){var n=!t&&1==(r>>e&1);g[Math.floor(e/3)][e%3+l-8-3]=n}for(e=0;e<18;e+=1){n=!t&&1==(r>>e&1);g[e%3+l-8-3][Math.floor(e/3)]=n}},v=function(t,r){for(var e=f<<3|r,n=B.getBCHTypeInfo(e),o=0;o<15;o+=1){var i=!t&&1==(n>>o&1);o<6?g[o][8]=i:o<8?g[o+1][8]=i:g[l-15+o][8]=i}for(o=0;o<15;o+=1){i=!t&&1==(n>>o&1);o<8?g[8][l-o-1]=i:o<9?g[8][15-o-1+1]=i:g[8][15-o-1]=i}g[l-8][8]=!t},d=function(t,r){for(var e=-1,n=l-1,o=7,i=0,a=B.getMaskFunction(r),u=l-1;0<u;u-=2)for(6==u&&(u-=1);;){for(var f=0;f<2;f+=1)if(null==g[n][u-f]){var c=!1;i<t.length&&(c=1==(t[i]>>>o&1)),a(n,u-f)&&(c=!c),g[n][u-f]=c,-1==(o-=1)&&(i+=1,o=7)}if((n+=e)<0||l<=n){n-=e,e=-e;break}}},w=function(t,r,e){for(var n=b.getRSBlocks(t,r),o=M(),i=0;i<e.length;i+=1){var a=e[i];o.put(a.getMode(),4),o.put(a.getLength(),B.getLengthInBits(a.getMode(),t)),a.write(o)}var u=0;for(i=0;i<n.length;i+=1)u+=n[i].dataCount;if(o.getLengthInBits()>8*u)throw"code length overflow. ("+o.getLengthInBits()+">"+8*u+")";for(o.getLengthInBits()+4<=8*u&&o.put(0,4);o.getLengthInBits()%8!=0;)o.putBit(!1);for(;!(o.getLengthInBits()>=8*u||(o.put(236,8),o.getLengthInBits()>=8*u));)o.put(17,8);return function(t,r){for(var e=0,n=0,o=0,i=new Array(r.length),a=new Array(r.length),u=0;u<r.length;u+=1){var f=r[u].dataCount,c=r[u].totalCount-f;n=Math.max(n,f),o=Math.max(o,c),i[u]=new Array(f);for(var g=0;g<i[u].length;g+=1)i[u][g]=255&t.getBuffer()[g+e];e+=f;var l=B.getErrorCorrectPolynomial(c),h=C(i[u],l.getLength()-1).mod(l);a[u]=new Array(l.getLength()-1);for(g=0;g<a[u].length;g+=1){var s=g+h.getLength()-a[u].length;a[u][g]=0<=s?h.getAt(s):0}}var v=0;for(g=0;g<r.length;g+=1)v+=r[g].totalCount;var d=new Array(v),w=0;for(g=0;g<n;g+=1)for(u=0;u<r.length;u+=1)g<i[u].length&&(d[w]=i[u][g],w+=1);for(g=0;g<o;g+=1)for(u=0;u<r.length;u+=1)g<a[u].length&&(d[w]=a[u][g],w+=1);return d}(o,n)};s.addData=function(t,r){var e=null;switch(r=r||"Byte"){case"Numeric":e=x(t);break;case"Alphanumeric":e=m(t);break;case"Byte":e=L(t);break;case"Kanji":e=D(t);break;default:throw"mode:"+r}c.push(e),n=null},s.isDark=function(t,r){if(t<0||l<=t||r<0||l<=r)throw t+","+r;return g[t][r]},s.getModuleCount=function(){return l},s.make=function(){if(u<1){for(var t=1;t<40;t++){for(var r=b.getRSBlocks(t,f),e=M(),n=0;n<c.length;n++){var o=c[n];e.put(o.getMode(),4),e.put(o.getLength(),B.getLengthInBits(o.getMode(),t)),o.write(e)}var i=0;for(n=0;n<r.length;n++)i+=r[n].dataCount;if(e.getLengthInBits()<=8*i)break}u=t}a(!1,function(){for(var t=0,r=0,e=0;e<8;e+=1){a(!0,e);var n=B.getLostPoint(s);(0==e||n<t)&&(t=n,r=e)}return r}())},s.createTableTag=function(t,r){t=t||2;var e="";e+='<table style="',e+=" border-width: 0px; border-style: none;",e+=" border-collapse: collapse;",e+=" padding: 0px; margin: "+(r=void 0===r?4*t:r)+"px;",e+='">',e+="<tbody>";for(var n=0;n<s.getModuleCount();n+=1){e+="<tr>";for(var o=0;o<s.getModuleCount();o+=1)e+='<td style="',e+=" border-width: 0px; border-style: none;",e+=" border-collapse: collapse;",e+=" padding: 0px; margin: 0px;",e+=" width: "+t+"px;",e+=" height: "+t+"px;",e+=" background-color: ",e+=s.isDark(n,o)?"#000000":"#ffffff",e+=";",e+='"/>';e+="</tr>"}return e+="</tbody>",e+="</table>"},s.createSvgTag=function(t,r,e,n){var o={};"object"==typeof t&&(t=(o=t).cellSize,r=o.margin,e=o.alt,n=o.title),t=t||2,r=void 0===r?4*t:r,(e="string"==typeof e?{text:e}:e||{}).text=e.text||null,e.id=e.text?e.id||"qrcode-description":null,(n="string"==typeof n?{text:n}:n||{}).text=n.text||null,n.id=n.text?n.id||"qrcode-title":null;var i,a,u,f,c=s.getModuleCount()*t+2*r,g="";for(f="l"+t+",0 0,"+t+" -"+t+",0 0,-"+t+"z ",g+='<svg version="1.1" xmlns="http://www.w3.org/2000/svg"',g+=o.scalable?"":' width="'+c+'px" height="'+c+'px"',g+=' viewBox="0 0 '+c+" "+c+'" ',g+=' preserveAspectRatio="xMinYMin meet"',g+=n.text||e.text?' role="img" aria-labelledby="'+p([n.id,e.id].join(" ").trim())+'"':"",g+=">",g+=n.text?'<title id="'+p(n.id)+'">'+p(n.text)+"</title>":"",g+=e.text?'<description id="'+p(e.id)+'">'+p(e.text)+"</description>":"",g+='<rect width="100%" height="100%" fill="white" cx="0" cy="0"/>',g+='<path d="',a=0;a<s.getModuleCount();a+=1)for(u=a*t+r,i=0;i<s.getModuleCount();i+=1)s.isDark(a,i)&&(g+="M"+(i*t+r)+","+u+f);return g+='" stroke="transparent" fill="black"/>',g+="</svg>"},s.createDataURL=function(o,t){o=o||2,t=void 0===t?4*o:t;var r=s.getModuleCount()*o+2*t,i=t,a=r-t;return I(r,r,function(t,r){if(i<=t&&t<a&&i<=r&&r<a){var e=Math.floor((t-i)/o),n=Math.floor((r-i)/o);return s.isDark(n,e)?0:1}return 1})},s.createImgTag=function(t,r,e){t=t||2,r=void 0===r?4*t:r;var n=s.getModuleCount()*t+2*r,o="";return o+="<img",o+=' src="',o+=s.createDataURL(t,r),o+='"',o+=' width="',o+=n,o+='"',o+=' height="',o+=n,o+='"',e&&(o+=' alt="',o+=p(e),o+='"'),o+="/>"};var p=function(t){for(var r="",e=0;e<t.length;e+=1){var n=t.charAt(e);switch(n){case"<":r+="&lt;";break;case">":r+="&gt;";break;case"&":r+="&amp;";break;case'"':r+="&quot;";break;default:r+=n}}return r};return s.createASCII=function(t,r){if((t=t||1)<2)return function(t){t=void 0===t?2:t;var r,e,n,o,i,a=1*s.getModuleCount()+2*t,u=t,f=a-t,c={"--":"-","- ":"-"," -":"-","  ":" "},g={"--":"-","- ":"-"," -":" ","  ":" "},l="";for(r=0;r<a;r+=2){for(n=Math.floor((r-u)/1),o=Math.floor((r+1-u)/1),e=0;e<a;e+=1)i="-",u<=e&&e<f&&u<=r&&r<f&&s.isDark(n,Math.floor((e-u)/1))&&(i=" "),u<=e&&e<f&&u<=r+1&&r+1<f&&s.isDark(o,Math.floor((e-u)/1))?i+=" ":i+="-",l+=t<1&&f<=r+1?g[i]:c[i];l+="\n"}return a%2&&0<t?l.substring(0,l.length-a-1)+Array(1+a).join("-"):l.substring(0,l.length-1)}(r);t-=1,r=void 0===r?2*t:r;var e,n,o,i,a=s.getModuleCount()*t+2*r,u=r,f=a-r,c=Array(t+1).join("--"),g=Array(t+1).join("  "),l="",h="";for(e=0;e<a;e+=1){for(o=Math.floor((e-u)/t),h="",n=0;n<a;n+=1)i=1,u<=n&&n<f&&u<=e&&e<f&&s.isDark(o,Math.floor((n-u)/t))&&(i=0),h+=i?c:g;for(o=0;o<t;o+=1)l+=h+"\n"}return l.substring(0,l.length-1)},s.renderTo2dContext=function(t,r){r=r||2;for(var e=s.getModuleCount(),n=0;n<e;n++)for(var o=0;o<e;o++)t.fillStyle=s.isDark(n,o)?"black":"white",t.fillRect(n*r,o*r,r,r)},s}i.stringToBytes=(i.stringToBytesFuncs={default:function(t){for(var r=[],e=0;e<t.length;e+=1){var n=t.charCodeAt(e);r.push(255&n)}return r}}).default,i.createStringToBytes=function(u,f){var i=function(){function t(){var t=r.read();if(-1==t)throw"eof";return t}for(var r=S(u),e=0,n={};;){var o=r.read();if(-1==o)break;var i=t(),a=t()<<8|t();n[String.fromCharCode(o<<8|i)]=a,e+=1}if(e!=f)throw e+" != "+f;return n}(),a="?".charCodeAt(0);return function(t){for(var r=[],e=0;e<t.length;e+=1){var n=t.charCodeAt(e);if(n<128)r.push(n);else{var o=i[t.charAt(e)];"number"==typeof o?(255&o)==o?r.push(o):(r.push(o>>>8),r.push(255&o)):r.push(a)}}return r}};var r,t,a=1,u=2,o=4,f=8,y={L:1,M:0,Q:3,H:2},e=0,n=1,c=2,g=3,l=4,h=5,s=6,v=7,B=(r=[[],[6,18],[6,22],[6,26],[6,30],[6,34],[6,22,38],[6,24,42],[6,26,46],[6,28,50],[6,30,54],[6,32,58],[6,34,62],[6,26,46,66],[6,26,48,70],[6,26,50,74],[6,30,54,78],[6,30,56,82],[6,30,58,86],[6,34,62,90],[6,28,50,72,94],[6,26,50,74,98],[6,30,54,78,102],[6,28,54,80,106],[6,32,58,84,110],[6,30,58,86,114],[6,34,62,90,118],[6,26,50,74,98,122],[6,30,54,78,102,126],[6,26,52,78,104,130],[6,30,56,82,108,134],[6,34,60,86,112,138],[6,30,58,86,114,142],[6,34,62,90,118,146],[6,30,54,78,102,126,150],[6,24,50,76,102,128,154],[6,28,54,80,106,132,158],[6,32,58,84,110,136,162],[6,26,54,82,110,138,166],[6,30,58,86,114,142,170]],(t={}).getBCHTypeInfo=function(t){for(var r=t<<10;0<=d(r)-d(1335);)r^=1335<<d(r)-d(1335);return 21522^(t<<10|r)},t.getBCHTypeNumber=function(t){for(var r=t<<12;0<=d(r)-d(7973);)r^=7973<<d(r)-d(7973);return t<<12|r},t.getPatternPosition=function(t){return r[t-1]},t.getMaskFunction=function(t){switch(t){case e:return function(t,r){return(t+r)%2==0};case n:return function(t,r){return t%2==0};case c:return function(t,r){return r%3==0};case g:return function(t,r){return(t+r)%3==0};case l:return function(t,r){return(Math.floor(t/2)+Math.floor(r/3))%2==0};case h:return function(t,r){return t*r%2+t*r%3==0};case s:return function(t,r){return(t*r%2+t*r%3)%2==0};case v:return function(t,r){return(t*r%3+(t+r)%2)%2==0};default:throw"bad maskPattern:"+t}},t.getErrorCorrectPolynomial=function(t){for(var r=C([1],0),e=0;e<t;e+=1)r=r.multiply(C([1,w.gexp(e)],0));return r},t.getLengthInBits=function(t,r){if(1<=r&&r<10)switch(t){case a:return 10;case u:return 9;case o:case f:return 8;default:throw"mode:"+t}else if(r<27)switch(t){case a:return 12;case u:return 11;case o:return 16;case f:return 10;default:throw"mode:"+t}else{if(!(r<41))throw"type:"+r;switch(t){case a:return 14;case u:return 13;case o:return 16;case f:return 12;default:throw"mode:"+t}}},t.getLostPoint=function(t){for(var r=t.getModuleCount(),e=0,n=0;n<r;n+=1)for(var o=0;o<r;o+=1){for(var i=0,a=t.isDark(n,o),u=-1;u<=1;u+=1)if(!(n+u<0||r<=n+u))for(var f=-1;f<=1;f+=1)o+f<0||r<=o+f||0==u&&0==f||a==t.isDark(n+u,o+f)&&(i+=1);5<i&&(e+=3+i-5)}for(n=0;n<r-1;n+=1)for(o=0;o<r-1;o+=1){var c=0;t.isDark(n,o)&&(c+=1),t.isDark(n+1,o)&&(c+=1),t.isDark(n,o+1)&&(c+=1),t.isDark(n+1,o+1)&&(c+=1),0!=c&&4!=c||(e+=3)}for(n=0;n<r;n+=1)for(o=0;o<r-6;o+=1)t.isDark(n,o)&&!t.isDark(n,o+1)&&t.isDark(n,o+2)&&t.isDark(n,o+3)&&t.isDark(n,o+4)&&!t.isDark(n,o+5)&&t.isDark(n,o+6)&&(e+=40);for(o=0;o<r;o+=1)for(n=0;n<r-6;n+=1)t.isDark(n,o)&&!t.isDark(n+1,o)&&t.isDark(n+2,o)&&t.isDark(n+3,o)&&t.isDark(n+4,o)&&!t.isDark(n+5,o)&&t.isDark(n+6,o)&&(e+=40);var g=0;for(o=0;o<r;o+=1)for(n=0;n<r;n+=1)t.isDark(n,o)&&(g+=1);return e+=Math.abs(100*g/r/r-50)/5*10},t);function d(t){for(var r=0;0!=t;)r+=1,t>>>=1;return r}var w=function(){for(var r=new Array(256),e=new Array(256),t=0;t<8;t+=1)r[t]=1<<t;for(t=8;t<256;t+=1)r[t]=r[t-4]^r[t-5]^r[t-6]^r[t-8];for(t=0;t<255;t+=1)e[r[t]]=t;var n={glog:function(t){if(t<1)throw"glog("+t+")";return e[t]},gexp:function(t){for(;t<0;)t+=255;for(;256<=t;)t-=255;return r[t]}};return n}();function C(n,o){if(void 0===n.length)throw n.length+"/"+o;var r=function(){for(var t=0;t<n.length&&0==n[t];)t+=1;for(var r=new Array(n.length-t+o),e=0;e<n.length-t;e+=1)r[e]=n[e+t];return r}(),i={getAt:function(t){return r[t]},getLength:function(){return r.length},multiply:function(t){for(var r=new Array(i.getLength()+t.getLength()-1),e=0;e<i.getLength();e+=1)for(var n=0;n<t.getLength();n+=1)r[e+n]^=w.gexp(w.glog(i.getAt(e))+w.glog(t.getAt(n)));return C(r,0)},mod:function(t){if(i.getLength()-t.getLength()<0)return i;for(var r=w.glog(i.getAt(0))-w.glog(t.getAt(0)),e=new Array(i.getLength()),n=0;n<i.getLength();n+=1)e[n]=i.getAt(n);for(n=0;n<t.getLength();n+=1)e[n]^=w.gexp(w.glog(t.getAt(n))+r);return C(e,0).mod(t)}};return i}function p(){var e=[],o={writeByte:function(t){e.push(255&t)},writeShort:function(t){o.writeByte(t),o.writeByte(t>>>8)},writeBytes:function(t,r,e){r=r||0,e=e||t.length;for(var n=0;n<e;n+=1)o.writeByte(t[n+r])},writeString:function(t){for(var r=0;r<t.length;r+=1)o.writeByte(t.charCodeAt(r))},toByteArray:function(){return e},toString:function(){var t="";t+="[";for(var r=0;r<e.length;r+=1)0<r&&(t+=","),t+=e[r];return t+="]"}};return o}var k,A,b=(k=[[1,26,19],[1,26,16],[1,26,13],[1,26,9],[1,44,34],[1,44,28],[1,44,22],[1,44,16],[1,70,55],[1,70,44],[2,35,17],[2,35,13],[1,100,80],[2,50,32],[2,50,24],[4,25,9],[1,134,108],[2,67,43],[2,33,15,2,34,16],[2,33,11,2,34,12],[2,86,68],[4,43,27],[4,43,19],[4,43,15],[2,98,78],[4,49,31],[2,32,14,4,33,15],[4,39,13,1,40,14],[2,121,97],[2,60,38,2,61,39],[4,40,18,2,41,19],[4,40,14,2,41,15],[2,146,116],[3,58,36,2,59,37],[4,36,16,4,37,17],[4,36,12,4,37,13],[2,86,68,2,87,69],[4,69,43,1,70,44],[6,43,19,2,44,20],[6,43,15,2,44,16],[4,101,81],[1,80,50,4,81,51],[4,50,22,4,51,23],[3,36,12,8,37,13],[2,116,92,2,117,93],[6,58,36,2,59,37],[4,46,20,6,47,21],[7,42,14,4,43,15],[4,133,107],[8,59,37,1,60,38],[8,44,20,4,45,21],[12,33,11,4,34,12],[3,145,115,1,146,116],[4,64,40,5,65,41],[11,36,16,5,37,17],[11,36,12,5,37,13],[5,109,87,1,110,88],[5,65,41,5,66,42],[5,54,24,7,55,25],[11,36,12,7,37,13],[5,122,98,1,123,99],[7,73,45,3,74,46],[15,43,19,2,44,20],[3,45,15,13,46,16],[1,135,107,5,136,108],[10,74,46,1,75,47],[1,50,22,15,51,23],[2,42,14,17,43,15],[5,150,120,1,151,121],[9,69,43,4,70,44],[17,50,22,1,51,23],[2,42,14,19,43,15],[3,141,113,4,142,114],[3,70,44,11,71,45],[17,47,21,4,48,22],[9,39,13,16,40,14],[3,135,107,5,136,108],[3,67,41,13,68,42],[15,54,24,5,55,25],[15,43,15,10,44,16],[4,144,116,4,145,117],[17,68,42],[17,50,22,6,51,23],[19,46,16,6,47,17],[2,139,111,7,140,112],[17,74,46],[7,54,24,16,55,25],[34,37,13],[4,151,121,5,152,122],[4,75,47,14,76,48],[11,54,24,14,55,25],[16,45,15,14,46,16],[6,147,117,4,148,118],[6,73,45,14,74,46],[11,54,24,16,55,25],[30,46,16,2,47,17],[8,132,106,4,133,107],[8,75,47,13,76,48],[7,54,24,22,55,25],[22,45,15,13,46,16],[10,142,114,2,143,115],[19,74,46,4,75,47],[28,50,22,6,51,23],[33,46,16,4,47,17],[8,152,122,4,153,123],[22,73,45,3,74,46],[8,53,23,26,54,24],[12,45,15,28,46,16],[3,147,117,10,148,118],[3,73,45,23,74,46],[4,54,24,31,55,25],[11,45,15,31,46,16],[7,146,116,7,147,117],[21,73,45,7,74,46],[1,53,23,37,54,24],[19,45,15,26,46,16],[5,145,115,10,146,116],[19,75,47,10,76,48],[15,54,24,25,55,25],[23,45,15,25,46,16],[13,145,115,3,146,116],[2,74,46,29,75,47],[42,54,24,1,55,25],[23,45,15,28,46,16],[17,145,115],[10,74,46,23,75,47],[10,54,24,35,55,25],[19,45,15,35,46,16],[17,145,115,1,146,116],[14,74,46,21,75,47],[29,54,24,19,55,25],[11,45,15,46,46,16],[13,145,115,6,146,116],[14,74,46,23,75,47],[44,54,24,7,55,25],[59,46,16,1,47,17],[12,151,121,7,152,122],[12,75,47,26,76,48],[39,54,24,14,55,25],[22,45,15,41,46,16],[6,151,121,14,152,122],[6,75,47,34,76,48],[46,54,24,10,55,25],[2,45,15,64,46,16],[17,152,122,4,153,123],[29,74,46,14,75,47],[49,54,24,10,55,25],[24,45,15,46,46,16],[4,152,122,18,153,123],[13,74,46,32,75,47],[48,54,24,14,55,25],[42,45,15,32,46,16],[20,147,117,4,148,118],[40,75,47,7,76,48],[43,54,24,22,55,25],[10,45,15,67,46,16],[19,148,118,6,149,119],[18,75,47,31,76,48],[34,54,24,34,55,25],[20,45,15,61,46,16]],(A={}).getRSBlocks=function(t,r){var e=function(t,r){switch(r){case y.L:return k[4*(t-1)+0];case y.M:return k[4*(t-1)+1];case y.Q:return k[4*(t-1)+2];case y.H:return k[4*(t-1)+3];default:return}}(t,r);if(void 0===e)throw"bad rs block @ typeNumber:"+t+"/errorCorrectionLevel:"+r;for(var n,o,i=e.length/3,a=[],u=0;u<i;u+=1)for(var f=e[3*u+0],c=e[3*u+1],g=e[3*u+2],l=0;l<f;l+=1)a.push((n=g,o=void 0,(o={}).totalCount=c,o.dataCount=n,o));return a},A),M=function(){var e=[],n=0,o={getBuffer:function(){return e},getAt:function(t){var r=Math.floor(t/8);return 1==(e[r]>>>7-t%8&1)},put:function(t,r){for(var e=0;e<r;e+=1)o.putBit(1==(t>>>r-e-1&1))},getLengthInBits:function(){return n},putBit:function(t){var r=Math.floor(n/8);e.length<=r&&e.push(0),t&&(e[r]|=128>>>n%8),n+=1}};return o},x=function(t){var r=a,n=t,e={getMode:function(){return r},getLength:function(t){return n.length},write:function(t){for(var r=n,e=0;e+2<r.length;)t.put(o(r.substring(e,e+3)),10),e+=3;e<r.length&&(r.length-e==1?t.put(o(r.substring(e,e+1)),4):r.length-e==2&&t.put(o(r.substring(e,e+2)),7))}},o=function(t){for(var r=0,e=0;e<t.length;e+=1)r=10*r+i(t.charAt(e));return r},i=function(t){if("0"<=t&&t<="9")return t.charCodeAt(0)-"0".charCodeAt(0);throw"illegal char :"+t};return e},m=function(t){var r=u,n=t,e={getMode:function(){return r},getLength:function(t){return n.length},write:function(t){for(var r=n,e=0;e+1<r.length;)t.put(45*o(r.charAt(e))+o(r.charAt(e+1)),11),e+=2;e<r.length&&t.put(o(r.charAt(e)),6)}},o=function(t){if("0"<=t&&t<="9")return t.charCodeAt(0)-"0".charCodeAt(0);if("A"<=t&&t<="Z")return t.charCodeAt(0)-"A".charCodeAt(0)+10;switch(t){case" ":return 36;case"$":return 37;case"%":return 38;case"*":return 39;case"+":return 40;case"-":return 41;case".":return 42;case"/":return 43;case":":return 44;default:throw"illegal char :"+t}};return e},L=function(t){var r=o,e=i.stringToBytes(t),n={getMode:function(){return r},getLength:function(t){return e.length},write:function(t){for(var r=0;r<e.length;r+=1)t.put(e[r],8)}};return n},D=function(t){var r=f,e=i.stringToBytesFuncs.SJIS;if(!e)throw"sjis not supported.";!function(){var t=e("?");if(2!=t.length||38726!=(t[0]<<8|t[1]))throw"sjis not supported."}();var o=e(t),n={getMode:function(){return r},getLength:function(t){return~~(o.length/2)},write:function(t){for(var r=o,e=0;e+1<r.length;){var n=(255&r[e])<<8|255&r[e+1];if(33088<=n&&n<=40956)n-=33088;else{if(!(57408<=n&&n<=60351))throw"illegal char at "+(e+1)+"/"+n;n-=49472}n=192*(n>>>8&255)+(255&n),t.put(n,13),e+=2}if(e<r.length)throw"illegal char at "+(e+1)}};return n},S=function(t){var e=t,n=0,o=0,i=0,r={read:function(){for(;i<8;){if(n>=e.length){if(0==i)return-1;throw"unexpected end of file./"+i}var t=e.charAt(n);if(n+=1,"="==t)return i=0,-1;t.match(/^\s$/)||(o=o<<6|a(t.charCodeAt(0)),i+=6)}var r=o>>>i-8&255;return i-=8,r}},a=function(t){if(65<=t&&t<=90)return t-65;if(97<=t&&t<=122)return t-97+26;if(48<=t&&t<=57)return t-48+52;if(43==t)return 62;if(47==t)return 63;throw"c:"+t};return r},I=function(t,r,e){for(var n=function(t,r){var n=t,o=r,l=new Array(t*r),e={setPixel:function(t,r,e){l[r*n+t]=e},write:function(t){t.writeString("GIF87a"),t.writeShort(n),t.writeShort(o),t.writeByte(128),t.writeByte(0),t.writeByte(0),t.writeByte(0),t.writeByte(0),t.writeByte(0),t.writeByte(255),t.writeByte(255),t.writeByte(255),t.writeString(","),t.writeShort(0),t.writeShort(0),t.writeShort(n),t.writeShort(o),t.writeByte(0);var r=i(2);t.writeByte(2);for(var e=0;255<r.length-e;)t.writeByte(255),t.writeBytes(r,e,255),e+=255;t.writeByte(r.length-e),t.writeBytes(r,e,r.length-e),t.writeByte(0),t.writeString(";")}},i=function(t){for(var r=1<<t,e=1+(1<<t),n=t+1,o=h(),i=0;i<r;i+=1)o.add(String.fromCharCode(i));o.add(String.fromCharCode(r)),o.add(String.fromCharCode(e));var a=p(),u=function(t){var e=t,n=0,o=0,r={write:function(t,r){if(t>>>r!=0)throw"length over";for(;8<=n+r;)e.writeByte(255&(t<<n|o)),r-=8-n,t>>>=8-n,n=o=0;o|=t<<n,n+=r},flush:function(){0<n&&e.writeByte(o)}};return r}(a);u.write(r,n);var f=0,c=String.fromCharCode(l[f]);for(f+=1;f<l.length;){var g=String.fromCharCode(l[f]);f+=1,o.contains(c+g)?c+=g:(u.write(o.indexOf(c),n),o.size()<4095&&(o.size()==1<<n&&(n+=1),o.add(c+g)),c=g)}return u.write(o.indexOf(c),n),u.write(e,n),u.flush(),a.toByteArray()},h=function(){var r={},e=0,n={add:function(t){if(n.contains(t))throw"dup key:"+t;r[t]=e,e+=1},size:function(){return e},indexOf:function(t){return r[t]},contains:function(t){return void 0!==r[t]}};return n};return e}(t,r),o=0;o<r;o+=1)for(var i=0;i<t;i+=1)n.setPixel(i,o,e(i,o));var a=p();n.write(a);for(var u=function(){function e(t){a+=String.fromCharCode(r(63&t))}var n=0,o=0,i=0,a="",t={},r=function(t){if(t<0);else{if(t<26)return 65+t;if(t<52)return t-26+97;if(t<62)return t-52+48;if(62==t)return 43;if(63==t)return 47}throw"n:"+t};return t.writeByte=function(t){for(n=n<<8|255&t,o+=8,i+=1;6<=o;)e(n>>>o-6),o-=6},t.flush=function(){if(0<o&&(e(n<<6-o),o=n=0),i%3!=0)for(var t=3-i%3,r=0;r<t;r+=1)a+="="},t.toString=function(){return a},t}(),f=a.toByteArray(),c=0;c<f.length;c+=1)u.writeByte(f[c]);return u.flush(),"data:image/gif;base64,"+u};return i}();qrcode.stringToBytesFuncs["UTF-8"]=function(t){return function(t){for(var r=[],e=0;e<t.length;e++){var n=t.charCodeAt(e);n<128?r.push(n):n<2048?r.push(192|n>>6,128|63&n):n<55296||57344<=n?r.push(224|n>>12,128|n>>6&63,128|63&n):(e++,n=65536+((1023&n)<<10|1023&t.charCodeAt(e)),r.push(240|n>>18,128|n>>12&63,128|n>>6&63,128|63&n))}return r}(t)},function(t){"function"==typeof define&&define.amd?define([],t):"object"==typeof exports&&(module.exports=t())}(function(){return qrcode});

  </script>
</head>
<body>
  <canvas id="fireworks" aria-hidden="true"></canvas>

  <!-- WARNING MODAL -->
  <div id="modal-warning" class="modal-overlay hidden">
    <div class="modal-card">
      <div class="modal-badge" id="modal-warning-badge">⚠️ ПОПЕРЕДЖЕННЯ 1 / 2</div>
      <h2 style="color: var(--amber); margin: 8px 0;">Увага: втрата фокусу тесту!</h2>
      <p id="modal-warning-text" style="font-size: 14px; color: #334155; margin: 10px 0 14px;"></p>
      <div class="modal-rule-note">
        <strong>Зверніть увагу:</strong> це перше зафіксоване попередження. Якщо ви знову перемкнете вкладку, вийдете з вікна або згорнете браузер — тест буде <strong>миттєво анульовано з оцінкою 2 бали</strong>.
      </div>
      <button type="button" class="btn btn-primary btn-full" id="btn-modal-resume" style="margin-top: 16px;">
        Зрозуміло, повертаюся до тесту
      </button>
    </div>
  </div>

  <header class="topbar">
    <div class="brand">КодТест · Інформатика (8 клас)</div>
    <div class="status-line" id="topbar-status">12 завдань · Захист від ШІ</div>
  </header>

  <main class="container">
    <!-- JOIN SCREEN -->
    <section class="card" id="screen-join">
      <p class="kicker">Контрольна робота онлайн</p>
      <h1>Інформаційні системи, сигнали та двійковий код</h1>
      <p class="desc">Впиши своє прізвище, ім’я та клас. Після натискання кнопки увімкнеться захищений режим перевірки знань.</p>

      <!-- QR CODE BLOCK -->
      <div class="qr-card" id="qr-section">
        <div class="qr-header">
          <span style="font-size: 26px;">📱</span>
          <div>
            <strong style="font-size: 15px; color: #1e293b;">Скануй QR-код камерою телефона</strong>
            <div style="font-size: 13px; color: var(--muted);">Відкрий тест на смартфоні або переходь за посиланням:</div>
          </div>
        </div>
        <div id="qr-container" class="qr-box"></div>
        <div class="qr-input-row">
          <input type="text" id="qr-link-input" readonly />
          <button type="button" class="btn btn-secondary btn-sm" id="btn-edit-url" title="Змінити посилання">Змінити ✏️</button>
        </div>
        <p class="qr-hint">💡 Посилання оновлюється автоматично під час публікації на GitHub Pages. Натисніть «Змінити», щоб ввести адресу для проєктора.</p>
      </div>

      <div class="grid-2">
        <div>
          <label class="field-label" for="student-name">Прізвище та ім’я</label>
          <input type="text" id="student-name" maxlength="80" placeholder="Наприклад: Мельник Софія" />
        </div>
        <div>
          <label class="field-label" for="student-class">Клас</label>
          <input type="text" id="student-class" maxlength="20" placeholder="8-А" />
        </div>
      </div>

      <div class="rules-box">
        <strong>Правила чесного тесту:</strong>
        <ul>
          <li>Тест відкриється на весь екран. Не згортай браузер!</li>
          <li><strong>Перемикання вкладки чи перехід до інших застосунків</strong> дає одне попередження; при повторній спробі роботу буде <strong>анульовано з оцінкою 2 бали</strong>.</li>
          <li>Копіювання питань та вставка тексту в розгорнутій відповіді заблоковані.</li>
        </ul>
      </div>

      <p class="err-msg hidden" id="join-error"></p>
      <button type="button" class="btn btn-primary btn-full" id="btn-start">
        Почати чесний тест (15 хв)
      </button>
    </section>

    <!-- EXAM SCREEN -->
    <section class="card hidden" id="screen-exam" style="user-select: none;">
      <div id="exam-warning" class="alert-banner hidden"></div>
      <div class="progress-bar"><div class="progress-fill" id="progress-fill" style="width: 8%;"></div></div>
      <p class="kicker" id="q-meta">Завдання 1 з 12</p>
      <h2 id="q-title"></h2>
      <div id="q-body"></div>
      <div class="map-grid" id="q-map"></div>
    </section>

    <!-- ANNULLED SCREEN -->
    <section class="card annul-card hidden" id="screen-annulled">
      <p class="kicker" style="color: var(--red);">Спрацював захист від виходу з тесту</p>
      <h1>Тест анульовано</h1>
      <div class="big-score score-red">2 / 12 балів</div>
      <p class="desc" id="annul-reason-text"></p>
      <button type="button" class="btn btn-primary btn-full" id="btn-download-annul">
        Завантажити звіт для вчителя (.html)
      </button>
    </section>

    <!-- SUBMITTED SCREEN -->
    <section class="card hidden" id="screen-submitted" style="text-align: center;">
      <p class="kicker" style="color: var(--emerald);">Чесне виконання підтверджено</p>
      <h1>Тест успішно завершено!</h1>
      <p class="desc" id="submit-student-label"></p>
      <div class="summary-grid">
        <div>
          <div style="font-size:12px;color:#64748b;">Автотест (1–11)</div>
          <div class="big-score" style="font-size:28px;margin:4px 0;" id="submit-auto-score">0 / 11</div>
        </div>
        <div>
          <div style="font-size:12px;color:#64748b;">Попередньо (12-б.)</div>
          <div class="big-score score-green" style="font-size:28px;margin:4px 0;" id="submit-grade-12">1 / 12</div>
        </div>
        <div style="grid-column: 1 / -1; font-size: 12px; color: #475569;" id="submit-extra-note">
          Питання 12 (три розгорнуті відповіді, до +3 балів) перевірить учитель із завантаженого звіту.
        </div>
      </div>
      <button type="button" class="btn btn-success btn-full" id="btn-download-report">
        Завантажити результат для вчителя (.html)
      </button>
    </section>
  </main>

  <div class="bottom-nav hidden" id="exam-bottom-nav">
    <div class="bottom-nav-inner">
      <button type="button" class="btn btn-secondary" id="btn-prev">← Назад</button>
      <button type="button" class="btn btn-primary" id="btn-next">Далі →</button>
      <button type="button" class="btn btn-success hidden" id="btn-finish">Завершити тест ✓</button>
    </div>
  </div>

  <script>
    (function () {
      const SESSION_KEY = "kodtest_pc_attempt_v2";

      // Base64-encoded answer keys: [[0], [0,1,2], [1], [0], [1], [1], [0], [1], [0], [1], [1]]
      const ENCODED_KEYS = "W1swXSxbMCwxLDJdLFsxXSxbMF0sWzFdLFsxXSxbMF0sWzFdLFswXSxbMV0sWzFdXQ==";

      const QUESTIONS = [
        {
          id: 1, type: "single", topic: "Інформаційні системи",
          question: "Яке визначення найкраще описує інформаційну систему?",
          options: [
            "Система, яка здійснює або в якій відбуваються інформаційні процеси: пошук, збирання, зберігання, передавання та опрацювання інформації.",
            "Набір комп’ютерних компонентів, які використовуються для зберігання даних.",
            "Система, яка забезпечує доступ до Інтернету.",
            "Комп’ютерна програма, що використовується для обробки тексту."
          ]
        },
        {
          id: 2, type: "multi", topic: "Складові інформаційної системи",
          question: "Які складові входять до будь-якої інформаційної системи? (оберіть усі правильні відповіді)",
          options: [
            "Апаратне забезпечення",
            "Програмне забезпечення",
            "Канали зв’язку",
            "Електронна пошта"
          ]
        },
        {
          id: 3, type: "single", topic: "Персональні комп’ютери",
          question: "Що з переліченого не є типом персонального комп’ютера?",
          options: ["Ноутбук", "Сервер", "Планшет", "Стаціонарний комп’ютер"]
        },
        {
          id: 4, type: "single", topic: "Апаратне забезпечення",
          question: "Яка роль апаратного забезпечення в інформаційній системі?",
          options: [
            "Зберігати дані та виконувати обчислення",
            "Перевіряти правильність коду",
            "Передавати дані та взаємодіяти із користувачем",
            "Здійснювати підтримку користувачів"
          ]
        },
        {
          id: 5, type: "single", topic: "Мікрокомп’ютери",
          question: "Що таке micro:bit?",
          options: [
            "Невеликий мікропроцесор для смартфонів.",
            "Кишеньковий комп’ютер для навчання програмуванню та робототехніці.",
            "Програмне забезпечення для обробки зображень.",
            "Пристрій для зберігання великих обсягів інформації."
          ]
        },
        {
          id: 6, type: "single", topic: "Кодування величин",
          question: "Що таке кодування фізичних величин у контексті цифрових пристроїв?",
          options: [
            "Процес стиснення даних для зменшення розміру файлу.",
            "Перетворення фізичних (аналогових) сигналів у цифровий формат для опрацювання та зберігання.",
            "Процес шифрування даних для забезпечення безпеки.",
            "Зміна кольорової гами зображення."
          ]
        },
        {
          id: 7, type: "single", topic: "Сигнали",
          question: "Чим відрізняється аналоговий сигнал від цифрового?",
          options: [
            "Аналоговий сигнал може мати будь-яке значення в певному діапазоні, а цифровий — тільки два (0 і 1).",
            "Цифровий сигнал може мати будь-яке значення, а аналоговий тільки два (0 і 1).",
            "Аналоговий сигнал використовується тільки в телефонних мережах, а цифровий — в комп’ютерах.",
            "Аналоговий сигнал передає дані швидше, ніж цифровий."
          ]
        },
        {
          id: 8, type: "single", topic: "Двійкове кодування",
          question: "Що таке двійковий код?",
          options: [
            "Спосіб кодування даних за допомогою алфавіту з трьох знаків.",
            "Спосіб кодування даних за допомогою алфавіту з двох знаків: 0 і 1.",
            "Кодування інформації за допомогою десяти цифр.",
            "Система вимірювання обсягу пам’яті комп’ютера."
          ]
        },
        {
          id: 9, type: "single", topic: "Бінарна логіка",
          question: "Навіщо використовують цифру 1 у бінарному коді?",
          options: [
            "Щоб позначити увімкнення або активний стан",
            "Щоб вимкнути пристрій",
            "Щоб зберегти аналоговий сигнал",
            "Щоб виміряти напругу на екрані"
          ]
        },
        {
          id: 10, type: "single", topic: "Електронна база",
          question: "Як працює транзистор у цифрових пристроях?",
          options: [
            "Він змінює свої розміри залежно від поданої напруги.",
            "Він вмикає або вимикає струм, діючи як швидкий перемикач.",
            "Він зберігає великі обсяги даних для комп’ютера.",
            "Він охолоджує процесор комп’ютера."
          ]
        },
        {
          id: 11, type: "single", topic: "Формати даних",
          question: "Який з наведених форматів файлів використовується для збереження звукових даних у закодованому вигляді?",
          options: ["JPEG", "MP3", "TXT", "HTML"]
        },
        {
          id: 12, type: "open3", topic: "Розгорнута відповідь",
          question: "Підготуйте відповіді на питання:",
          subPrompts: [
            "Наведіть приклад фізичної величини, яка може бути закодована цифровим пристроєм, і поясніть, як це відбувається.",
            "Чому під час кодування зображень важливо враховувати глибину кольору?",
            "Опишіть, що може статися з сигналом, якщо частота дискретизації вибрана занадто низькою."
          ]
        }
      ];

      function shuffle(arr) {
        const copy = arr.slice();
        for (let i = copy.length - 1; i > 0; i--) {
          const j = Math.floor(Math.random() * (i + 1));
          const tmp = copy[i]; copy[i] = copy[j]; copy[j] = tmp;
        }
        return copy;
      }

      let state = {
        phase: "join",
        studentName: "",
        studentClass: "",
        questionOrder: [],
        optionOrders: {},
        choices: {},
        open12: { part1: "", part2: "", part3: "", pasteAttempted: false },
        currentIdx: 0,
        startedAt: 0,
        finishedAt: null,
        annulReason: "",
        autoScore: 0,
        grade12: 1,
        warningsCount: 0,
        warningLog: []
      };

      let armed = false;
      let finishing = false;
      let enteredFullscreen = false;
      let timerInterval = null;
      let lastBlur = 0;

      const el = (id) => document.getElementById(id);

      function renderQrCode(url) {
        const container = el("qr-container");
        if (!container || typeof qrcode === "undefined") return;
        try {
          const qr = qrcode(0, "M");
          qr.addData(url);
          qr.make();
          container.innerHTML = qr.createSvgTag(5, 4);
        } catch (e) {
          container.innerHTML = "<p style='color:var(--muted);font-size:12px;'>Введіть дійсне посилання для коду</p>";
        }
      }

      function initQrSection() {
        const linkInput = el("qr-link-input");
        const editBtn = el("btn-edit-url");
        if (!linkInput) return;

        let cur = window.location.href;
        if (cur.startsWith("file:")) {
          cur = "https://ваш-аккаунт.github.io/назва-репозиторію/";
        }
        linkInput.value = cur;
        renderQrCode(cur);

        editBtn.addEventListener("click", () => {
          if (linkInput.readOnly) {
            linkInput.readOnly = false;
            linkInput.focus();
            linkInput.select();
            editBtn.textContent = "Готово ✓";
          } else {
            linkInput.readOnly = true;
            editBtn.textContent = "Змінити ✏️";
            renderQrCode(linkInput.value.trim() || window.location.href);
          }
        });

        linkInput.addEventListener("input", () => {
          renderQrCode(linkInput.value.trim() || window.location.href);
        });
      }

      function saveSession() {
        try { sessionStorage.setItem(SESSION_KEY, JSON.stringify(state)); } catch {}
      }

      function restoreSession() {
        try {
          const raw = sessionStorage.getItem(SESSION_KEY);
          if (!raw) return false;
          const parsed = JSON.parse(raw);
          if (parsed && parsed.phase && parsed.phase !== "join") {
            state = parsed;
            return true;
          }
        } catch {}
        return false;
      }

      function showWarning(msg) {
        const box = el("exam-warning");
        box.textContent = msg;
        box.classList.remove("hidden");
      }

      function showModalWarning(reason) {
        const modal = el("modal-warning");
        if (!modal) return;
        el("modal-warning-badge").textContent = `⚠️ ПОПЕРЕДЖЕННЯ ${state.warningsCount} / 2`;
        el("modal-warning-text").innerHTML = `Зафіксовано подію: <strong>${reason}</strong>.<br>Будь ласка, залишайтеся на цій сторінці тесту.`;
        modal.classList.remove("hidden");
        try { if (navigator.vibrate) navigator.vibrate([200, 100, 200]); } catch {}
      }

      function hideModalWarning() {
        const modal = el("modal-warning");
        if (modal) modal.classList.add("hidden");
        if (enteredFullscreen && !document.fullscreenElement) {
          try { document.documentElement.requestFullscreen(); } catch {}
        }
      }

      function handleViolation(reason) {
        if (state.phase !== "exam" || finishing || !armed) return;
        state.warningsCount = (state.warningsCount || 0) + 1;
        state.warningLog = state.warningLog || [];
        const timeStr = new Date().toLocaleTimeString("uk-UA");
        state.warningLog.push(`${timeStr} — ${reason}`);
        saveSession();

        if (state.warningsCount <= 1) {
          showModalWarning(reason);
        } else {
          hideModalWarning();
          triggerAnnul(`Повторне порушення: ${reason}`);
        }
      }

      function gradeQuiz() {
        const keys = JSON.parse(atob(ENCODED_KEYS));
        let score = 0;
        const details = [];
        for (let i = 0; i < 11; i++) {
          const q = QUESTIONS[i];
          const sel = (state.choices[q.id] || []).slice().sort((a, b) => a - b);
          const exp = keys[i].slice().sort((a, b) => a - b);
          let earned = 0;
          if (q.type === "single") {
            if (sel.length === 1 && sel[0] === exp[0]) earned = 1;
          } else {
            const exact = sel.length === exp.length && sel.every((v, k) => v === exp[k]);
            if (exact) earned = 1;
            else {
              const hasWrong = sel.some((v) => !exp.includes(v));
              const matched = sel.filter((v) => exp.includes(v)).length;
              if (!hasWrong && matched >= 2) earned = 0.5;
            }
          }
          score += earned;
          details.push({ id: q.id, earned, sel, exp });
        }
        state.autoScore = Math.round(score * 10) / 10;
        state.grade12 = Math.max(1, Math.min(12, Math.round((state.autoScore / 14) * 12)));
        return details;
      }

      function triggerAnnul(reason) {
        if (state.phase !== "exam" || finishing || !armed) return;
        armed = false;
        state.phase = "annulled";
        state.annulReason = reason;
        state.finishedAt = new Date().toISOString();
        state.grade12 = 2;
        saveSession();
        clearInterval(timerInterval);
        try { if (document.fullscreenElement) document.exitFullscreen(); } catch {}
        renderScreens();
      }

      function finishExam() {
        if (state.phase !== "exam" || finishing) return;
        finishing = true;
        armed = false;
        clearInterval(timerInterval);
        try { if (document.fullscreenElement) document.exitFullscreen(); } catch {}
        gradeQuiz();
        state.phase = "submitted";
        state.finishedAt = new Date().toISOString();
        saveSession();
        renderScreens();
        launchFireworks();
      }

      function renderQuestion() {
        const qId = state.questionOrder[state.currentIdx];
        const q = QUESTIONS.find((x) => x.id === qId);
        if (!q) return;

        el("q-meta").textContent = `Завдання ${state.currentIdx + 1} з ${QUESTIONS.length} · ${q.topic}`;
        el("q-title").textContent = q.question;
        el("progress-fill").style.width = `${((state.currentIdx + 1) / QUESTIONS.length) * 100}%`;

        const body = el("q-body");
        body.innerHTML = "";

        if (q.type !== "open3") {
          const list = document.createElement("div");
          list.className = "options-list";
          const order = state.optionOrders[q.id] || q.options.map((_, i) => i);
          const selected = state.choices[q.id] || [];

          order.forEach((origIdx, dispIdx) => {
            const btn = document.createElement("button");
            btn.type = "button";
            btn.className = "option-btn" + (selected.includes(origIdx) ? " selected" : "");
            const letter = document.createElement("span");
            letter.className = "option-letter";
            letter.textContent = String.fromCharCode(65 + dispIdx);
            const text = document.createElement("span");
            text.textContent = q.options[origIdx];
            btn.appendChild(letter);
            btn.appendChild(text);
            btn.addEventListener("click", () => {
              const cur = state.choices[q.id] || [];
              if (q.type === "single") {
                state.choices[q.id] = [origIdx];
              } else {
                state.choices[q.id] = cur.includes(origIdx)
                  ? cur.filter((x) => x !== origIdx)
                  : cur.concat(origIdx);
              }
              saveSession();
              renderQuestion();
            });
            list.appendChild(btn);
          });
          body.appendChild(list);
        } else {
          const parts = [
            { key: "part1", prompt: q.subPrompts[0] },
            { key: "part2", prompt: q.subPrompts[1] },
            { key: "part3", prompt: q.subPrompts[2] }
          ];
          parts.forEach((p, idx) => {
            const wrap = document.createElement("div");
            wrap.className = "open-part";
            const lbl = document.createElement("label");
            lbl.textContent = `${idx + 1}. ${p.prompt}`;
            const ta = document.createElement("textarea");
            ta.rows = 3;
            ta.value = state.open12[p.key] || "";
            ta.placeholder = "Впиши відповідь своїми словами...";
            ta.addEventListener("input", (e) => {
              state.open12[p.key] = e.target.value;
              saveSession();
            });
            ta.addEventListener("paste", (e) => {
              e.preventDefault();
              state.open12.pasteAttempted = true;
              saveSession();
              showWarning("Вставка скопійованого тексту вимкнена! Запиши відповідь самостійно.");
            });
            wrap.appendChild(lbl);
            wrap.appendChild(ta);
            body.appendChild(wrap);
          });
        }

        // Map
        const map = el("q-map");
        map.innerHTML = "";
        state.questionOrder.forEach((id, idx) => {
          const dot = document.createElement("button");
          dot.type = "button";
          const qItem = QUESTIONS.find((x) => x.id === id);
          const isAns = qItem.type === "open3"
            ? Boolean(state.open12.part1.trim() || state.open12.part2.trim() || state.open12.part3.trim())
            : (state.choices[id] || []).length > 0;
          dot.className = "map-dot" + (idx === state.currentIdx ? " current" : isAns ? " answered" : "");
          dot.textContent = String(idx + 1);
          dot.addEventListener("click", () => {
            state.currentIdx = idx;
            saveSession();
            renderQuestion();
          });
          map.appendChild(dot);
        });

        el("btn-prev").disabled = state.currentIdx === 0;
        const isLast = state.currentIdx === QUESTIONS.length - 1;
        el("btn-next").classList.toggle("hidden", isLast);
        el("btn-finish").classList.toggle("hidden", !isLast);
      }

      function startTimer() {
        clearInterval(timerInterval);
        const deadline = state.startedAt + 15 * 60 * 1000;
        const tick = () => {
          const left = Math.max(0, Math.floor((deadline - Date.now()) / 1000));
          const m = String(Math.floor(left / 60)).padStart(2, "0");
          const s = String(left % 60).padStart(2, "0");
          el("topbar-status").textContent = `Щит активний · ${m}:${s} · ${state.studentName}`;
          if (left === 0) finishExam();
        };
        tick();
        timerInterval = setInterval(tick, 1000);
      }

      function renderScreens() {
        el("screen-join").classList.toggle("hidden", state.phase !== "join");
        el("screen-exam").classList.toggle("hidden", state.phase !== "exam");
        el("exam-bottom-nav").classList.toggle("hidden", state.phase !== "exam");
        el("screen-annulled").classList.toggle("hidden", state.phase !== "annulled");
        el("screen-submitted").classList.toggle("hidden", state.phase !== "submitted");

        if (state.phase === "exam") {
          renderQuestion();
          startTimer();
        } else if (state.phase === "annulled") {
          el("topbar-status").textContent = "Анульовано (2 бали)";
          el("annul-reason-text").textContent =
            `${state.studentName} (${state.studentClass}) · Причина: ${state.annulReason}. Оцінка: 2 бали.`;
        } else if (state.phase === "submitted") {
          el("topbar-status").textContent = "Тест здано";
          el("submit-student-label").textContent = `${state.studentName} (${state.studentClass})`;
          el("submit-auto-score").textContent = `${state.autoScore} / 11`;
          el("submit-grade-12").textContent = `${state.grade12} / 12`;
          if (state.warningsCount > 0) {
            el("submit-extra-note").innerHTML = `⚠️ Зафіксовано попереджень: <strong>${state.warningsCount}</strong>.<br>Питання 12 (розгорнуті відповіді, до +3 балів) перевірить учитель.`;
          }
        }
      }

      function downloadReport() {
        const details = state.phase === "submitted" ? gradeQuiz() : [];
        const safeName = (state.studentName || "Учень").replace(/[<>"]/g, "");
        const safeClass = (state.studentClass || "—").replace(/[<>"]/g, "");
        const esc = (s) => String(s || "").replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");

        const html = `<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <title>Результат тесту — ${esc(safeName)}</title>
  <style>
    body { font-family: system-ui, sans-serif; max-width: 760px; margin: 36px auto; padding: 0 18px; color: #0f172a; line-height: 1.55; }
    .box { border: 2px solid ${state.phase === "annulled" ? "#dc2626" : "#0284c7"}; border-radius: 14px; padding: 20px; margin-bottom: 20px; background: ${state.phase === "annulled" ? "#fef2f2" : "#f0f9ff"}; }
    .item { border: 1px solid #e2e8f0; border-radius: 10px; padding: 12px 14px; margin-bottom: 10px; }
  </style>
</head>
<body>
  <div class="box">
    <h1 style="margin:0 0 8px;">Звіт з тесту «Інформаційні системи та кодування»</h1>
    <p style="margin:4px 0;">Учень: <strong>${esc(safeName)}</strong> · Клас: <strong>${esc(safeClass)}</strong></p>
    <p style="margin:4px 0;">Статус: <strong>${state.phase === "annulled" ? "АНУЛЬОВАНО (" + esc(state.annulReason) + ")" : "Успішно завершено"}</strong></p>
    <p style="margin:4px 0;">Зафіксовано попереджень фокусу: <strong>${state.warningsCount || 0}</strong></p>
    ${state.warningLog && state.warningLog.length ? `<p style="font-size:13px;color:#b45309;margin:4px 0;">Журнал подій: ${esc(state.warningLog.join("; "))}</p>` : ""}
    <p style="margin:8px 0 0;font-size:22px;font-weight:800;">
      ${state.phase === "annulled" ? "Підсумкова оцінка: 2 / 12 балів" : `Автотест (1–11): ${state.autoScore} / 11 · Попередня (12-б.): ${state.grade12} / 12 (+ питання 12)`}
    </p>
    ${state.open12.pasteAttempted ? '<p style="color:#b45309;font-weight:700;">Увага: зафіксовано спробу вставки тексту у питанні 12.</p>' : ""}
  </div>
  ${details.map((d) => {
    const q = QUESTIONS.find((x) => x.id === d.id);
    return `<div class="item">
      <strong>${q.id}. ${esc(q.question)}</strong>
      <div>Обрано: ${d.sel.map((i) => esc(q.options[i])).join("; ") || "—"} · Бал: <strong>+${d.earned}</strong></div>
    </div>`;
  }).join("")}
  <div class="item">
    <strong>12. Відкриті відповіді учня (перевіряє вчитель, до 3 балів):</strong>
    <p><em>1) Фізична величина:</em> ${esc(state.open12.part1) || "—"}</p>
    <p><em>2) Глибина кольору:</em> ${esc(state.open12.part2) || "—"}</p>
    <p><em>3) Частота дискретизації:</em> ${esc(state.open12.part3) || "—"}</p>
  </div>
</body>
</html>`;
        const blob = new Blob([html], { type: "text/html;charset=utf-8" });
        const url = URL.createObjectURL(blob);
        const a = document.createElement("a");
        a.href = url;
        a.download = `результат_${safeName.replace(/\s+/g, "_")}.html`;
        a.click();
        URL.revokeObjectURL(url);
      }

      function launchFireworks() {
        const canvas = el("fireworks");
        const ctx = canvas.getContext("2d");
        const dpr = Math.min(window.devicePixelRatio || 1, 2);
        const w = window.innerWidth, h = window.innerHeight;
        canvas.width = w * dpr; canvas.height = h * dpr;
        ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
        const colors = ["#0284c7", "#10b981", "#f59e0b", "#f43f5e", "#8b5cf6"];
        const particles = [];
        [0.25, 0.5, 0.75].forEach((xr) => {
          for (let i = 0; i < 34; i++) {
            const angle = (Math.PI * 2 * i) / 34;
            const speed = 2.5 + Math.random() * 5.2;
            particles.push({
              x: w * xr, y: h * 0.3,
              vx: Math.cos(angle) * speed, vy: Math.sin(angle) * speed - 1.5,
              r: 3 + Math.random() * 4,
              c: colors[i % colors.length], a: 1
            });
          }
        });
        function frame() {
          ctx.clearRect(0, 0, w, h);
          let alive = false;
          particles.forEach((p) => {
            if (p.a <= 0.02) return;
            alive = true;
            p.x += p.vx; p.y += p.vy; p.vy += 0.12; p.a -= 0.015;
            ctx.globalAlpha = Math.max(0, p.a);
            ctx.fillStyle = p.c;
            ctx.beginPath(); ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2); ctx.fill();
          });
          if (alive) requestAnimationFrame(frame);
          else ctx.clearRect(0, 0, w, h);
        }
        requestAnimationFrame(frame);
      }

      el("btn-start").addEventListener("click", async () => {
        const name = el("student-name").value.trim();
        const cls = el("student-class").value.trim() || "—";
        if (name.length < 2) {
          el("join-error").textContent = "Введи своє прізвище та ім’я.";
          el("join-error").classList.remove("hidden");
          return;
        }
        el("join-error").classList.add("hidden");

        state.studentName = name;
        state.studentClass = cls;
        state.questionOrder = shuffle(QUESTIONS.slice(0, 11).map((q) => q.id)).concat(12);
        state.optionOrders = {};
        QUESTIONS.forEach((q) => {
          if (q.options) state.optionOrders[q.id] = shuffle(q.options.map((_, i) => i));
        });
        state.choices = {};
        state.open12 = { part1: "", part2: "", part3: "", pasteAttempted: false };
        state.currentIdx = 0;
        state.startedAt = Date.now();
        state.phase = "exam";
        state.warningsCount = 0;
        state.warningLog = [];
        saveSession();

        try {
          if (document.documentElement.requestFullscreen) {
            await document.documentElement.requestFullscreen();
            enteredFullscreen = true;
          }
        } catch { enteredFullscreen = false; }

        renderScreens();
        setTimeout(() => { armed = true; }, 700);
      });

      el("btn-prev").addEventListener("click", () => {
        if (state.currentIdx > 0) { state.currentIdx--; saveSession(); renderQuestion(); }
      });
      el("btn-next").addEventListener("click", () => {
        if (state.currentIdx < QUESTIONS.length - 1) { state.currentIdx++; saveSession(); renderQuestion(); }
      });
      el("btn-finish").addEventListener("click", finishExam);
      el("btn-download-report").addEventListener("click", downloadReport);
      el("btn-download-annul").addEventListener("click", downloadReport);
      el("btn-modal-resume").addEventListener("click", hideModalWarning);

      document.addEventListener("visibilitychange", () => {
        if (document.visibilityState === "hidden") {
          handleViolation("Перемикання вкладки або згортання браузера");
        }
      });
      window.addEventListener("blur", () => {
        const now = Date.now();
        if (now - lastBlur < 500) return;
        lastBlur = now;
        setTimeout(() => {
          if (!armed || finishing) return;
          const tag = document.activeElement && document.activeElement.tagName;
          if (!document.hasFocus() && tag !== "TEXTAREA" && tag !== "INPUT") {
            handleViolation("Перехід в інше вікно або застосунок");
          }
        }, 350);
      });
      document.addEventListener("fullscreenchange", () => {
        if (enteredFullscreen && !document.fullscreenElement && armed && !finishing) {
          handleViolation("Вихід із повноекранного режиму");
        }
      });
      document.addEventListener("contextmenu", (e) => {
        if (state.phase === "exam") e.preventDefault();
      });
      document.addEventListener("copy", (e) => {
        if (state.phase === "exam" && e.target.tagName !== "TEXTAREA") {
          e.preventDefault();
          showWarning("Копіювання тексту питань заборонено.");
        }
      });

      initQrSection();

      if (restoreSession()) {
        renderScreens();
        if (state.phase === "exam") setTimeout(() => { armed = true; }, 500);
      }
    })();
  </script>
</body>
</html>
