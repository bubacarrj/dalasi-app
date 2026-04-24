[index.html](https://github.com/user-attachments/files/27057042/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>Dalasi — Home for Every Gambian</title>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:wght@400;600;700&family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{
  --g:#1B4332;--gm:#2D6A4F;--gl:#40916C;--gp:#D8F3DC;
  --au:#D4A017;--al:#F4C430;
  --cr:#FAF7F0;--ww:#FFFDF7;
  --td:#1A1A1A;--tm:#4A4A4A;--tl:#888;
  --sh:0 4px 20px rgba(27,67,50,0.10);
  --rd:#E74C3C;
}
body{font-family:'DM Sans',sans-serif;background:#0f0f0f;display:flex;flex-direction:column;align-items:center;padding:24px 16px 110px;min-height:100vh}
.app-title{font-family:'Fraunces',serif;font-size:34px;font-weight:700;color:#FAF7F0;letter-spacing:-1px;margin-bottom:2px;text-align:center}
.app-title span{color:#D4A017}
.app-sub{color:#444;font-size:12px;margin-bottom:22px;text-align:center}

/* ── PHONE ── */
.phone{width:390px;min-height:820px;background:var(--cr);border-radius:50px;overflow:hidden;position:relative;box-shadow:0 40px 100px rgba(0,0,0,0.75),inset 0 0 0 1px rgba(255,255,255,0.05);display:none;flex-direction:column}
.phone.active{display:flex;animation:fu 0.25s ease}
@keyframes fu{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
.notch{position:absolute;top:0;left:50%;transform:translateX(-50%);width:124px;height:33px;background:#0f0f0f;border-radius:0 0 18px 18px;z-index:100}
.scr{flex:1;overflow-y:auto;overflow-x:hidden;padding-top:42px;scrollbar-width:none}
.scr::-webkit-scrollbar{display:none}

/* ── BOTTOM NAV ── */
.bnav{background:var(--ww);border-top:1px solid rgba(27,67,50,0.07);padding:10px 0 26px;display:flex;justify-content:space-around;flex-shrink:0}
.nvi{display:flex;flex-direction:column;align-items:center;gap:3px;cursor:pointer;opacity:0.30;transition:opacity 0.18s;position:relative}
.nvi.on{opacity:1}
.nvi-i{font-size:22px}
.nvi-l{font-size:9px;font-weight:700;color:var(--g);letter-spacing:0.04em}
.nbg{position:absolute;top:-3px;right:-4px;width:15px;height:15px;border-radius:50%;background:var(--rd);color:#fff;font-size:8px;font-weight:700;display:flex;align-items:center;justify-content:center;border:2px solid var(--ww)}

/* ── SWITCHER ── */
.sw{position:fixed;bottom:14px;left:50%;transform:translateX(-50%);display:flex;gap:5px;flex-wrap:wrap;justify-content:center;background:rgba(8,8,8,0.97);backdrop-filter:blur(20px);padding:9px 13px;border-radius:40px;border:1px solid rgba(255,255,255,0.07);z-index:9999;max-width:96vw}
.sb{padding:6px 11px;border-radius:26px;font-family:'DM Sans',sans-serif;font-size:10px;font-weight:700;border:none;cursor:pointer;color:rgba(255,255,255,0.35);background:transparent;transition:all 0.18s;white-space:nowrap}
.sb.on{background:var(--g);color:#fff;box-shadow:0 3px 10px rgba(27,67,50,0.5)}

/* ── COMMON ── */
.ph{padding:20px 20px 34px;position:relative;overflow:hidden}
.phg{background:linear-gradient(155deg,var(--g) 0%,var(--gm) 60%,var(--gl) 100%)}
.phb{background:linear-gradient(155deg,#5C3317 0%,#8B5E3C 100%)}
.phn{background:linear-gradient(155deg,#1A2E4A 0%,#2C4A6E 100%)}
.ph::before{content:'';position:absolute;top:-50px;right:-50px;width:180px;height:180px;border-radius:50%;background:rgba(212,160,23,0.09);pointer-events:none}
.bkr{display:flex;align-items:center;gap:10px;margin-bottom:16px}
.bk{width:34px;height:34px;border-radius:50%;background:rgba(255,255,255,0.13);display:flex;align-items:center;justify-content:center;color:#fff;font-size:15px;cursor:pointer;flex-shrink:0;border:none}
.ptl{font-family:'Fraunces',serif;color:#fff;font-size:24px;font-weight:700}
.psl{color:rgba(255,255,255,0.55);font-size:12px;margin-top:2px}
.card{background:var(--ww);border-radius:16px;border:1px solid rgba(27,67,50,0.07);box-shadow:var(--sh)}
.pbtn{width:100%;background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border:none;border-radius:14px;padding:16px;font-family:'DM Sans',sans-serif;font-size:15px;font-weight:700;cursor:pointer;box-shadow:0 6px 20px rgba(27,67,50,0.28);transition:transform 0.14s}
.pbtn:active{transform:scale(0.97)}
.sec{padding:16px 18px 0}
.sh{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
.st{font-size:14px;font-weight:700;color:var(--td)}
.sa{font-size:11px;color:var(--gl);font-weight:600;cursor:pointer}

/* ════════ LOCK ════════ */
#s-lock .scr{background:linear-gradient(160deg,var(--g) 0%,var(--gm) 50%,#0D2B1F 100%);display:flex;flex-direction:column;align-items:center;justify-content:center;padding:60px 28px 40px;min-height:100%}
.lk-logo{font-family:'Fraunces',serif;font-size:42px;font-weight:700;color:#fff;letter-spacing:-2px;margin-bottom:2px}
.lk-logo span{color:var(--au)}
.lk-sub{color:rgba(255,255,255,0.4);font-size:13px;margin-bottom:50px}
.lk-av{width:80px;height:80px;border-radius:50%;background:linear-gradient(135deg,var(--au),var(--al));display:flex;align-items:center;justify-content:center;font-size:30px;font-weight:700;color:var(--g);margin-bottom:14px;box-shadow:0 0 0 6px rgba(212,160,23,0.16),0 0 0 12px rgba(212,160,23,0.07)}
.lk-nm{color:#fff;font-size:20px;font-weight:700;margin-bottom:4px}
.lk-ct{color:rgba(255,255,255,0.42);font-size:13px;margin-bottom:44px}
.bio{width:76px;height:76px;border-radius:50%;background:rgba(255,255,255,0.09);border:2px solid rgba(255,255,255,0.16);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:5px;cursor:pointer;margin-bottom:22px;transition:all 0.2s}
.bio:hover{background:rgba(212,160,23,0.22);border-color:var(--au)}
.bio:active{transform:scale(0.95)}
.bio-i{font-size:28px}
.bio-l{color:rgba(255,255,255,0.52);font-size:10px;font-weight:700;letter-spacing:0.07em}
.pin-a{color:rgba(255,255,255,0.36);font-size:12px;cursor:pointer}
.pin-a strong{color:rgba(255,255,255,0.62)}
.off-p{margin-top:28px;background:rgba(255,255,255,0.07);border:1px solid rgba(255,255,255,0.1);border-radius:20px;padding:7px 14px;display:flex;align-items:center;gap:7px;color:rgba(255,255,255,0.52);font-size:11px}
.od{width:7px;height:7px;border-radius:50%;background:var(--al);flex-shrink:0}

/* ════════ HOME ════════ */
.bal-c{background:rgba(255,255,255,0.1);backdrop-filter:blur(10px);border:1px solid rgba(255,255,255,0.13);border-radius:18px;padding:16px 18px;position:relative;z-index:1}
.bal-l{color:rgba(255,255,255,0.58);font-size:11px;letter-spacing:0.07em;text-transform:uppercase;margin-bottom:3px}
.bal-a{font-family:'Fraunces',serif;color:#fff;font-size:34px;font-weight:700;letter-spacing:-1px}
.bal-s{color:rgba(255,255,255,0.45);font-size:12px;margin-top:2px}
.rb{position:absolute;top:12px;right:12px;background:var(--au);color:var(--g);font-size:10px;font-weight:700;padding:3px 9px;border-radius:16px}
.htop{display:flex;justify-content:space-between;align-items:center;margin-bottom:20px}
.hav{width:38px;height:38px;border-radius:50%;background:linear-gradient(135deg,var(--au),var(--al));display:flex;align-items:center;justify-content:center;font-size:14px;font-weight:700;color:var(--g);border:2px solid rgba(255,255,255,0.22);margin-left:8px}
.nb-b{width:36px;height:36px;border-radius:50%;background:rgba(255,255,255,0.11);display:flex;align-items:center;justify-content:center;font-size:15px;position:relative;cursor:pointer}
.nd{position:absolute;top:5px;right:5px;width:9px;height:9px;border-radius:50%;background:var(--rd);border:2px solid var(--g)}
.qas{display:flex;gap:9px;padding:0 16px;margin-top:-22px;position:relative;z-index:2;margin-bottom:4px}
.qa{flex:1;background:var(--ww);border-radius:14px;padding:12px 5px;display:flex;flex-direction:column;align-items:center;gap:5px;box-shadow:var(--sh);cursor:pointer;border:1px solid rgba(27,67,50,0.06);transition:transform 0.13s}
.qa:active{transform:scale(0.93)}
.qi{width:36px;height:36px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:16px}
.qi.s{background:linear-gradient(135deg,var(--g),var(--gl))}
.qi.p{background:linear-gradient(135deg,#7D3C98,#A569BD)}
.qi.g{background:linear-gradient(135deg,#1A5276,#2E86C1)}
.qi.f{background:linear-gradient(135deg,var(--au),var(--al))}
.ql{font-size:9px;font-weight:700;color:var(--tm);text-align:center;line-height:1.2}
.ai-tip{background:linear-gradient(135deg,var(--g),var(--gm));border-radius:16px;padding:14px 15px;display:flex;align-items:flex-start;gap:11px}
.ai-orb{width:34px;height:34px;border-radius:50%;flex-shrink:0;background:linear-gradient(135deg,var(--au),var(--al));display:flex;align-items:center;justify-content:center;font-size:14px}
.ai-ttl{color:rgba(255,255,255,0.55);font-size:9px;letter-spacing:0.07em;text-transform:uppercase;margin-bottom:2px}
.ai-tx{color:#fff;font-size:12px;line-height:1.5}
.ai-tx strong{color:var(--al)}
.yr-ban{background:linear-gradient(135deg,#1A2E4A,#2C4A6E);border-radius:16px;padding:14px 16px;display:flex;align-items:center;gap:12px;cursor:pointer}
.yr-ic{font-size:26px}
.yr-tt{color:#fff;font-size:13px;font-weight:700;margin-bottom:2px}
.yr-sb{color:rgba(255,255,255,0.5);font-size:11px}
.yr-ar{margin-left:auto;color:rgba(255,255,255,0.36);font-size:17px}
.tri{display:flex;align-items:center;gap:11px;padding:12px 0;border-bottom:1px solid rgba(27,67,50,0.07)}
.tri:last-child{border-bottom:none}
.tr-i{width:40px;height:40px;border-radius:12px;flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:17px}
.tr-i.ok{background:rgba(64,145,108,0.11)}
.tr-i.wt{background:rgba(212,160,23,0.11)}
.tr-inf{flex:1}
.tr-nm{font-size:13px;font-weight:600;color:var(--td);margin-bottom:2px}
.tr-dt{font-size:11px;color:var(--tl)}
.tr-am{text-align:right}
.tr-eu{font-size:13px;font-weight:700;color:var(--td);margin-bottom:1px}
.tr-gm{font-size:10px;color:var(--tl)}

/* ════════ NOTIFICATIONS ════════ */
.ng-l{font-size:10px;font-weight:700;color:var(--tl);letter-spacing:0.08em;text-transform:uppercase;margin:14px 0 8px;padding:0 16px}
.nit{background:var(--ww);border-radius:14px;padding:13px 14px;margin:0 16px 9px;display:flex;align-items:flex-start;gap:11px;border:1px solid rgba(27,67,50,0.07);box-shadow:var(--sh);position:relative}
.nit.u{border-color:rgba(27,67,50,0.14);background:#fff}
.nit.u::before{content:'';position:absolute;left:0;top:50%;transform:translateY(-50%);width:3px;height:55%;background:var(--gl);border-radius:0 3px 3px 0}
.nii{width:40px;height:40px;border-radius:12px;flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:17px}
.nig{background:rgba(64,145,108,0.11)}
.nia{background:rgba(212,160,23,0.11)}
.nib{background:rgba(36,113,163,0.11)}
.nir{background:rgba(231,76,60,0.09)}
.ni-t{font-size:13px;font-weight:600;color:var(--td);margin-bottom:2px}
.ni-b{font-size:11px;color:var(--tm);line-height:1.4}
.ni-m{font-size:10px;color:var(--tl);margin-top:3px}

/* ════════ SEND ════════ */
.rsl{font-size:10px;color:var(--tl);letter-spacing:0.07em;text-transform:uppercase;margin-bottom:10px;font-weight:600}
.rrow{display:flex;gap:9px;overflow-x:auto;padding-bottom:3px;scrollbar-width:none}
.rrow::-webkit-scrollbar{display:none}
.rc{display:flex;flex-direction:column;align-items:center;gap:4px;cursor:pointer;flex-shrink:0}
.rav{width:46px;height:46px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:17px;font-weight:700;border:2.5px solid transparent;transition:border-color 0.18s}
.rav.sel{border-color:var(--gl)}
.rv1{background:linear-gradient(135deg,var(--au),var(--al));color:var(--g)}
.rv2{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff}
.rv3{background:linear-gradient(135deg,#8B5E3C,#C4895B);color:#fff}
.rv4{background:rgba(27,67,50,0.08);color:var(--gl);font-size:20px}
.rn{font-size:10px;color:var(--tm);font-weight:500}
.amtr{display:flex;align-items:center;gap:9px;margin-bottom:12px}
.cur{background:var(--g);color:#fff;font-size:11px;font-weight:700;padding:7px 11px;border-radius:9px}
.ami{flex:1;font-family:'Fraunces',serif;font-size:32px;font-weight:700;color:var(--td);border:none;background:transparent;width:100%;outline:none}
.cvr{background:rgba(27,67,50,0.05);border-radius:11px;padding:10px 13px;display:flex;align-items:center;justify-content:space-between}
.cv-l{font-size:11px;color:var(--tl)}
.cv-a{font-size:15px;font-weight:700;color:var(--g)}
.cv-r{font-size:10px;color:var(--tl);text-align:right}
.ral{background:rgba(212,160,23,0.08);border:1px solid rgba(212,160,23,0.2);border-radius:11px;padding:10px 13px;display:flex;align-items:center;gap:9px;margin-bottom:14px}
.ral-t{font-size:11px;color:var(--tm);line-height:1.4}
.ral-t strong{color:#B8860B}
.dop{display:flex;align-items:center;gap:11px;padding:11px 13px;border-radius:11px;margin-bottom:7px;border:1px solid rgba(27,67,50,0.1);cursor:pointer;transition:all 0.18s}
.dop.sel{border-color:var(--gl);background:rgba(64,145,108,0.05)}
.di{font-size:18px}
.dn{font-size:12px;font-weight:600;color:var(--td)}
.ds{font-size:10px;color:var(--tl)}
.dc{margin-left:auto;color:var(--gl);font-size:17px}
.vcs{display:flex;align-items:center;gap:11px;padding:13px 15px}
.vcb{width:44px;height:44px;border-radius:50%;background:linear-gradient(135deg,var(--g),var(--gl));display:flex;align-items:center;justify-content:center;font-size:17px;cursor:pointer;flex-shrink:0;box-shadow:0 4px 10px rgba(27,67,50,0.28)}
.vcl{font-size:12px;font-weight:600;color:var(--td);margin-bottom:2px}
.vcs2{font-size:10px;color:var(--tl)}

/* ════════ CONFIRM ════════ */
#s-confirm .scr{background:linear-gradient(160deg,var(--g),var(--gm));display:flex;flex-direction:column;align-items:center;justify-content:center;padding:40px 28px;min-height:100%}
@keyframes pop{0%{transform:scale(0.5)}70%{transform:scale(1.15)}100%{transform:scale(1)}}
.conf-ic{font-size:64px;margin-bottom:20px;animation:pop 0.5s ease}
.conf-t{font-family:'Fraunces',serif;color:#fff;font-size:28px;font-weight:700;margin-bottom:8px;text-align:center}
.conf-s{color:rgba(255,255,255,0.62);font-size:13px;text-align:center;line-height:1.6;margin-bottom:28px}
.conf-box{background:rgba(255,255,255,0.1);border:1px solid rgba(255,255,255,0.14);border-radius:16px;padding:18px 20px;width:100%;margin-bottom:22px}
.conf-row{display:flex;justify-content:space-between;margin-bottom:10px}
.conf-row:last-child{margin-bottom:0}
.conf-lbl{color:rgba(255,255,255,0.58);font-size:12px}
.conf-val{color:#fff;font-weight:700;font-size:13px}
.conf-val.gold{color:var(--al)}

/* ════════ MESSAGES ════════ */
.cvi{display:flex;align-items:center;gap:12px;padding:13px 16px;border-bottom:1px solid rgba(27,67,50,0.07);cursor:pointer;transition:background 0.15s}
.cvi:hover{background:rgba(27,67,50,0.03)}
.cva{width:48px;height:48px;border-radius:50%;flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:19px;font-weight:700}
.ca1{background:linear-gradient(135deg,var(--au),var(--al));color:var(--g)}
.ca2{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff}
.ca3{background:linear-gradient(135deg,#8B5E3C,#C4895B);color:#fff}
.cvinf{flex:1;min-width:0}
.cvnm{font-size:13px;font-weight:700;color:var(--td);margin-bottom:2px}
.cvpv{font-size:11px;color:var(--tl);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.cvmt{text-align:right;flex-shrink:0}
.cvtm{font-size:10px;color:var(--tl);margin-bottom:4px}
.ubd{background:var(--g);color:#fff;font-size:9px;font-weight:700;width:17px;height:17px;border-radius:50%;display:flex;align-items:center;justify-content:center;margin-left:auto}

/* ════════ CHAT ════════ */
.chat-hd{display:flex;align-items:center;gap:11px;padding:16px 18px;background:linear-gradient(135deg,var(--g),var(--gm));flex-shrink:0}
.cha{width:40px;height:40px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:17px;font-weight:700;flex-shrink:0}
.chnm{color:#fff;font-size:14px;font-weight:700}
.chst{color:rgba(255,255,255,0.55);font-size:11px}
.chat-area{flex:1;overflow-y:auto;padding:14px;background:var(--cr);scrollbar-width:none}
.chat-area::-webkit-scrollbar{display:none}
.bbl{max-width:78%;margin-bottom:12px}
.bbl.me{margin-left:auto}
.bbl.th{margin-right:auto}
.bbl-in{padding:10px 13px;border-radius:16px;font-size:12px;line-height:1.55}
.bbl.th .bbl-in{background:var(--ww);color:var(--td);border-radius:4px 16px 16px 16px;box-shadow:var(--sh);border:1px solid rgba(27,67,50,0.07)}
.bbl.me .bbl-in{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border-radius:16px 4px 16px 16px}
.bbl-tm{font-size:9px;color:var(--tl);margin-top:3px;padding:0 3px}
.bbl.me .bbl-tm{text-align:right}
.tr-bbl{background:var(--ww);border:1px solid rgba(27,67,50,0.1);border-radius:12px;padding:11px 13px;display:flex;align-items:center;gap:9px;margin-bottom:12px;max-width:78%;margin-left:auto;box-shadow:var(--sh)}
.tb-a{font-size:14px;font-weight:700;color:var(--g)}
.tb-s{font-size:10px;color:var(--tl)}
.cin-row{padding:9px 12px 18px;background:var(--ww);border-top:1px solid rgba(27,67,50,0.07);display:flex;gap:8px;align-items:center;flex-shrink:0}
.cin{flex:1;background:rgba(27,67,50,0.06);border:none;border-radius:22px;padding:10px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--td);outline:none}
.csnd{width:40px;height:40px;border-radius:50%;background:var(--g);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0;color:#fff}

/* ════════ AI ════════ */
.lang-t{display:flex;gap:6px;flex-wrap:wrap;margin-top:12px}
.lt{padding:5px 12px;border-radius:18px;font-size:11px;font-weight:600;border:1px solid rgba(255,255,255,0.18);color:rgba(255,255,255,0.52);cursor:pointer;transition:all 0.18s}
.lt.on{background:var(--au);border-color:var(--au);color:var(--g)}
.ai-msgs{flex:1;overflow-y:auto;padding:14px;scrollbar-width:none}
.ai-msgs::-webkit-scrollbar{display:none}
.msg{max-width:80%;margin-bottom:12px}
.msg.ai{margin-right:auto}
.msg.us{margin-left:auto}
.msg-bbl{padding:11px 14px;border-radius:16px;font-size:12px;line-height:1.55}
.msg.ai .msg-bbl{background:var(--ww);color:var(--td);border-radius:4px 16px 16px 16px;box-shadow:var(--sh);border:1px solid rgba(27,67,50,0.07)}
.msg.us .msg-bbl{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border-radius:16px 4px 16px 16px}
.msg-tm{font-size:9px;color:var(--tl);margin-top:3px;padding:0 3px}
.msg.us .msg-tm{text-align:right}
.typing{display:flex;align-items:center;gap:4px;padding:10px 14px;background:var(--ww);border-radius:4px 16px 16px 16px;width:fit-content;box-shadow:var(--sh);border:1px solid rgba(27,67,50,0.07);margin-bottom:12px}
.typing span{width:7px;height:7px;border-radius:50%;background:var(--gl);animation:bn 1.2s infinite}
.typing span:nth-child(2){animation-delay:0.2s}
.typing span:nth-child(3){animation-delay:0.4s}
@keyframes bn{0%,80%,100%{transform:scale(0.7);opacity:0.5}40%{transform:scale(1);opacity:1}}
.chips{display:flex;flex-wrap:wrap;gap:7px;padding:0 14px 12px}
.chip{background:rgba(27,67,50,0.07);color:var(--g);padding:7px 12px;border-radius:18px;font-size:11px;font-weight:500;cursor:pointer;border:1px solid rgba(27,67,50,0.1)}
.chip:active{background:rgba(27,67,50,0.14)}
.ai-in-row{padding:9px 12px 16px;background:var(--ww);border-top:1px solid rgba(27,67,50,0.07);display:flex;gap:8px;align-items:center;flex-shrink:0}
.ai-in{flex:1;background:rgba(27,67,50,0.06);border:none;border-radius:22px;padding:11px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--td);outline:none}
.ai-snd{width:40px;height:40px;border-radius:50%;background:var(--g);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0;color:#fff}

/* ════════ FAMILY ════════ */
.tot-s{text-align:center;padding:18px;background:rgba(27,67,50,0.04);border-radius:14px;margin-bottom:18px}
.tot-l{font-size:10px;color:var(--tl);letter-spacing:0.07em;text-transform:uppercase;margin-bottom:4px}
.tot-a{font-family:'Fraunces',serif;font-size:32px;font-weight:700;color:var(--g)}
.tot-s2{font-size:11px;color:var(--tl);margin-top:2px}
.mc{background:var(--ww);border:1px solid rgba(27,67,50,0.09);border-radius:14px;padding:13px;margin-bottom:10px;box-shadow:0 2px 10px rgba(27,67,50,0.05)}
.mt{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.mav{width:42px;height:42px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:17px;font-weight:700;flex-shrink:0}
.m1{background:linear-gradient(135deg,var(--au),var(--al));color:var(--g)}
.m2{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff}
.m3{background:linear-gradient(135deg,#8B5E3C,#C4895B);color:#fff}
.mnm{font-size:13px;font-weight:700;color:var(--td)}
.mrl{font-size:10px;color:var(--tl);margin-top:1px}
.msnt{margin-left:auto;text-align:right}
.ms{font-size:14px;font-weight:700;color:var(--g)}
.md{font-size:10px;color:var(--tl);margin-top:1px}
.pb{background:rgba(27,67,50,0.09);border-radius:4px;height:5px}
.pf{height:5px;border-radius:4px;background:linear-gradient(90deg,var(--g),var(--gl))}
.pl{display:flex;justify-content:space-between;margin-top:4px}
.pt{font-size:10px;color:var(--tl)}
.req-c{background:rgba(212,160,23,0.08);border:1px solid rgba(212,160,23,0.2);border-radius:13px;padding:12px 14px;margin-bottom:10px;display:flex;align-items:center;gap:10px}
.rs-btn{background:var(--g);color:#fff;font-size:11px;font-weight:700;padding:6px 12px;border-radius:9px;white-space:nowrap;cursor:pointer;border:none}
.add-m{width:100%;border:2px dashed rgba(27,67,50,0.16);border-radius:14px;padding:13px;background:none;cursor:pointer;color:var(--gl);font-size:12px;font-weight:600;display:flex;align-items:center;justify-content:center;gap:7px}

/* ════════ YEARLY ════════ */
.bs{text-align:center;padding:22px 18px 18px}
.bsl{font-size:11px;color:var(--tl);letter-spacing:0.07em;text-transform:uppercase;margin-bottom:6px}
.bsn{font-family:'Fraunces',serif;font-size:48px;font-weight:700;color:var(--g);letter-spacing:-2px}
.bss{font-size:13px;color:var(--tm);margin-top:4px}
.bsb{display:inline-block;background:var(--gp);color:var(--g);font-size:11px;font-weight:700;padding:4px 13px;border-radius:18px;margin-top:8px}
.sg{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:18px}
.sc{background:var(--ww);border-radius:13px;padding:14px 13px;border:1px solid rgba(27,67,50,0.07);box-shadow:var(--sh)}
.sci{font-size:18px;margin-bottom:6px}
.scn{font-family:'Fraunces',serif;font-size:20px;font-weight:700;color:var(--td);margin-bottom:1px}
.scl{font-size:10px;color:var(--tl)}
.mc-w{background:var(--ww);border-radius:16px;padding:14px;margin-bottom:18px;border:1px solid rgba(27,67,50,0.07)}
.ct{font-size:12px;font-weight:700;color:var(--td);margin-bottom:12px}
.cbrs{display:flex;align-items:flex-end;gap:5px;height:72px}
.bc{flex:1;display:flex;flex-direction:column;align-items:center;gap:3px}
.br{width:100%;border-radius:3px 3px 0 0;background:rgba(27,67,50,0.13)}
.br.hi{background:linear-gradient(180deg,var(--gl),var(--g))}
.bm{font-size:8px;color:var(--tl);font-weight:600}
.shr{width:100%;background:linear-gradient(135deg,#1A2E4A,#2C4A6E);color:#fff;border:none;border-radius:14px;padding:14px;font-family:'DM Sans',sans-serif;font-size:14px;font-weight:700;cursor:pointer;display:flex;align-items:center;justify-content:center;gap:9px}

/* ════════ COMMUNITY ════════ */
.loc-t{display:inline-flex;align-items:center;gap:5px;background:rgba(255,255,255,0.1);border-radius:18px;padding:4px 11px;margin-top:8px;color:rgba(255,255,255,0.72);font-size:11px}
.cm-tabs{display:flex;background:rgba(0,0,0,0.17);padding:3px;border-radius:11px;margin:12px 0 0}
.cmt{flex:1;padding:7px 3px;text-align:center;border-radius:9px;font-size:10px;font-weight:700;color:rgba(255,255,255,0.42);cursor:pointer;transition:all 0.18s}
.cmt.on{background:#fff;color:var(--td)}
.cm-body{padding:16px;background:var(--cr)}
.p-row{display:flex;gap:10px;overflow-x:auto;padding-bottom:3px;scrollbar-width:none;margin-bottom:20px}
.p-row::-webkit-scrollbar{display:none}
.pc{flex-shrink:0;width:82px;background:var(--ww);border-radius:14px;padding:12px 7px;text-align:center;box-shadow:var(--sh);border:1px solid rgba(27,67,50,0.07)}
.pav{width:42px;height:42px;border-radius:50%;margin:0 auto 6px;display:flex;align-items:center;justify-content:center;font-size:16px;font-weight:700}
.p1{background:linear-gradient(135deg,var(--au),var(--al));color:var(--g)}
.p2{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff}
.p3{background:linear-gradient(135deg,#8B5E3C,#C4895B);color:#fff}
.p4{background:linear-gradient(135deg,#2980B9,#5DADE2);color:#fff}
.pnm{font-size:10px;font-weight:600;color:var(--td);margin-bottom:1px}
.pct{font-size:9px;color:var(--tl)}
.pol{width:6px;height:6px;border-radius:50%;background:#2ECC71;margin:3px auto 0}
.nwi{background:var(--ww);border-radius:14px;padding:13px;margin-bottom:10px;box-shadow:var(--sh);border:1px solid rgba(27,67,50,0.07)}
.ntag{display:inline-block;padding:2px 8px;border-radius:18px;font-size:9px;font-weight:700;letter-spacing:0.06em;text-transform:uppercase;margin-bottom:6px}
.tn{background:rgba(41,128,185,0.1);color:#2980B9}
.te{background:rgba(212,160,23,0.12);color:#B8860B}
.tj{background:rgba(46,204,113,0.1);color:#27AE60}
.n-tt{font-size:12px;font-weight:700;color:var(--td);margin-bottom:4px;line-height:1.3}
.n-mt{font-size:10px;color:var(--tl);display:flex;align-items:center;gap:6px}
.ndot{width:3px;height:3px;border-radius:50%;background:var(--tl)}

@media(max-width:430px){body{padding:12px 0 100px}.phone{width:100vw;border-radius:0}.sw{left:6px;right:6px;transform:none;border-radius:20px}}

/* ════════ BILLS ════════ */
#s-bills .ph{background:linear-gradient(155deg,#5B2C8D 0%,#8E44AD 100%)}
.bill-card{background:var(--ww);border-radius:16px;border:1px solid rgba(27,67,50,0.07);box-shadow:var(--sh);padding:16px;margin-bottom:14px}
.bill-head{display:flex;align-items:center;gap:12px;margin-bottom:14px}
.bill-icon{width:42px;height:42px;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:20px;flex-shrink:0}
.bill-title{font-size:14px;font-weight:700;color:var(--td)}
.bill-sub{font-size:11px;color:var(--tl);margin-top:1px}
.bill-field{margin-bottom:10px}
.bill-lbl{font-size:10px;font-weight:700;color:var(--tl);letter-spacing:0.06em;text-transform:uppercase;display:block;margin-bottom:5px}
.bill-inp{width:100%;background:rgba(27,67,50,0.05);border:1.5px solid rgba(27,67,50,0.1);border-radius:10px;padding:10px 13px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--td);outline:none;transition:border-color 0.18s}
.bill-inp:focus{border-color:var(--gl)}
.bill-sel{width:100%;background:rgba(27,67,50,0.05);border:1.5px solid rgba(27,67,50,0.1);border-radius:10px;padding:10px 13px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--td);outline:none;cursor:pointer}
.bill-pay{width:100%;background:linear-gradient(135deg,#7D3C98,#A569BD);color:#fff;border:none;border-radius:11px;padding:12px;font-family:'DM Sans',sans-serif;font-size:13px;font-weight:700;cursor:pointer;margin-top:4px;box-shadow:0 4px 14px rgba(125,60,152,0.25);transition:transform 0.14s}
.bill-pay:active{transform:scale(0.97)}
.net-row{display:flex;gap:8px;margin-bottom:10px}
.net-btn{flex:1;padding:8px 4px;border-radius:10px;font-size:11px;font-weight:700;border:2px solid rgba(27,67,50,0.12);background:none;cursor:pointer;color:var(--tm);transition:all 0.18s;font-family:'DM Sans',sans-serif;text-align:center}
.net-btn.on{border-color:#7D3C98;background:rgba(125,60,152,0.07);color:#7D3C98}
#s-billconf .scr{background:linear-gradient(160deg,#5B2C8D,#8E44AD);display:flex;flex-direction:column;align-items:center;justify-content:center;padding:40px 28px;min-height:100%}

/* ════════ COUNTRY TOGGLE ════════ */
.ctry-btn{flex:1;padding:8px 6px;border-radius:10px;font-size:11px;font-weight:700;border:2px solid rgba(27,67,50,0.12);background:none;cursor:pointer;color:var(--tm);transition:all 0.18s;font-family:'DM Sans',sans-serif}
.ctry-btn.on{border-color:var(--gl);background:rgba(27,67,50,0.06);color:var(--g)}

/* ════════ JOBS ════════ */
.job-search{width:100%;background:rgba(27,67,50,0.05);border:1.5px solid rgba(27,67,50,0.1);border-radius:12px;padding:10px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--td);outline:none;margin-bottom:12px;transition:border-color 0.18s}
.job-search:focus{border-color:var(--gl)}
.jfilt-row{display:flex;gap:7px;margin-bottom:14px;overflow-x:auto;scrollbar-width:none;padding-bottom:2px}
.jfilt-row::-webkit-scrollbar{display:none}
.jfilt-btn{padding:6px 13px;border-radius:18px;font-size:11px;font-weight:700;border:1.5px solid rgba(27,67,50,0.14);background:none;cursor:pointer;color:var(--tm);white-space:nowrap;font-family:'DM Sans',sans-serif;transition:all 0.18s;flex-shrink:0}
.jfilt-btn.on{background:var(--g);color:#fff;border-color:var(--g)}
.job-card{background:var(--ww);border-radius:14px;border:1px solid rgba(27,67,50,0.08);box-shadow:var(--sh);padding:14px;margin-bottom:11px}
.jctag{display:inline-block;padding:2px 8px;border-radius:18px;font-size:9px;font-weight:700;letter-spacing:0.05em;text-transform:uppercase;margin-bottom:8px}
.jtag-gm{background:rgba(27,67,50,0.08);color:var(--g)}
.jtag-sn{background:rgba(39,174,96,0.1);color:#1e8449}
.jtag-rm{background:rgba(41,128,185,0.1);color:#1a5276}
.job-ttl{font-size:14px;font-weight:700;color:var(--td);margin-bottom:2px}
.job-co{font-size:12px;color:var(--tm);margin-bottom:7px}
.job-meta{display:flex;align-items:center;gap:8px;flex-wrap:wrap;margin-bottom:10px}
.job-loc{font-size:11px;color:var(--tl)}
.job-sal{font-size:11px;font-weight:700;color:var(--g);background:rgba(27,67,50,0.07);padding:3px 9px;border-radius:8px}
.job-foot{display:flex;align-items:center;justify-content:space-between}
.job-date{font-size:10px;color:var(--tl)}
.apply-btn{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border:none;border-radius:9px;padding:7px 16px;font-family:'DM Sans',sans-serif;font-size:11px;font-weight:700;cursor:pointer;transition:transform 0.13s;box-shadow:0 3px 10px rgba(27,67,50,0.22)}
.apply-btn:active{transform:scale(0.94)}
.apply-btn:disabled{opacity:0.55;cursor:default;transform:none}
/* ════════ BUSINESSES ════════ */
.biz-card{background:var(--ww);border-radius:14px;border:1px solid rgba(27,67,50,0.08);box-shadow:var(--sh);padding:14px;margin-bottom:11px;position:relative}
.diaspora-badge{display:inline-flex;align-items:center;gap:4px;background:linear-gradient(135deg,var(--au),var(--al));color:var(--g);font-size:9px;font-weight:700;padding:2px 8px;border-radius:18px;letter-spacing:0.04em;margin-bottom:7px}
.biz-name{font-size:14px;font-weight:700;color:var(--td);margin-bottom:2px}
.biz-cat{display:inline-block;padding:2px 8px;border-radius:18px;font-size:9px;font-weight:700;text-transform:uppercase;letter-spacing:0.05em;background:rgba(27,67,50,0.07);color:var(--g);margin-bottom:7px}
.biz-meta{display:flex;align-items:center;gap:9px;flex-wrap:wrap;margin-bottom:6px}
.biz-loc{font-size:11px;color:var(--tl)}
.biz-phone{font-size:11px;color:var(--gl);font-weight:600}
.biz-desc{font-size:11px;color:var(--tm);line-height:1.5;margin-bottom:10px}
.contact-btn{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border:none;border-radius:9px;padding:7px 16px;font-family:'DM Sans',sans-serif;font-size:11px;font-weight:700;cursor:pointer;transition:transform 0.13s;box-shadow:0 3px 10px rgba(27,67,50,0.22)}
.contact-btn:active{transform:scale(0.94)}
.contact-btn:disabled{opacity:0.55;cursor:default;transform:none}

.apply-toast{position:absolute;bottom:82px;left:14px;right:14px;background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border-radius:14px;padding:13px 16px;z-index:200;box-shadow:0 8px 24px rgba(27,67,50,0.4);animation:fu 0.25s ease;pointer-events:none}
.apply-toast-t{font-weight:700;font-size:13px;margin-bottom:2px}
.apply-toast-s{font-size:11px;opacity:0.75}

/* ════════ ONBOARDING ════════ */
#s-onboard .scr{background:linear-gradient(160deg,var(--g) 0%,var(--gm) 50%,#0D2B1F 100%);display:flex;flex-direction:column;align-items:center;justify-content:center;padding:60px 28px 40px;min-height:100%}
.ob-opt{width:100%;background:rgba(255,255,255,0.1);border:2px solid rgba(255,255,255,0.18);border-radius:16px;padding:18px 20px;display:flex;align-items:center;gap:14px;cursor:pointer;transition:all 0.2s;margin-bottom:14px;font-family:'DM Sans',sans-serif}
.ob-opt:active{transform:scale(0.97)}
.ob-opt:hover{border-color:var(--au);background:rgba(212,160,23,0.12)}
.ob-flag{font-size:28px;flex-shrink:0}
.ob-nm{color:#fff;font-size:16px;font-weight:700;text-align:left;margin-bottom:2px}
.ob-sb{color:rgba(255,255,255,0.52);font-size:11px;text-align:left}
.ob-ar{margin-left:auto;color:rgba(255,255,255,0.36);font-size:18px}

/* ════════ INVEST ════════ */
.inv-trust{background:linear-gradient(135deg,rgba(27,67,50,0.07),rgba(64,145,108,0.07));border:1px solid rgba(27,67,50,0.13);border-radius:13px;padding:12px 14px;font-size:12px;color:var(--tm);line-height:1.5;display:flex;align-items:flex-start;gap:9px}
.inv-cat-hd{font-size:14px;font-weight:700;color:var(--td);margin:18px 0 10px}
.inv-card{background:var(--ww);border-radius:14px;border:1px solid rgba(27,67,50,0.08);box-shadow:var(--sh);padding:14px;margin-bottom:11px}
.verified-badge{display:inline-flex;align-items:center;gap:4px;background:rgba(27,67,50,0.08);color:var(--g);font-size:9px;font-weight:700;padding:2px 8px;border-radius:18px;letter-spacing:0.04em;margin-bottom:7px}
.inv-title{font-size:14px;font-weight:700;color:var(--td);margin-bottom:4px}
.inv-meta{font-size:11px;color:var(--tl);margin-bottom:8px}
.inv-price{font-size:17px;font-weight:700;color:var(--g);font-family:'Fraunces',serif;margin-bottom:10px}
.inv-stats{display:flex;gap:8px;margin:8px 0 10px}
.inv-stat{flex:1;background:rgba(27,67,50,0.05);border-radius:9px;padding:8px 10px}
.inv-stat-l{font-size:9px;color:var(--tl);font-weight:700;text-transform:uppercase;letter-spacing:0.05em;margin-bottom:2px}
.inv-stat-v{font-size:13px;font-weight:700;color:var(--td)}
.inv-stat-v.ret{color:var(--g)}
.inv-desc{font-size:11px;color:var(--tm);line-height:1.5;margin-bottom:10px}
.inv-btn{background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border:none;border-radius:9px;padding:7px 16px;font-family:'DM Sans',sans-serif;font-size:11px;font-weight:700;cursor:pointer;transition:transform 0.13s;box-shadow:0 3px 10px rgba(27,67,50,0.22)}
.inv-btn:active{transform:scale(0.94)}
.inv-btn:disabled{opacity:0.55;cursor:default;transform:none}
.invest-toast{position:absolute;bottom:82px;left:14px;right:14px;background:linear-gradient(135deg,var(--g),var(--gl));color:#fff;border-radius:14px;padding:13px 16px;z-index:200;box-shadow:0 8px 24px rgba(27,67,50,0.4);animation:fu 0.25s ease;pointer-events:none}
</style>
</head>
<body>

<div class="app-title">Dal<span>asi</span></div>
<div class="app-sub">Functional Demo · AI is live · Tap the bar below to navigate</div>

<!-- ══ ONBOARDING ══ -->
<div class="phone active" id="s-onboard">
  <div class="notch"></div>
  <div class="scr">
    <div class="lk-logo">Dal<span>asi</span></div>
    <div style="color:rgba(255,255,255,0.45);font-size:13px;margin-bottom:48px;text-align:center">Home for every West African 🌍</div>
    <div style="color:#fff;font-size:20px;font-weight:700;margin-bottom:8px;text-align:center;font-family:'Fraunces',serif">Where are you from?</div>
    <div style="color:rgba(255,255,255,0.42);font-size:12px;margin-bottom:28px;text-align:center">This sets your default currency and language</div>
    <button class="ob-opt" onclick="selectCountry('gambia')">
      <span class="ob-flag">🇬🇲</span>
      <div><div class="ob-nm">I'm Gambian</div><div class="ob-sb">Send GMD · Wave, Bank & APS</div></div>
      <span class="ob-ar">›</span>
    </button>
    <button class="ob-opt" onclick="selectCountry('senegal')">
      <span class="ob-flag">🇸🇳</span>
      <div><div class="ob-nm">I'm Senegalese</div><div class="ob-sb">Send XOF · Wave & Orange Money</div></div>
      <span class="ob-ar">›</span>
    </button>
  </div>
</div>

<!-- ══ LOCK ══ -->
<div class="phone" id="s-lock">
  <div class="notch"></div>
  <div class="scr">
    <div class="lk-logo">Dal<span>asi</span></div>
    <div class="lk-sub">Home for every Gambian</div>
    <div class="lk-av">B</div>
    <div class="lk-nm">Buba Jallow</div>
    <div class="lk-ct">Vienna, Austria 🇦🇹</div>
    <div class="bio" onclick="go('home')">
      <div class="bio-i">👆</div>
      <div class="bio-l">TOUCH ID</div>
    </div>
    <div class="pin-a">or <strong>Enter PIN</strong></div>
    <div class="off-p"><div class="od"></div>Wallet available offline · Last synced 2 min ago</div>
  </div>
</div>

<!-- ══ HOME ══ -->
<div class="phone" id="s-home">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phg" style="padding-bottom:46px">
      <div class="htop">
        <div><div style="color:rgba(255,255,255,0.62);font-size:12px">Salamu alaikum 👋</div><div style="color:#fff;font-size:18px;font-weight:700">Buba</div></div>
        <div style="display:flex;align-items:center">
          <div class="nb-b" onclick="go('notifs')">🔔<div class="nd"></div></div>
          <div class="hav">B</div>
        </div>
      </div>
      <div class="bal-c">
        <div class="rb">🟢 Good Rate</div>
        <div class="bal-l">Sent This Month</div>
        <div class="bal-a">€340</div>
        <div class="bal-s">GMD 27,064 received by family</div>
      </div>
    </div>
    <div class="qas">
      <div class="qa" onclick="go('send')"><div class="qi s">💸</div><div class="ql">Send Money</div></div>
      <div class="qa" onclick="go('bills')"><div class="qi p">⚡</div><div class="ql">Pay Bills</div></div>
      <div class="qa" onclick="go('invest')"><div class="qi g">📈</div><div class="ql">Invest</div></div>
      <div class="qa" onclick="go('family')"><div class="qi f">👨‍👩‍👧</div><div class="ql">Family</div></div>
    </div>
    <div class="sec" style="margin-top:16px">
      <div class="ai-tip">
        <div class="ai-orb">✨</div>
        <div><div class="ai-ttl">Dalasi AI · Rate Alert</div><div class="ai-tx">EUR/GMD is <strong>79.6</strong> today — best in 11 days. Good time to send.</div></div>
      </div>
    </div>
    <div class="sec" style="margin-top:12px">
      <div class="yr-ban" onclick="go('yearly')">
        <div class="yr-ic">📊</div>
        <div><div class="yr-tt">Your 2025 Summary</div><div class="yr-sb">€3,840 sent · 47 transfers</div></div>
        <div class="yr-ar">›</div>
      </div>
    </div>
    <div class="sec" style="margin-top:18px">
      <div class="sh"><div class="st">Recent Transfers</div><div class="sa">See all</div></div>
      <div class="tri"><div class="tr-i ok">👵🏾</div><div class="tr-inf"><div class="tr-nm">Mama Fatoumata</div><div class="tr-dt">Today · Cash Power + food</div></div><div class="tr-am"><div class="tr-eu">€120</div><div class="tr-gm">GMD 9,552 ✓</div></div></div>
      <div class="tri"><div class="tr-i ok">👦🏾</div><div class="tr-inf"><div class="tr-nm">Lamin (brother)</div><div class="tr-dt">Yesterday · School fees</div></div><div class="tr-am"><div class="tr-eu">€85</div><div class="tr-gm">GMD 6,766 ✓</div></div></div>
      <div class="tri"><div class="tr-i wt">👧🏾</div><div class="tr-inf"><div class="tr-nm">Aminata (sister)</div><div class="tr-dt">Apr 10 · Monthly support</div></div><div class="tr-am"><div class="tr-eu">€135</div><div class="tr-gm" style="color:var(--au)">Pending ⏳</div></div></div>
    </div>
    <div style="height:32px"></div>
  </div>
  <div class="bnav">
    <div class="nvi on"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div><div class="nbg">2</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ NOTIFICATIONS ══ -->
<div class="phone" id="s-notifs">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phg"><div class="bkr"><button class="bk" onclick="go('home')">←</button><div><div class="ptl">Notifications</div><div class="psl">3 new alerts</div></div></div></div>
    <div class="ng-l">Today</div>
    <div class="nit u"><div class="nii nig">✅</div><div><div class="ni-t">Mama received your money</div><div class="ni-b">€120 → GMD 9,552 to Wave wallet. She also received your voice note.</div><div class="ni-m">2 hours ago</div></div></div>
    <div class="nit u"><div class="nii nia">📩</div><div><div class="ni-t">New request from Mama</div><div class="ni-b">"School fees for Abdou — GMD 3,500 needed by Friday"</div><div class="ni-m">4 hours ago</div></div></div>
    <div class="nit u"><div class="nii nib">⚡</div><div><div class="ni-t">Rate alert — Best this week</div><div class="ni-b">EUR/GMD hit 79.6 — best in 11 days. Good time to send.</div><div class="ni-m">6 hours ago</div></div></div>
    <div class="ng-l">Yesterday</div>
    <div class="nit"><div class="nii nig">✅</div><div><div class="ni-t">Lamin received school fees</div><div class="ni-b">€85 → GMD 6,766 delivered to GTBank.</div><div class="ni-m">Yesterday · 14:32</div></div></div>
    <div class="nit"><div class="nii nib">🌍</div><div><div class="ni-t">Community event near you</div><div class="ni-b">Gambia Community Day Vienna — May 18, Prater Park. 142 attending.</div><div class="ni-m">Yesterday · 09:15</div></div></div>
    <div class="nit"><div class="nii nir">🔐</div><div><div class="ni-t">New device login</div><div class="ni-b">Account accessed from a new iPhone in Vienna. Was this you?</div><div class="ni-m">Yesterday · 08:47</div></div></div>
    <div style="height:32px"></div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ SEND ══ -->
<div class="phone" id="s-send">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phg"><div class="bkr"><button class="bk" onclick="go('home')">←</button><div><div class="ptl">Send Money</div><div class="psl" id="send-subtitle">Worldwide → The Gambia</div></div></div></div>
    <div style="padding:16px">
      <div style="display:flex;gap:8px;margin-bottom:14px">
        <button class="ctry-btn on" id="btn-gambia" onclick="setCountry('gambia')">🇬🇲 Gambia (GMD)</button>
        <button class="ctry-btn" id="btn-senegal" onclick="setCountry('senegal')">🇸🇳 Senegal (XOF)</button>
      </div>
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="rsl">Send To</div>
        <div class="rrow">
          <div class="rc"><div class="rav rv1 sel">👵🏾</div><div class="rn">Mama</div></div>
          <div class="rc"><div class="rav rv2">L</div><div class="rn">Lamin</div></div>
          <div class="rc"><div class="rav rv3">A</div><div class="rn">Aminata</div></div>
          <div class="rc"><div class="rav rv4">+</div><div class="rn">Add</div></div>
        </div>
      </div>
      <div class="card" style="padding:18px 16px;margin-bottom:14px">
        <div class="amtr"><div class="cur">EUR €</div><input class="ami" type="number" value="200" id="ami"/></div>
        <div class="cvr"><div><div class="cv-l">Mama receives</div><div class="cv-a" id="gmd">GMD 15,920</div></div><div><div class="cv-r" id="rate-label">Rate: 79.6</div><div class="cv-r">Fee: €0.99</div><div class="cv-r" style="margin-top:3px"><span id="rate-badge" style="display:none;background:#D8F3DC;color:#1B4332;font-size:9px;font-weight:700;padding:2px 6px;border-radius:7px;letter-spacing:0.04em">🟢 Live</span></div></div></div>
      </div>
      <div class="ral" id="rate-alert"><span style="font-size:16px">⚡</span><div class="ral-t"><strong>Great rate right now.</strong> Sending today saves ~GMD 400 vs. yesterday.</div></div>
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="rsl">Delivery Method</div>
        <div id="delivery-methods">
          <div class="dop sel"><div class="di">📱</div><div><div class="dn">Wave Wallet</div><div class="ds">Instant · Free</div></div><div class="dc">✓</div></div>
          <div class="dop"><div class="di">🏦</div><div><div class="dn">Bank Deposit</div><div class="ds">1–2 hours</div></div></div>
          <div class="dop"><div class="di">💵</div><div><div class="dn">Cash Pickup</div><div class="ds">APS branches · Same day</div></div></div>
        </div>
      </div>
      <div class="card vcs" style="margin-bottom:16px">
        <div class="vcb">🎙️</div>
        <div><div class="vcl">Add a voice note</div><div class="vcs2">Send a message with your money</div></div>
      </div>
      <button class="pbtn" id="sbtn">Send €200 to Mama →</button>
    </div>
    <div style="height:20px"></div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi on"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ CONFIRM ══ -->
<div class="phone" id="s-confirm">
  <div class="notch"></div>
  <div class="scr">
    <div class="conf-ic">✅</div>
    <div class="conf-t">Money Sent!</div>
    <div class="conf-s">€200 is on its way to Mama.<br>GMD 15,920 via Wave Wallet.<br>She'll receive it instantly.</div>
    <div class="conf-box">
      <div class="conf-row"><span class="conf-lbl">Amount sent</span><span class="conf-val">€200</span></div>
      <div class="conf-row"><span class="conf-lbl">Mama receives</span><span class="conf-val gold">GMD 15,920</span></div>
      <div class="conf-row"><span class="conf-lbl">Fee</span><span class="conf-val">€0.99</span></div>
    </div>
    <button class="pbtn" onclick="go('home')" style="background:rgba(255,255,255,0.14);border:1px solid rgba(255,255,255,0.22)">Back to Home</button>
    <div style="color:rgba(255,255,255,0.42);font-size:12px;margin-top:14px;cursor:pointer" onclick="go('msgs')">Add a message to Mama →</div>
  </div>
</div>

<!-- ══ BILLS ══ -->
<div class="phone" id="s-bills">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph"><div class="bkr"><button class="bk" onclick="go('home')">←</button><div><div class="ptl">Pay Bills</div><div class="psl">Utilities & top-ups for family</div></div></div></div>
    <div style="padding:16px">

      <!-- NAWEC CashPower -->
      <div class="bill-card">
        <div class="bill-head">
          <div class="bill-icon" style="background:linear-gradient(135deg,#F39C12,#F8C471)">⚡</div>
          <div><div class="bill-title">NAWEC CashPower</div><div class="bill-sub">Electricity top-up · Instant</div></div>
        </div>
        <div class="bill-field"><label class="bill-lbl">Meter Number</label><input class="bill-inp" id="nawec-meter" type="text" placeholder="e.g. 05-12345-6"/></div>
        <div class="bill-field"><label class="bill-lbl">Amount (GMD)</label><input class="bill-inp" id="nawec-amt" type="number" placeholder="e.g. 500"/></div>
        <button class="bill-pay" onclick="payNawec()">⚡ Pay CashPower</button>
      </div>

      <!-- School Fees -->
      <div class="bill-card">
        <div class="bill-head">
          <div class="bill-icon" style="background:linear-gradient(135deg,#1A5276,#2E86C1)">🎓</div>
          <div><div class="bill-title">School Fees</div><div class="bill-sub">Pay directly to school · Same day</div></div>
        </div>
        <div class="bill-field">
          <label class="bill-lbl">Family Member</label>
          <select class="bill-sel" id="school-member">
            <option value="Mama Fatoumata">Mama Fatoumata</option>
            <option value="Lamin (brother)">Lamin (brother)</option>
            <option value="Aminata (sister)">Aminata (sister)</option>
            <option value="Abdou (nephew)">Abdou (nephew)</option>
          </select>
        </div>
        <div class="bill-field"><label class="bill-lbl">Amount (GMD)</label><input class="bill-inp" id="school-amt" type="number" placeholder="e.g. 3500"/></div>
        <button class="bill-pay" onclick="paySchool()">🎓 Pay School Fees</button>
      </div>

      <!-- Water Bill -->
      <div class="bill-card">
        <div class="bill-head">
          <div class="bill-icon" style="background:linear-gradient(135deg,#148F77,#1ABC9C)">💧</div>
          <div><div class="bill-title">Water Bill</div><div class="bill-sub">NAWEC Water · 1–2 hours</div></div>
        </div>
        <div class="bill-field"><label class="bill-lbl">Account Number</label><input class="bill-inp" id="water-acct" type="text" placeholder="e.g. W-88321"/></div>
        <div class="bill-field"><label class="bill-lbl">Amount (GMD)</label><input class="bill-inp" id="water-amt" type="number" placeholder="e.g. 300"/></div>
        <button class="bill-pay" onclick="payWater()">💧 Pay Water Bill</button>
      </div>

      <!-- Mobile Top-up -->
      <div class="bill-card">
        <div class="bill-head">
          <div class="bill-icon" style="background:linear-gradient(135deg,#7D3C98,#A569BD)">📱</div>
          <div><div class="bill-title">Mobile Top-up</div><div class="bill-sub">Airtime · Instant</div></div>
        </div>
        <div class="bill-field">
          <label class="bill-lbl">Network</label>
          <div class="net-row" id="mobile-networks" style="flex-wrap:wrap">
            <button class="net-btn on" id="net-0" onclick="selectNet(this)">Africell</button>
            <button class="net-btn" id="net-1" onclick="selectNet(this)">QCell</button>
            <button class="net-btn" id="net-2" onclick="selectNet(this)">Gamcel</button>
            <button class="net-btn" id="net-3" onclick="selectNet(this)">Comium</button>
          </div>
        </div>
        <div class="bill-field"><label class="bill-lbl">Phone Number</label><input class="bill-inp" id="mobile-phone" type="tel" placeholder="e.g. +220 7XX XXXX"/></div>
        <div class="bill-field"><label class="bill-lbl" id="mobile-amt-lbl">Amount (GMD)</label><input class="bill-inp" id="mobile-amt" type="number" placeholder="e.g. 100"/></div>
        <button class="bill-pay" onclick="payMobile()">📱 Top Up</button>
      </div>

      <!-- Rent Payment -->
      <div class="bill-card">
        <div class="bill-head">
          <div class="bill-icon" style="background:linear-gradient(135deg,#1A5276,#5DADE2)">🏠</div>
          <div><div class="bill-title">Rent Payment</div><div class="bill-sub">Pay your family's landlord directly</div></div>
        </div>
        <div class="bill-field"><label class="bill-lbl">Landlord Name</label><input class="bill-inp" id="rent-landlord" type="text" placeholder="e.g. Ousman Camara"/></div>
        <div class="bill-field"><label class="bill-lbl">Property Address</label><input class="bill-inp" id="rent-address" type="text" placeholder="e.g. Kairaba Avenue, Banjul"/></div>
        <div class="bill-field"><label class="bill-lbl" id="rent-amt-lbl">Amount (GMD)</label><input class="bill-inp" id="rent-amt" type="number" placeholder="e.g. 4000"/></div>
        <div class="bill-field">
          <label class="bill-lbl">Payment Method</label>
          <select class="bill-sel" id="rent-method">
            <option value="Wave">Wave</option>
            <option value="Bank Transfer">Bank Transfer</option>
            <option value="Orange Money">Orange Money</option>
          </select>
        </div>
        <div style="background:rgba(27,67,50,0.05);border:1px solid rgba(27,67,50,0.1);border-radius:10px;padding:10px 12px;display:flex;align-items:flex-start;gap:8px;margin-bottom:10px">
          <span style="font-size:13px;flex-shrink:0">📣</span>
          <div style="font-size:11px;color:var(--tm);line-height:1.5">We notify your landlord automatically when payment is sent.</div>
        </div>
        <button class="bill-pay" onclick="payRent()">🏠 Pay Rent</button>
      </div>

      <div style="height:20px"></div>
    </div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ BILL CONFIRM ══ -->
<div class="phone" id="s-billconf">
  <div class="notch"></div>
  <div class="scr">
    <div class="conf-ic" id="bc-icon">✅</div>
    <div class="conf-t" id="bc-title">Payment Sent!</div>
    <div class="conf-s" id="bc-sub">Your bill payment is being processed.</div>
    <div class="conf-box">
      <div class="conf-row"><span class="conf-lbl">Amount</span><span class="conf-val gold" id="bc-amount">GMD 500</span></div>
      <div class="conf-row"><span class="conf-lbl">Details</span><span class="conf-val" id="bc-detail">—</span></div>
      <div class="conf-row"><span class="conf-lbl">Status</span><span class="conf-val" id="bc-status">Processing ⏳</span></div>
    </div>
    <button class="pbtn" onclick="go('bills')" style="background:rgba(255,255,255,0.14);border:1px solid rgba(255,255,255,0.22);margin-bottom:10px">Pay Another Bill</button>
    <button class="pbtn" onclick="go('home')" style="background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.12)">Back to Home</button>
  </div>
</div>

<!-- ══ MESSAGES ══ -->
<div class="phone" id="s-msgs">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phg" style="padding-bottom:24px"><div class="ptl">Messages</div><div class="psl">Family threads</div></div>
    <div class="cvi" onclick="go('chat')">
      <div class="cva ca1">👵🏾</div>
      <div class="cvinf"><div class="cvnm">Mama Fatoumata</div><div class="cvpv">🎙️ Voice note received · Thank you Buba...</div></div>
      <div class="cvmt"><div class="cvtm">Now</div><div class="ubd">2</div></div>
    </div>
    <div class="cvi">
      <div class="cva ca2">L</div>
      <div class="cvinf"><div class="cvnm">Lamin (brother)</div><div class="cvpv">School fees paid ✅ Thanks big bro</div></div>
      <div class="cvmt"><div class="cvtm">Yesterday</div></div>
    </div>
    <div class="cvi">
      <div class="cva ca3">A</div>
      <div class="cvinf"><div class="cvnm">Aminata (sister)</div><div class="cvpv">Did you send this month? I haven't received...</div></div>
      <div class="cvmt"><div class="cvtm">Apr 10</div><div class="ubd">1</div></div>
    </div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi on"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ CHAT ══ -->
<div class="phone" id="s-chat">
  <div class="notch"></div>
  <div class="scr" style="display:flex;flex-direction:column;padding-top:32px">
    <div class="chat-hd">
      <button class="bk" onclick="go('msgs')">←</button>
      <div class="cha ca1">👵🏾</div>
      <div><div class="chnm">Mama Fatoumata</div><div class="chst">🟢 Online · Banjul, Gambia</div></div>
    </div>
    <div class="chat-area" id="chat-area">
      <div class="tr-bbl"><span style="font-size:20px">💸</span><div><div class="tb-a">€120 sent</div><div class="tb-s">GMD 9,552 · Wave Wallet</div></div><span style="margin-left:auto;color:var(--gl);font-size:16px">✓</span></div>
      <div class="bbl me"><div class="bbl-in">🎙️ <em>Voice note: 0:14</em></div><div class="bbl-tm">10:22</div></div>
      <div class="bbl th"><div class="bbl-in">Alhamdulillah! I received it. Thank you so much Buba. May Allah bless you. 🙏</div><div class="bbl-tm">10:31</div></div>
      <div class="bbl th"><div class="bbl-in">I need to pay Abdou's school fees by Friday. It's GMD 3,500. Can you help?</div><div class="bbl-tm">10:33</div></div>
      <div class="bbl me"><div class="bbl-in">Of course Mama. I'll send Thursday when the rate is better. 💚</div><div class="bbl-tm">10:45</div></div>
    </div>
    <div style="padding:8px 14px;background:var(--ww);border-top:1px solid rgba(27,67,50,0.07)">
      <button class="pbtn" style="font-size:13px;padding:13px;margin-bottom:8px" onclick="go('send')">💸 Send Money to Mama</button>
    </div>
    <div class="cin-row">
      <input class="cin" id="cin" placeholder="Type a message..."/>
      <button class="csnd" onclick="sendChat()">➤</button>
    </div>
  </div>
</div>

<!-- ══ AI ══ -->
<div class="phone" id="s-ai">
  <div class="notch"></div>
  <div class="scr" style="display:flex;flex-direction:column">
    <div class="ph phg" style="padding-bottom:20px">
      <div style="display:flex;align-items:center;gap:12px;margin-bottom:12px">
        <div style="width:48px;height:48px;border-radius:50%;background:linear-gradient(135deg,var(--au),var(--al));display:flex;align-items:center;justify-content:center;font-size:22px;flex-shrink:0">✨</div>
        <div>
          <div class="ptl">Dalasi AI</div>
          <div class="psl">Your West African assistant · Always here</div>
          <div style="display:inline-flex;align-items:center;gap:5px;background:rgba(46,204,113,0.18);border:1px solid rgba(46,204,113,0.35);border-radius:18px;padding:3px 10px;margin-top:6px">
            <span style="width:7px;height:7px;border-radius:50%;background:#2ECC71;flex-shrink:0;display:inline-block"></span>
            <span style="color:#D8F3DC;font-size:10px;font-weight:700;letter-spacing:0.04em">Offline AI — instant responses</span>
          </div>
        </div>
      </div>
      <div class="lang-t">
        <div class="lt on" onclick="setLang(this)">English</div>
        <div class="lt" onclick="setLang(this)">Mandinka</div>
        <div class="lt" onclick="setLang(this)">Wolof</div>
        <div class="lt" onclick="setLang(this)">Français</div>
      </div>
    </div>
    <div class="ai-msgs" id="ai-msgs">
      <div class="msg ai"><div class="msg-bbl">Salamu alaikum Buba! 👋 I'm your Dalasi AI. Ask me anything — transfers, exchange rates, Austrian visa help, Gambian news, or anything about home. I speak English, Mandinka and Wolof.</div><div class="msg-tm">Now</div></div>
    </div>
    <div class="chips">
      <div class="chip" onclick="askQ('What is the best rate this week to send money to Gambia?')">📊 Best rate this week?</div>
      <div class="chip" onclick="askQ('How do I top up electricity CashPower for my family in Gambia from Europe?')">⚡ Top up electricity</div>
      <div class="chip" onclick="askQ('My Austrian Aufenthaltstitel expires in 2 months. What documents do I need to renew it?')">📋 Visa renewal help</div>
      <div class="chip" onclick="askQ('Are there Gambian community events or groups in Vienna, Austria?')">🌍 Vienna community</div>
    </div>
    <div class="ai-in-row">
      <input class="ai-in" id="ai-in" placeholder="Ask anything..." onkeydown="if(event.key==='Enter')sendAI()"/>
      <button class="ai-snd" onclick="sendAI()">➤</button>
    </div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi on"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ FAMILY ══ -->
<div class="phone" id="s-family">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phb" style="padding-bottom:42px"><div class="bkr"><button class="bk" onclick="go('home')">←</button></div><div class="ptl">Family Wallet</div><div class="psl">Buba's family · Gambia 🇬🇲</div></div>
    <div style="background:var(--cr);border-radius:20px 20px 0 0;margin-top:-20px;padding:20px 16px;position:relative;z-index:2">
      <div class="tot-s"><div class="tot-l">Sent this month</div><div class="tot-a">€340</div><div class="tot-s2">GMD 27,064 across 3 members</div></div>
      <div class="mc"><div class="mt"><div class="mav m1">👵🏾</div><div><div class="mnm">Mama Fatoumata</div><div class="mrl">Mother · Banjul</div></div><div class="msnt"><div class="ms">€120</div><div class="md">Today</div></div></div><div class="pb"><div class="pf" style="width:80%"></div></div><div class="pl"><div class="pt">€120 of €150 monthly</div><div class="pt" style="color:var(--g)">80%</div></div></div>
      <div class="mc"><div class="mt"><div class="mav m2">L</div><div><div class="mnm">Lamin Jallow</div><div class="mrl">Brother · Serrekunda</div></div><div class="msnt"><div class="ms">€85</div><div class="md">Yesterday</div></div></div><div class="pb"><div class="pf" style="width:85%"></div></div><div class="pl"><div class="pt">€85 of €100 monthly</div><div class="pt" style="color:var(--g)">85%</div></div></div>
      <div class="mc"><div class="mt"><div class="mav m3">A</div><div><div class="mnm">Aminata Jallow</div><div class="mrl">Sister · Brikama</div></div><div class="msnt"><div class="ms" style="color:var(--au)">€135</div><div class="md" style="color:var(--au)">Pending</div></div></div><div class="pb"><div class="pf" style="width:0%"></div></div><div class="pl"><div class="pt">€0 of €135 monthly</div><div class="pt" style="color:var(--au)">Pending</div></div></div>
      <div class="req-c"><span style="font-size:20px">📩</span><div style="flex:1"><div style="font-size:12px;font-weight:700;color:var(--td);margin-bottom:2px">New request from Mama</div><div style="font-size:11px;color:var(--tl)">"School fees for Abdou — GMD 3,500"</div></div><button class="rs-btn" onclick="go('send')">Send</button></div>
      <button class="add-m">+ Add family member</button>
    </div>
    <div style="height:32px"></div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ YEARLY ══ -->
<div class="phone" id="s-yearly">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phn" style="padding-bottom:42px"><div class="bkr"><button class="bk" onclick="go('home')">←</button><div><div class="ptl">Your 2025 Story</div><div class="psl">A year of taking care of family</div></div></div></div>
    <div style="background:var(--cr);border-radius:20px 20px 0 0;margin-top:-20px;padding:20px 16px;position:relative;z-index:2">
      <div class="bs"><div class="bsl">Total sent in 2025</div><div class="bsn">€3,840</div><div class="bss">GMD 305,664 received by your family</div><div class="bsb">🏆 Top 12% of Dalasi senders</div></div>
      <div class="sg">
        <div class="sc"><div class="sci">📤</div><div class="scn">47</div><div class="scl">Transfers made</div></div>
        <div class="sc"><div class="sci">👨‍👩‍👧</div><div class="scn">3</div><div class="scl">Family supported</div></div>
        <div class="sc"><div class="sci">⚡</div><div class="scn">18</div><div class="scl">Bills paid remotely</div></div>
        <div class="sc"><div class="sci">💰</div><div class="scn">€34</div><div class="scl">Fees saved vs APS</div></div>
      </div>
      <div class="mc-w">
        <div class="ct">Monthly transfers (€)</div>
        <div class="cbrs">
          <div class="bc"><div class="br" style="height:42px"></div><div class="bm">Jan</div></div>
          <div class="bc"><div class="br" style="height:35px"></div><div class="bm">Feb</div></div>
          <div class="bc"><div class="br" style="height:52px"></div><div class="bm">Mar</div></div>
          <div class="bc"><div class="br hi" style="height:66px"></div><div class="bm">Apr</div></div>
          <div class="bc"><div class="br" style="height:40px"></div><div class="bm">May</div></div>
          <div class="bc"><div class="br" style="height:46px"></div><div class="bm">Jun</div></div>
          <div class="bc"><div class="br" style="height:58px"></div><div class="bm">Jul</div></div>
          <div class="bc"><div class="br" style="height:33px"></div><div class="bm">Aug</div></div>
          <div class="bc"><div class="br" style="height:48px"></div><div class="bm">Sep</div></div>
          <div class="bc"><div class="br" style="height:62px"></div><div class="bm">Oct</div></div>
          <div class="bc"><div class="br" style="height:38px"></div><div class="bm">Nov</div></div>
          <div class="bc"><div class="br" style="height:28px"></div><div class="bm">Dec</div></div>
        </div>
      </div>
      <button class="shr">📤 Share my 2025 Summary</button>
    </div>
    <div style="height:32px"></div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ COMMUNITY ══ -->
<div class="phone" id="s-comm">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phn" style="padding-bottom:24px">
      <div class="ptl">Community</div>
      <div class="psl">Gambians near you & back home</div>
      <div class="loc-t">📍 Vienna, Austria</div>
      <div class="cm-tabs">
        <div class="cmt on" onclick="switchCommTab(0,this)">Nearby</div>
        <div class="cmt" onclick="switchCommTab(1,this)">News</div>
        <div class="cmt" onclick="switchCommTab(2,this)">Jobs</div>
        <div class="cmt" onclick="switchCommTab(3,this)">Businesses</div>
      </div>
    </div>
    <div class="cm-body">

      <!-- ── NEARBY ── -->
      <div id="comm-tab-nearby">
        <div class="sh" style="margin-bottom:10px"><div class="st">Gambians in Vienna</div><div class="sa">View map</div></div>
        <div class="p-row">
          <div class="pc"><div class="pav p1">K</div><div class="pnm">Kaddy</div><div class="pct">1st District</div><div class="pol"></div></div>
          <div class="pc"><div class="pav p2">M</div><div class="pnm">Modou</div><div class="pct">10th District</div><div class="pol"></div></div>
          <div class="pc"><div class="pav p3">F</div><div class="pnm">Fatou</div><div class="pct">16th District</div><div class="pol" style="background:#ccc"></div></div>
          <div class="pc"><div class="pav p4">S</div><div class="pnm">Samba</div><div class="pct">21st District</div><div class="pol"></div></div>
        </div>
        <div class="sh" style="margin-bottom:10px;margin-top:4px"><div class="st">Senegalese in Vienna</div><div class="sa">View map</div></div>
        <div class="p-row">
          <div class="pc"><div class="pav" style="background:linear-gradient(135deg,#27AE60,#2ECC71);color:#fff">O</div><div class="pnm">Oumar</div><div class="pct">2nd District</div><div class="pol"></div></div>
          <div class="pc"><div class="pav" style="background:linear-gradient(135deg,#E74C3C,#F1948A);color:#fff">A</div><div class="pnm">Aissatou</div><div class="pct">7th District</div><div class="pol"></div></div>
          <div class="pc"><div class="pav" style="background:linear-gradient(135deg,#F39C12,#F8C471);color:#fff">D</div><div class="pnm">Diallo</div><div class="pct">15th District</div><div class="pol" style="background:#ccc"></div></div>
          <div class="pc"><div class="pav" style="background:linear-gradient(135deg,#8E44AD,#BB8FCE);color:#fff">N</div><div class="pnm">Ndèye</div><div class="pct">20th District</div><div class="pol"></div></div>
        </div>
      </div>

      <!-- ── NEWS ── -->
      <div id="comm-tab-news" style="display:none">
        <div class="sh" style="margin-bottom:10px"><div class="st">Latest</div><div class="sa">See all</div></div>
        <div class="nwi"><div class="ntag te">Event</div><div class="n-tt">Gambia Community Day — Vienna 2025 🎉</div><div class="n-mt"><span>May 18 · Prater Park</span><div class="ndot"></div><span>142 attending</span></div></div>
        <div class="nwi"><div class="ntag tn">News</div><div class="n-tt">Central Bank of Gambia holds exchange rate steady this quarter</div><div class="n-mt"><span>2 hours ago</span><div class="ndot"></div><span>The Standard</span></div></div>
        <div class="nwi"><div class="ntag te">Event</div><div class="n-tt">Dakar – Senegalese Diaspora Day Vienna 🇸🇳</div><div class="n-mt"><span>Jun 7 · Augarten</span><div class="ndot"></div><span>📍 Dakar community</span></div></div>
        <div class="nwi"><div class="ntag tj">Jobs</div><div class="n-tt">Cleaning & logistics roles in Vienna — no German required</div><div class="n-mt"><span>Posted today</span><div class="ndot"></div><span>4 positions</span></div></div>
      </div>

      <!-- ── JOBS ── -->
      <div id="comm-tab-jobs" style="display:none">
        <input class="job-search" id="job-search" type="text" placeholder="🔍  Search jobs, companies, skills..." oninput="filterJobs()"/>
        <div class="jfilt-row">
          <button class="jfilt-btn on" onclick="setJobFilter('all',this)">All</button>
          <button class="jfilt-btn" onclick="setJobFilter('gambia',this)">🇬🇲 Gambia</button>
          <button class="jfilt-btn" onclick="setJobFilter('senegal',this)">🇸🇳 Senegal</button>
          <button class="jfilt-btn" onclick="setJobFilter('remote',this)">🌐 Remote</button>
        </div>
        <div id="jobs-list">

          <!-- Gambia 1 -->
          <div class="job-card" data-country="gambia">
            <div class="jctag jtag-gm">🇬🇲 Gambia</div>
            <div class="job-ttl">Accountant</div>
            <div class="job-co">GAMTEL · Telecommunications</div>
            <div class="job-meta">
              <span class="job-loc">📍 Banjul</span>
              <span class="job-sal">GMD 18,000 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted 2 days ago</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Gambia 2 -->
          <div class="job-card" data-country="gambia">
            <div class="jctag jtag-gm">🇬🇲 Gambia</div>
            <div class="job-ttl">Registered Nurse</div>
            <div class="job-co">Edward Francis Small Teaching Hospital</div>
            <div class="job-meta">
              <span class="job-loc">📍 Banjul</span>
              <span class="job-sal">GMD 12,500 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted today</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Gambia 3 -->
          <div class="job-card" data-country="gambia">
            <div class="jctag jtag-gm">🇬🇲 Gambia</div>
            <div class="job-ttl">Software Developer</div>
            <div class="job-co">Africell Gambia · Mobile Tech</div>
            <div class="job-meta">
              <span class="job-loc">📍 Kairaba Avenue</span>
              <span class="job-sal">GMD 35,000 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted 1 week ago</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Gambia 4 -->
          <div class="job-card" data-country="gambia">
            <div class="jctag jtag-gm">🇬🇲 Gambia</div>
            <div class="job-ttl">Secondary School Teacher</div>
            <div class="job-co">Gambia College · Education</div>
            <div class="job-meta">
              <span class="job-loc">📍 Brikama</span>
              <span class="job-sal">GMD 9,500 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted 3 days ago</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Gambia 5 -->
          <div class="job-card" data-country="gambia">
            <div class="jctag jtag-gm">🇬🇲 Gambia</div>
            <div class="job-ttl">Sales Executive</div>
            <div class="job-co">QCell Gambia · Telecoms</div>
            <div class="job-meta">
              <span class="job-loc">📍 Serrekunda</span>
              <span class="job-sal">GMD 15,000 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted today</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Gambia 6 -->
          <div class="job-card" data-country="gambia">
            <div class="jctag jtag-gm">🇬🇲 Gambia</div>
            <div class="job-ttl">Construction Supervisor</div>
            <div class="job-co">NAWEC Projects · Infrastructure</div>
            <div class="job-meta">
              <span class="job-loc">📍 Banjul</span>
              <span class="job-sal">GMD 22,000 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted 5 days ago</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Senegal 1 -->
          <div class="job-card" data-country="senegal">
            <div class="jctag jtag-sn">🇸🇳 Senegal</div>
            <div class="job-ttl">Marketing Manager</div>
            <div class="job-co">Orange Sénégal · Telecoms</div>
            <div class="job-meta">
              <span class="job-loc">📍 Dakar</span>
              <span class="job-sal">XOF 450,000 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted today</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Senegal 2 -->
          <div class="job-card" data-country="senegal">
            <div class="jctag jtag-sn">🇸🇳 Senegal</div>
            <div class="job-ttl">Civil Engineer</div>
            <div class="job-co">Groupe Eiffage Sénégal · Construction</div>
            <div class="job-meta">
              <span class="job-loc">📍 Dakar</span>
              <span class="job-sal">XOF 580,000 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted 2 days ago</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

          <!-- Senegal 3 -->
          <div class="job-card" data-country="senegal">
            <div class="jctag jtag-sn">🇸🇳 Senegal</div>
            <div class="job-ttl">Finance Analyst</div>
            <div class="job-co">CBAO Banque · Financial Services</div>
            <div class="job-meta">
              <span class="job-loc">📍 Dakar Plateau</span>
              <span class="job-sal">XOF 380,000 / mo</span>
            </div>
            <div class="job-foot"><span class="job-date">Posted 1 week ago</span><button class="apply-btn" onclick="applyJob(this)">Apply →</button></div>
          </div>

        </div>
      </div>

      <!-- ── BUSINESSES ── -->
      <div id="comm-tab-biz" style="display:none">
        <input class="job-search" id="biz-search" type="text" placeholder="🔍  Search businesses..." oninput="filterBiz()"/>
        <div class="jfilt-row">
          <button class="jfilt-btn on" onclick="setBizFilter('all',this)">All</button>
          <button class="jfilt-btn" onclick="setBizFilter('restaurant',this)">🍽 Restaurants</button>
          <button class="jfilt-btn" onclick="setBizFilter('shop',this)">🛍 Shops</button>
          <button class="jfilt-btn" onclick="setBizFilter('services',this)">✂️ Services</button>
          <button class="jfilt-btn" onclick="setBizFilter('realestate',this)">🏠 Real Estate</button>
          <button class="jfilt-btn" onclick="setBizFilter('transport',this)">🚐 Transport</button>
        </div>
        <div id="biz-list">

          <!-- 1 — Restaurant · Gambia · Diaspora Owned -->
          <div class="biz-card" data-category="restaurant">
            <div class="diaspora-badge">🌍 Diaspora Owned</div>
            <div class="biz-name">Mama Africa Kitchen</div>
            <div class="biz-cat">Restaurant</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Serrekunda, Gambia</span>
              <span class="biz-phone">+220 976 3421</span>
            </div>
            <div class="biz-desc">Authentic benachin, domoda & pastels. Family-run since 2018. Catering & takeaway available.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

          <!-- 2 — Restaurant · Gambia -->
          <div class="biz-card" data-category="restaurant">
            <div class="biz-name">Jollof House</div>
            <div class="biz-cat">Restaurant</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Banjul, Gambia</span>
              <span class="biz-phone">+220 772 1190</span>
            </div>
            <div class="biz-desc">Best jollof rice and thieboudienne in the city. Open daily 10am–10pm. Group bookings welcome.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

          <!-- 3 — Shop · Senegal · Diaspora Owned -->
          <div class="biz-card" data-category="shop">
            <div class="diaspora-badge">🌍 Diaspora Owned</div>
            <div class="biz-name">Baobab Fashion</div>
            <div class="biz-cat">Shop</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Dakar Plateau, Senegal</span>
              <span class="biz-phone">+221 77 432 0011</span>
            </div>
            <div class="biz-desc">African prints, boubous and tailored outfits. Custom orders & international shipping available.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

          <!-- 4 — Shop · Gambia -->
          <div class="biz-card" data-category="shop">
            <div class="biz-name">Serrekunda Electronics</div>
            <div class="biz-cat">Shop</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Serrekunda, Gambia</span>
              <span class="biz-phone">+220 993 5582</span>
            </div>
            <div class="biz-desc">Phones, accessories and repairs. All major brands stocked. Unlocking & screen replacement on-site.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

          <!-- 5 — Services · Gambia · Diaspora Owned -->
          <div class="biz-card" data-category="services">
            <div class="diaspora-badge">🌍 Diaspora Owned</div>
            <div class="biz-name">Fatou's Hair & Beauty</div>
            <div class="biz-cat">Services</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Kanifing, Gambia</span>
              <span class="biz-phone">+220 781 4430</span>
            </div>
            <div class="biz-desc">Braiding, locs and natural hair care. Walk-ins welcome. Book ahead for weekends.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

          <!-- 6 — Real Estate · Gambia -->
          <div class="biz-card" data-category="realestate">
            <div class="biz-name">Kairaba Property Group</div>
            <div class="biz-cat">Real Estate</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Banjul, Gambia</span>
              <span class="biz-phone">+220 968 7700</span>
            </div>
            <div class="biz-desc">Residential & commercial sales, rentals and property management. Trusted by diaspora investors since 2015.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

          <!-- 7 — Transport · Senegal -->
          <div class="biz-card" data-category="transport">
            <div class="biz-name">Teranga Logistics</div>
            <div class="biz-cat">Transport</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Dakar, Senegal</span>
              <span class="biz-phone">+221 76 521 8844</span>
            </div>
            <div class="biz-desc">Freight, parcel delivery and airport transfers across Senegal. Same-day delivery in Dakar.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

          <!-- 8 — Transport · Gambia -->
          <div class="biz-card" data-category="transport">
            <div class="biz-name">Gambia Tours & Safaris</div>
            <div class="biz-cat">Transport</div>
            <div class="biz-meta">
              <span class="biz-loc">📍 Banjul, Gambia</span>
              <span class="biz-phone">+220 774 9923</span>
            </div>
            <div class="biz-desc">Guided tours, river trips and car hire. Popular with diaspora visiting home. English & French spoken.</div>
            <div style="display:flex;justify-content:flex-end"><button class="contact-btn" onclick="contactBiz(this)">Message →</button></div>
          </div>

        </div>
      </div>

    </div>
    <div style="height:32px"></div>
  </div>
  <!-- Apply toast -->
  <div id="apply-toast" style="display:none" class="apply-toast">
    <div class="apply-toast-t">✅ Application sent!</div>
    <div class="apply-toast-s">The employer will contact you via Dalasi messages.</div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi on"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ INVEST ══ -->
<div class="phone" id="s-invest">
  <div class="notch"></div>
  <div class="scr">
    <div class="ph phg"><div class="bkr"><button class="bk" onclick="go('home')">←</button><div><div class="ptl">Invest Back Home</div><div class="psl">Verified opportunities in Gambia &amp; Senegal</div></div></div></div>
    <div style="padding:16px 16px 0">
      <div class="inv-trust"><span style="font-size:16px;flex-shrink:0">🛡️</span><div><strong>All listings verified by Dalasi.</strong> Your investment is protected and monitored by our local partners.</div></div>
    </div>
    <div style="padding:0 16px 16px">

      <!-- Land & Property -->
      <div class="inv-cat-hd">🏡 Land &amp; Property</div>

      <div class="inv-card">
        <div class="verified-badge">✅ Verified</div>
        <div class="inv-title">Residential Plot — Bakau, Banjul</div>
        <div class="inv-meta">📍 Bakau, Gambia · 1,200 sqm · Freehold title</div>
        <div class="inv-price">GMD 450,000</div>
        <div style="display:flex;justify-content:flex-end"><button class="inv-btn" onclick="investInterest(this)">I'm Interested →</button></div>
      </div>

      <div class="inv-card">
        <div class="verified-badge">✅ Verified</div>
        <div class="inv-title">2-Bedroom Apartment — Serrekunda</div>
        <div class="inv-meta">📍 Serrekunda, Gambia · 85 sqm · 2nd floor · Ready to let</div>
        <div class="inv-price">GMD 1,200,000</div>
        <div style="display:flex;justify-content:flex-end"><button class="inv-btn" onclick="investInterest(this)">I'm Interested →</button></div>
      </div>

      <div class="inv-card">
        <div class="verified-badge">✅ Verified</div>
        <div class="inv-title">Commercial Unit — Dakar Plateau</div>
        <div class="inv-meta">📍 Dakar Plateau, Senegal · 200 sqm · Ground floor · High footfall</div>
        <div class="inv-price">XOF 15,000,000</div>
        <div style="display:flex;justify-content:flex-end"><button class="inv-btn" onclick="investInterest(this)">I'm Interested →</button></div>
      </div>

      <!-- Small Businesses -->
      <div class="inv-cat-hd">🏪 Small Businesses</div>

      <div class="inv-card">
        <div class="verified-badge">✅ Verified</div>
        <div class="inv-title">Benachin Kitchen — Diaspora Restaurant</div>
        <div class="inv-meta">📍 Serrekunda, Gambia · Seeking diaspora co-investors</div>
        <div class="inv-stats">
          <div class="inv-stat"><div class="inv-stat-l">Needed</div><div class="inv-stat-v">GMD 180,000</div></div>
          <div class="inv-stat"><div class="inv-stat-l">Expected Return</div><div class="inv-stat-v ret">18% / year</div></div>
        </div>
        <div style="display:flex;justify-content:flex-end"><button class="inv-btn" onclick="investInterest(this)">Invest →</button></div>
      </div>

      <div class="inv-card">
        <div class="verified-badge">✅ Verified</div>
        <div class="inv-title">Senegambia Transport Co.</div>
        <div class="inv-meta">📍 Banjul, Gambia · Fleet expansion · 3 new vehicles</div>
        <div class="inv-stats">
          <div class="inv-stat"><div class="inv-stat-l">Needed</div><div class="inv-stat-v">GMD 250,000</div></div>
          <div class="inv-stat"><div class="inv-stat-l">Expected Return</div><div class="inv-stat-v ret">22% / year</div></div>
        </div>
        <div style="display:flex;justify-content:flex-end"><button class="inv-btn" onclick="investInterest(this)">Invest →</button></div>
      </div>

      <!-- Agriculture -->
      <div class="inv-cat-hd">🌾 Agriculture</div>

      <div class="inv-card">
        <div class="verified-badge">✅ Verified</div>
        <div class="inv-title">Jarra Rice Farming Cooperative</div>
        <div class="inv-meta">📍 Jarra District, Gambia · Seasonal rice production · 50 acres</div>
        <div class="inv-stats">
          <div class="inv-stat"><div class="inv-stat-l">Seeking</div><div class="inv-stat-v">GMD 120,000</div></div>
          <div class="inv-stat"><div class="inv-stat-l">Expected Return</div><div class="inv-stat-v ret">15% / season</div></div>
        </div>
        <div class="inv-desc">30-member cooperative. Revenue shared among diaspora investors after each harvest. Dalasi monitors progress quarterly.</div>
        <div style="display:flex;justify-content:flex-end"><button class="inv-btn" onclick="investInterest(this)">Invest →</button></div>
      </div>

      <div style="height:20px"></div>
    </div>
  </div>
  <div id="invest-toast" style="display:none" class="invest-toast">
    <div style="font-weight:700;font-size:13px;margin-bottom:2px">✅ Interest registered!</div>
    <div style="font-size:11px;opacity:0.75">Our team will contact you via Dalasi messages within 48 hours.</div>
  </div>
  <div class="bnav">
    <div class="nvi" onclick="go('home')"><div class="nvi-i">🏠</div><div class="nvi-l">Home</div></div>
    <div class="nvi" onclick="go('send')"><div class="nvi-i">💸</div><div class="nvi-l">Send</div></div>
    <div class="nvi" onclick="go('ai')"><div class="nvi-i">✨</div><div class="nvi-l">AI</div></div>
    <div class="nvi" onclick="go('msgs')"><div class="nvi-i">💬</div><div class="nvi-l">Messages</div></div>
    <div class="nvi" onclick="go('comm')"><div class="nvi-i">🌍</div><div class="nvi-l">Community</div></div>
  </div>
</div>

<!-- ══ SWITCHER ══ -->
<div class="sw">
  <button class="sb on" onclick="go('onboard')">🌍 Start</button>
  <button class="sb" onclick="go('lock')">🔐</button>
  <button class="sb" onclick="go('home')">🏠 Home</button>
  <button class="sb" onclick="go('notifs')">🔔 Alerts</button>
  <button class="sb" onclick="go('send')">💸 Send</button>
  <button class="sb" onclick="go('bills')">⚡ Bills</button>
  <button class="sb" onclick="go('msgs')">💬 Msgs</button>
  <button class="sb" onclick="go('ai')">✨ AI</button>
  <button class="sb" onclick="go('family')">👨‍👩‍👧 Family</button>
  <button class="sb" onclick="go('yearly')">📊 Year</button>
  <button class="sb" onclick="go('comm')">🌍 Community</button>
  <button class="sb" onclick="go('invest')">📈 Invest</button>
</div>

<script>
const screens={onboard:0,lock:1,home:2,notifs:3,send:4,bills:5,msgs:6,ai:7,family:8,yearly:9,comm:10,invest:11};
function go(id){
  document.querySelectorAll('.phone').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.sb').forEach(b=>b.classList.remove('on'));
  const el=document.getElementById('s-'+id);
  if(el){el.classList.add('active');window.scrollTo({top:0,behavior:'smooth'})}
  const sbs=[...document.querySelectorAll('.sb')];
  if(screens[id]!==undefined)sbs[screens[id]].classList.add('on');
  if(id==='send')refreshSendScreen();
  if(id==='bills')setupBillsScreen();
}

// Live rate fetch
async function fetchRates(){
  try{
    const r=await fetch('https://open.er-api.com/v6/latest/EUR');
    const d=await r.json();
    if(d.result==='success'&&d.rates){
      const gmd=+(d.rates.GMD||0).toFixed(2);
      const xof=Math.round(d.rates.XOF||0);
      if(gmd>0)countryData.gambia.rate=gmd;
      if(xof>0)countryData.senegal.rate=xof;
      const badge=document.getElementById('rate-badge');
      if(badge)badge.style.display='inline';
      refreshSendScreen();
    }
  }catch(e){}
}
document.addEventListener('DOMContentLoaded',fetchRates);

// Country / currency logic
let currentCountry='gambia';
const countryData={
  gambia:{rate:79.6,currency:'GMD',subtitle:'Worldwide → The Gambia',alertHtml:'<span style="font-size:16px">⚡</span><div class="ral-t"><strong>Great rate right now.</strong> Sending today saves ~GMD 400 vs. yesterday.</div>',deliveryHtml:`<div class="dop sel"><div class="di">📱</div><div><div class="dn">Wave Wallet</div><div class="ds">Instant · Free</div></div><div class="dc">✓</div></div><div class="dop"><div class="di">🏦</div><div><div class="dn">Bank Deposit</div><div class="ds">1–2 hours</div></div></div><div class="dop"><div class="di">💵</div><div><div class="dn">Cash Pickup</div><div class="ds">APS branches · Same day</div></div></div>`},
  senegal:{rate:655,currency:'XOF',subtitle:'Worldwide → Senegal',alertHtml:'<span style="font-size:16px">⚡</span><div class="ral-t"><strong>Stable CFA rate.</strong> 1 EUR = 655 XOF — pegged, no surprises.</div>',deliveryHtml:`<div class="dop sel"><div class="di">📱</div><div><div class="dn">Wave Wallet</div><div class="ds">Instant · Free · Dominant in Senegal</div></div><div class="dc">✓</div></div><div class="dop"><div class="di">🟠</div><div><div class="dn">Orange Money</div><div class="ds">Instant · Widely used</div></div></div><div class="dop"><div class="di">🏦</div><div><div class="dn">Bank Deposit</div><div class="ds">1–2 hours</div></div></div>`}
};

function selectCountry(c){
  currentCountry=c;
  go('lock');
}

function setCountry(c){
  currentCountry=c;
  refreshSendScreen();
}

function refreshSendScreen(){
  const d=countryData[currentCountry];
  const v=parseFloat(document.getElementById('ami')?.value)||0;
  const gmdEl=document.getElementById('gmd');
  const rlEl=document.getElementById('rate-label');
  const subEl=document.getElementById('send-subtitle');
  const alertEl=document.getElementById('rate-alert');
  const delivEl=document.getElementById('delivery-methods');
  const sbtnEl=document.getElementById('sbtn');
  if(gmdEl)gmdEl.textContent=d.currency+' '+(v*d.rate).toLocaleString('en',{maximumFractionDigits:0});
  if(rlEl)rlEl.textContent='Rate: '+d.rate;
  if(subEl)subEl.textContent=d.subtitle;
  if(alertEl)alertEl.innerHTML=d.alertHtml;
  if(delivEl)delivEl.innerHTML=d.deliveryHtml;
  if(sbtnEl)sbtnEl.textContent='Send €'+v+' to Mama →';
  document.getElementById('btn-gambia')?.classList.toggle('on',currentCountry==='gambia');
  document.getElementById('btn-senegal')?.classList.toggle('on',currentCountry==='senegal');
}

// Send screen live calculation
const ami=document.getElementById('ami');
const gmd=document.getElementById('gmd');
const sbtn=document.getElementById('sbtn');
if(ami){
  ami.addEventListener('input',()=>{
    const d=countryData[currentCountry];
    const v=parseFloat(ami.value)||0;
    gmd.textContent=d.currency+' '+(v*d.rate).toLocaleString('en',{maximumFractionDigits:0});
    sbtn.textContent='Send €'+v+' to Mama →';
  });
}
if(sbtn)sbtn.addEventListener('click',()=>go('confirm'));

// Businesses
let currentBizFilter='all';
function setBizFilter(f,el){
  currentBizFilter=f;
  document.querySelectorAll('#comm-tab-biz .jfilt-btn').forEach(b=>b.classList.remove('on'));
  el.classList.add('on');
  filterBiz();
}
function filterBiz(){
  const q=(document.getElementById('biz-search')?.value||'').toLowerCase();
  document.querySelectorAll('.biz-card').forEach(card=>{
    const matchFilter=currentBizFilter==='all'||card.dataset.category===currentBizFilter;
    const matchSearch=!q||card.textContent.toLowerCase().includes(q);
    card.style.display=matchFilter&&matchSearch?'block':'none';
  });
}
function contactBiz(btn){
  btn.textContent='Sent ✓';
  btn.disabled=true;
  const toast=document.getElementById('apply-toast');
  if(toast){
    toast.querySelector('.apply-toast-t').textContent='✅ Message sent via Dalasi!';
    toast.querySelector('.apply-toast-s').textContent='The business will reply to your Dalasi messages.';
    toast.style.display='block';
    clearTimeout(applyTimer);
    applyTimer=setTimeout(()=>toast.style.display='none',3200);
  }
}

// Community tabs
function switchCommTab(i,el){
  document.querySelectorAll('.cmt').forEach(t=>t.classList.remove('on'));
  el.classList.add('on');
  const tabs=['comm-tab-nearby','comm-tab-news','comm-tab-jobs','comm-tab-biz'];
  tabs.forEach((t,j)=>{const el=document.getElementById(t);if(el)el.style.display=j===i?'block':'none';});
}

// Jobs
let currentJobFilter='all';
function setJobFilter(f,el){
  currentJobFilter=f;
  document.querySelectorAll('.jfilt-btn').forEach(b=>b.classList.remove('on'));
  el.classList.add('on');
  filterJobs();
}
function filterJobs(){
  const q=(document.getElementById('job-search')?.value||'').toLowerCase();
  document.querySelectorAll('.job-card').forEach(card=>{
    const country=card.dataset.country;
    const matchFilter=currentJobFilter==='all'||country===currentJobFilter;
    const matchSearch=!q||card.textContent.toLowerCase().includes(q);
    card.style.display=matchFilter&&matchSearch?'block':'none';
  });
}
let applyTimer=null;
function applyJob(btn){
  btn.textContent='Applied ✓';
  btn.disabled=true;
  const toast=document.getElementById('apply-toast');
  if(toast){
    toast.style.display='block';
    clearTimeout(applyTimer);
    applyTimer=setTimeout(()=>toast.style.display='none',3200);
  }
}

// Bills
let selectedNet='Africell';
function selectNet(el){
  document.querySelectorAll('.net-btn').forEach(b=>b.classList.remove('on'));
  el.classList.add('on');
  selectedNet=el.textContent;
}

function setupBillsScreen(){
  const nets=document.getElementById('mobile-networks');
  const lbl=document.getElementById('mobile-amt-lbl');
  if(!nets)return;
  const cur=countryData[currentCountry].currency;
  if(currentCountry==='senegal'){
    nets.innerHTML=`<button class="net-btn on" id="net-0" onclick="selectNet(this)">Orange</button><button class="net-btn" id="net-1" onclick="selectNet(this)">Free</button>`;
    selectedNet='Orange';
  }else{
    nets.innerHTML=`<button class="net-btn on" id="net-0" onclick="selectNet(this)">Africell</button><button class="net-btn" id="net-1" onclick="selectNet(this)">QCell</button><button class="net-btn" id="net-2" onclick="selectNet(this)">Gamcel</button><button class="net-btn" id="net-3" onclick="selectNet(this)">Comium</button>`;
    selectedNet='Africell';
  }
  if(lbl)lbl.textContent='Amount ('+cur+')';
  const rentLbl=document.getElementById('rent-amt-lbl');
  if(rentLbl)rentLbl.textContent='Amount ('+cur+')';
}

function showBillConf(icon,title,sub,amount,detail,status){
  document.getElementById('bc-icon').textContent=icon;
  document.getElementById('bc-title').textContent=title;
  document.getElementById('bc-sub').textContent=sub;
  document.getElementById('bc-amount').textContent=amount;
  document.getElementById('bc-detail').textContent=detail;
  document.getElementById('bc-status').textContent=status||'Processing ⏳';
  go('billconf');
}

function payNawec(){
  const meter=document.getElementById('nawec-meter').value.trim()||'05-12345-6';
  const amt=parseInt(document.getElementById('nawec-amt').value)||500;
  showBillConf('⚡','CashPower Topped Up!','Power will arrive in ~2 minutes.',amt.toLocaleString()+' GMD','Meter: '+meter,'Sent ✅');
}

function paySchool(){
  const member=document.getElementById('school-member').value;
  const amt=parseInt(document.getElementById('school-amt').value)||3500;
  showBillConf('🎓','School Fees Paid!','Payment confirmed with school.','GMD '+amt.toLocaleString(),'For: '+member,'Confirmed ✅');
}

function payWater(){
  const acct=document.getElementById('water-acct').value.trim()||'W-88321';
  const amt=parseInt(document.getElementById('water-amt').value)||300;
  showBillConf('💧','Water Bill Paid!','NAWEC Water · Account updated.','GMD '+amt.toLocaleString(),'Account: '+acct,'Processing ⏳');
}

function payRent(){
  const landlord=document.getElementById('rent-landlord').value.trim()||'Landlord';
  const address=document.getElementById('rent-address').value.trim()||'—';
  const amt=parseInt(document.getElementById('rent-amt').value)||4000;
  const method=document.getElementById('rent-method').value;
  const cur=countryData[currentCountry].currency;
  showBillConf('🏠','Rent Paid!','Your landlord has been notified.',amt.toLocaleString()+' '+cur,landlord+' · '+address,'Sent via '+method+' ✅');
}

function payMobile(){
  const phone=document.getElementById('mobile-phone').value.trim()||'+220 7XX XXXX';
  const amt=parseInt(document.getElementById('mobile-amt').value)||100;
  const cur=countryData[currentCountry].currency;
  showBillConf('📱','Top-Up Sent!',selectedNet+' airtime delivered instantly.',amt.toLocaleString()+' '+cur,phone+' · '+selectedNet,'Sent ✅');
}

// Chat
function sendChat(){
  const inp=document.getElementById('cin');
  const txt=inp.value.trim();
  if(!txt)return;
  const area=document.getElementById('chat-area');
  const t=new Date().toLocaleTimeString('en',{hour:'2-digit',minute:'2-digit'});
  area.innerHTML+=`<div class="bbl me"><div class="bbl-in">${escHtml(txt)}</div><div class="bbl-tm">${t}</div></div>`;
  inp.value='';
  area.scrollTop=area.scrollHeight;
  const replies=["Inshallah, I'll be waiting. Allah bless you! 🙏","Ok habibi, thank you so much 💚","Alhamdulillah. You're always there for us.","Ok my son. We're doing fine here, don't worry about us."];
  setTimeout(()=>{
    area.innerHTML+=`<div class="bbl th"><div class="bbl-in">${replies[Math.floor(Math.random()*replies.length)]}</div><div class="bbl-tm">${t}</div></div>`;
    area.scrollTop=area.scrollHeight;
  },1400);
}
const cin=document.getElementById('cin');
if(cin)cin.addEventListener('keydown',e=>{if(e.key==='Enter')sendChat()});

// AI
let currentLang='English';
function setLang(el){
  document.querySelectorAll('.lt').forEach(x=>x.classList.remove('on'));
  el.classList.add('on');
  currentLang=el.textContent;
}

// ── Offline AI engine ──
const AI_R={
  rate:{
    kw:['rate','exchange','eur','gmd','xof','cfa','currency','dalasi rate','best rate','today','kurs','taux'],
    en:[
      "Today's rate is around 1 EUR = 79.6 GMD — pretty solid, better than most of last month. For Senegal the CFA is fixed at 655 XOF per Euro and never moves, so no surprises there. If you've been waiting for a good moment, now is decent. Inshallah it stays this way! 💚",
      "EUR/GMD is sitting at about 79.6 right now — above average for this quarter. For Senegal, 655 XOF per Euro is fixed forever (pegged to the Euro), so zero risk. I'd say it's a good day to send today. ⚡"
    ],
    md:[
      "Sii, 1 Euro ye 79.6 GMD le bi tuma nin na. A ka nyi — a fara kɔrɔ kelen kan ka tɛmɛ kalo tɛmɛnen. Senegal na, 655 XOF le a dɔn, a bɛ dɔn kelen dɔn. Inshallah, bi ye tuma ɲuman ka wari ci! 💚",
      "EUR bɛ 79.6 GMD na bi — a ka fisa kosɛbɛ. Senegal na, 655 XOF le, a tɛ yɛlɛma. Inshallah i ka wari ci bi! ⚡"
    ],
    wo:[
      "Rate bi dafa 1 EUR = 79.6 GMD — dafa baax, gën yu jiitu ci wergi bu jiitu. Sénégal bi, 655 XOF bu dëggël, dafa siiw. Léegi mooy am li baax ak ci dem. Inshallah! 💚",
      "EUR/GMD bi dafa 79.6 — dafa passé ci kaw ci cee bi jiitu. Sénégal 655 XOF — dafa jëm bu amul yépp. Dem ko bi léegi! ⚡"
    ],
    fr:[
      "Le taux aujourd'hui est d'environ 1 EUR = 79,6 GMD — c'est plutôt bien, au-dessus de la moyenne du mois dernier. Pour le Sénégal, le CFA est fixé à 655 XOF par euro et ne bouge jamais. Si tu attendais le bon moment pour envoyer, c'est maintenant. Inch'Allah ça reste ! 💚",
      "EUR/GMD est à 79,6 en ce moment — correct pour ce trimestre. Le XOF ne change jamais — 655 par euro, ancré à jamais. C'est un bon jour pour envoyer de l'argent. ⚡"
    ]
  },
  send:{
    kw:['send','transfer','remit','sending','how to send','envoyer','envoie','wari ci','payer','payment'],
    en:[
      "Sending through Dalasi is quick — tap Send Money, choose Gambia or Senegal, pick your recipient and enter the amount. Wave Wallet is fastest (instant, free to receive), bank transfer takes 1–2 hours, APS cash pickup is same day. Fee is just €0.99 flat whatever you send — way cheaper than Western Union. 💸",
      "Takes about 2 minutes. Pick country, amount, delivery method — Wave is your best bet for speed. Your family gets a notification the second it arrives. Fee is €0.99 no matter how much you send. Hard to beat! 💚"
    ],
    md:[
      "Wari ciyo ka nɔgɔ — 'Send Money' daminɛ, yɔrɔ sugandi (Gambia waa Senegal), mɔgɔ sugandi, ka wari jate. Wave Wallet ye jan ka fɔlɔ — i bangarɔ bɛ se wari la ka kɛrɛfɛ. Fee ye Euro 0.99 dɔrɔn. Ka fisa kosɛbɛ! 💸",
      "Miniti fila dɔrɔn. Wave ye jan, i bangarɔ bɛ wari sɔrɔ ka kɛrɛfɛ. Fee: €0.99. Inshallah! 💚"
    ],
    wo:[
      "Dafa yomb — dëkk 'Send Money', tann Gambie walla Sénégal, tann njabootam bi, bind xaalis bi. Wave Wallet dafa màtt — instant, free. Fee bi dafa 0,99 € rekk, lu mel ni dara. Dafa di lu baax gën ci APS! 💸",
      "2 miniti rekk la. Tann dëkk bi, xaalis bi, ak moyen bi — Wave la gën. Njabootam bi dafay jël message ci télép bi. €0,99 rekk. 💚"
    ],
    fr:[
      "Envoyer avec Dalasi, c'est rapide — appuie sur Envoyer, choisis Gambie ou Sénégal, sélectionne le destinataire et saisis le montant. Wave Wallet est le plus rapide (instantané, gratuit à la réception), virement bancaire en 1–2h, retrait APS le jour même. Frais fixes : 0,99€ quelle que soit la somme. Bien moins cher que Western Union. 💸",
      "Ça prend 2 minutes. Pays, montant, mode de livraison — Wave c'est le top pour la vitesse. Ta famille reçoit une notification dès que l'argent arrive. 0,99€ de frais, peu importe le montant. Imbattable ! 💚"
    ]
  },
  nawec:{
    kw:['nawec','cashpower','cash power','electricity','power','electric','light','courant','électric','meter','compteur'],
    en:[
      "To top up CashPower, go to Pay Bills → NAWEC CashPower, enter the meter number and amount in GMD. It processes instantly — the power token lands on your family's meter in about 2 minutes. No need to go to a shop or call anyone. Just need the meter number from your family! 💡",
      "NAWEC CashPower is built right into Dalasi. Enter the meter number (ask family to WhatsApp it), put in your amount, hit Pay. Power arrives in 2 minutes flat. Alhamdulillah, so much easier than before! ⚡"
    ],
    md:[
      "CashPower fɔlɔ ka nɔgɔ — 'Pay Bills' daminɛ, NAWEC CashPower sugandi, meter number ni wari jate GMD na. Miniti fila kɔnɔ, power bɛ se. Alhamdulillah! ⚡",
      "I ka bangarɔ meters number don i la — i bɛ CashPower to ka nɔgɔ. Miniti fila dɔrɔn. Nɔgɔ kosɛbɛ! 💡"
    ],
    wo:[
      "CashPower bi dafa yomb ci Dalasi bi. Dëkk 'Pay Bills', tann NAWEC CashPower, bind numéro compteur ak xaalis bi. Ci 2 minute, électricité bi dafay ànd. Alhamdulillah! ⚡",
      "Numéro compteur bi — danga ko wécc ci WhatsApp. Ci kanam jëkk, waxtaan yi dafay jóg. Yomb lool! 💡"
    ],
    fr:[
      "Pour recharger le CashPower, va dans Payer des factures → NAWEC CashPower, saisis le numéro de compteur et le montant en GMD. C'est instantané — le token électrique arrive sur le compteur de ta famille en 2 minutes. Juste besoin du numéro de compteur ! 💡",
      "La recharge NAWEC est directement dans Dalasi. Numéro de compteur (demande à la famille de te l'envoyer sur WhatsApp), montant, Payer. Électricité en 2 minutes. Alhamdulillah, tellement plus simple ! ⚡"
    ]
  },
  visa:{
    kw:['visa','aufenthaltstitel','residence','permit','renew','ma 35','anmeldung','austri','wien','vienna','sozialvers','niederlassung','renouvell','papier'],
    en:[
      "For Aufenthaltstitel renewal in Vienna: apply at MA 35 (or online at mein.wien.gv.at) at least 3 months before it expires. Documents needed: valid passport, current permit, proof of income (last 3 payslips or Lohnzettel), Meldezettel (address registration), and the application form. Processing takes 4–8 weeks. They'll give you a Verfahrensanordnung so you can keep working while you wait. 📋",
      "Aufenthaltstitel renewal — start 3 months early, MA 35 gets very busy. Key docs: passport, current permit, Meldezettel, last 3 payslips. Book appointment at mein.wien.gv.at. Don't wait until the last month. Inshallah it goes smoothly for you! 🇦🇹"
    ],
    md:[
      "Aufenthaltstitel yiriwali kama, i ka daminɛ kalo saba ka ɲɛsin a kɔrɔ. I bɛ kafu olu ɲini: passport, permit kɔrɔ, wari sɔrɔli dili (Lohnzettel), ati Meldezettel. MA 35 bɛ Vienna. Inshallah ka nɔgɔ! 📋",
      "MA 35 bɛ sɔrɔ Vienna — kalo saba ka ɲɛsin a kɔrɔ, i ka daminɛ. Inshallah ka nɔgɔ i ye! 🇦🇹"
    ],
    wo:[
      "Aufenthaltstitel yéggalaat ci Wien: jëgg ci MA 35 (walla mein.wien.gv.at) ci kanam bu nekk ci 3 weer. Jëkkëram: passeport, permis bi, Meldezettel, ak liggéeyam (3 fiches de paie). Dëgg ci 4-8 weer la rekk. Inshallah dafa dem bu baax! 📋",
      "Dëkk ci mein.wien.gv.at benn rendez-vous ci MA 35. 3 weer la ci kanam — Inshallah dafa jëm bu baax! 🇦🇹"
    ],
    fr:[
      "Pour renouveler ton Aufenthaltstitel à Vienne : dépose ta demande à MA 35 (ou sur mein.wien.gv.at) au moins 3 mois avant l'expiration. Documents : passeport valide, permis actuel, justificatif de revenus (3 dernières fiches de paie ou Lohnzettel), Meldezettel. Délai : 4–8 semaines. Ils te donnent un Verfahrensanordnung pour continuer à travailler en attendant. 📋",
      "Renouvellement Aufenthaltstitel — commence 3 mois à l'avance, MA 35 est très chargé. Docs clés : passeport, permis actuel, Meldezettel, 3 dernières fiches de paie. Rendez-vous sur mein.wien.gv.at. Inch'Allah ça se passe bien ! 🇦🇹"
    ]
  },
  scholarship:{
    kw:['scholarship','study','university','education','grant','bursary','bourse','étude','school abroad','study abroad','studienstipendium'],
    en:[
      "Great options for Gambians: the Turkish Government Scholarship (Türkiye Bursları) is fully funded — covers tuition, accommodation and a monthly allowance. Very popular, deadline usually February. Also check the Commonwealth Scholarship for UK, DAAD for Germany, and OIC scholarships. Applications typically open January–March. 🎓",
      "For fully funded scholarships: Türkiye Bursları is the top pick for Gambians right now — free tuition, housing and living allowance. OIC has positions for member countries. For Austria, check the OeAD website. Inshallah your family gets one! 🎓"
    ],
    md:[
      "Gansan kɔlɔsilaw bɛ Gambia deenw ye: Turkey Bursları ye gansan kɔlɔsi kɔrɔ — a bɛ se kalan sara, so sara, ni wari min na dɔrɔn. OIC gansan kɔlɔsi fana bɛ olu ɲini. I bɛ daminɛ January waa March cɛ. Inshallah i ka deenw bɛ se! 🎓",
      "Turkey Bursları — o ye sɔrɔ fɔlɔ Gambia deenw ye. Fana bɛ DAAD ye Germany, ni Commonwealth UK kama. Inshallah! 🎓"
    ],
    wo:[
      "Bourse yu bari la: Türkiye Bursları dafay fund ak yépp — cours, kër, ak argent diggante. Dafa dem ci Gambie ndax bu bari. OIC am bourse, DAAD ci Allemagne, Commonwealth ci UK. Ñu am mbir ci Janvier - Mars. Inshallah njabootam bi da ko jël! 🎓",
      "Türkiye Bursları la gën jëm ci kanam — dafay fund ak yépp, Gambie am seen diiwaan. Inshallah! 🎓"
    ],
    fr:[
      "Excellentes options pour les Gambiens : la bourse du gouvernement turc (Türkiye Bursları) est entièrement financée — frais de scolarité, logement et allocation mensuelle inclus. Très populaire, délai généralement en février. Vérifiez aussi le Commonwealth Scholarship pour le Royaume-Uni, le DAAD pour l'Allemagne et les bourses OCI. Candidatures en janvier–mars. Inch'Allah ! 🎓",
      "Pour les bourses entièrement financées : Türkiye Bursları est le meilleur choix pour les Gambiens — tuition, logement, et allocation. L'OCI a des places pour les pays membres. Pour l'Autriche, consultez le site OeAD. Inch'Allah votre famille en bénéficiera ! 🎓"
    ]
  },
  community:{
    kw:['community','event','prater','wien','vienna','gambian','senegalese','meetup','association','diaspora event','gathering','near','nearby'],
    en:[
      "The main community hub in Vienna is the Gambian Community Association of Austria — regular meetups, Eid celebrations and cultural events. Big one coming: Gambia Community Day on May 18 at Prater Park (142 people going!). Senegalese Diaspora Day is June 7 at Augarten. Check the Community tab in Dalasi for everything. 🌍",
      "Vienna has a solid West African community. Gambia Community Day May 18 (Prater Park), Senegalese Diaspora Day June 7 (Augarten). The Community tab in Dalasi shows people near you, news, jobs and events all in one place. Alhamdulillah we're not alone here! 🎉"
    ],
    md:[
      "Vienna bɛ Gambia mɔgɔw bɛ kosɛbɛ — Gambian Community Association of Austria bɛ segin olu ɲɛ la. Gambia Community Day bɛ mai 18 Prater Park — mɔgɔ 142 bɛ taa! Senegal Community Day bɛ juin 7 Augarten. Community tab kɛ Dalasi kɔnɔ! Alhamdulillah! 🌍",
      "Mai 18 bɛ Gambia Community Day Vienna — Prater Park. Juin 7 bɛ Senegal Diaspora Day. Community tab kɛ Dalasi kɔnɔ! 🎉"
    ],
    wo:[
      "Dëkk bi am ci kanam Gambie ak Sénégal. Gambia Community Day ci 18 Mai ci Prater Park — ñaari témeeri ñaari nit ñu dem ko! Sénégalais Diaspora Day ci 7 Juin ci Augarten. Dëkk Community tab ci Dalasi bi — nit ñu ci biir, xibaar, ak ndaje. Alhamdulillah! 🎉",
      "Gambia Community Day bi ci 18 Mai — Prater Park. Sénégal Diaspora Day bi ci 7 Juin — Augarten. Community tab ci Dalasi bi dafa amoon ak yépp! 🌍"
    ],
    fr:[
      "La principale communauté gambienne à Vienne est la Gambian Community Association of Austria — réunions régulières, célébrations de l'Aïd et événements culturels. Grand événement à venir : Journée de la communauté gambienne le 18 mai au Prater Park (142 participants !). Journée de la diaspora sénégalaise le 7 juin à l'Augarten. 🌍",
      "Vienne a une belle communauté ouest-africaine. Journée gambienne le 18 mai (Prater Park), Journée sénégalaise le 7 juin (Augarten). L'onglet Communauté dans Dalasi montre les gens près de toi, les actualités et les événements. Alhamdulillah, on n'est pas seuls ! 🎉"
    ]
  },
  wave:{
    kw:['wave','wallet','mobile money','wave wallet','wave app','wave account','orange money'],
    en:[
      "Wave Wallet is the fastest way for your family to receive money in both Gambia and Senegal. Instant, free to receive, and they get a notification immediately. Most people in Gambia and Senegal now have Wave — your family can open one free with just a phone number. No bank account needed. 📱",
      "Wave is dominant in both Gambia and Senegal now. To set up: family downloads the Wave app (free), registers with their phone number, done. When sending, just select Wave as the delivery method. Money arrives instantly. Alhamdulillah it's so much better than queuing at a branch! 📱"
    ],
    md:[
      "Wave Wallet ye ca ka fɔlɔ wari sɔrɔli kama Gambia ni Senegal na. A ka nɔgɔ — app min ka nɔgɔ, telefon number dɔrɔn ka ɲini. Wari bɛ se ka kɛrɛfɛ. Alhamdulillah! 📱",
      "Wave ye jan — i bangarɔ bɛ se app min, olu bɛ sɔrɔ wari ka kɛrɛfɛ. Dalasi bɛ se Wave sugandi wari ciyo na. 📱"
    ],
    wo:[
      "Wave Wallet dafa di lu gën baax ci Gambie ak Sénégal. Yomb — app bi dafay free, njabootam bi boo yóbbu ko benn numéro télép bi sax, instant. Dalasi bi dafa baax ak Wave. Alhamdulillah! 📱",
      "Wave bi dafay dëkk ci Gambie ak Sénégal. Woy ci app store, bind numéro bi — jëm! Dalasi bi dafa yomb ak Wave — tann ko ci mode livraison bi. 📱"
    ],
    fr:[
      "Wave Wallet est le meilleur moyen pour ta famille de recevoir de l'argent en Gambie et au Sénégal. Instantané, gratuit à la réception, notification immédiate. La plupart ont maintenant Wave — ta famille peut en ouvrir un gratuitement avec juste un numéro de téléphone. Aucun compte bancaire nécessaire. 📱",
      "Wave est dominant en Gambie et au Sénégal. Pour s'inscrire : la famille télécharge l'app Wave (gratuite), s'inscrit avec son numéro. De ton côté, sélectionne Wave comme mode de livraison. L'argent arrive instantanément. Alhamdulillah ! 📱"
    ]
  },
  aps:{
    kw:['aps','western union','compare','comparison','fee','cheaper','cheaper than','vs','wu','money gram','moneygram','fees','commission'],
    en:[
      "APS vs Dalasi — honest breakdown. APS charges 3–5% and cash pickup only, so your family walks to a branch. Dalasi is €0.99 flat and delivers to Wave, bank or cash. On €200, APS costs you €6–10; Dalasi costs €0.99. Over a year of monthly sends that's €60–120 difference. APS's only edge: physical presence for older relatives who prefer cash. 💸",
      "Dalasi beats APS on fees every time. APS = 3–5% commission, Dalasi = €0.99 flat. Speed is similar, delivery options are better (Wave, bank or cash pickup). If your family is on Wave, there's genuinely no reason to use APS. Keep that money for the family! 💚"
    ],
    md:[
      "APS ni Dalasi kɔlɔsi: APS bɛ mara 3-5% — wari €200 ci, APS bɛ se €6-10. Dalasi bɛ se €0.99 dɔrɔn. Kalo kelen kelen na, i bɛ wari caman halabu. Dalasi ye ca kosɛbɛ! 💸",
      "Dalasi ye ca — €0.99 dɔrɔn. APS bɛ caman ɲini. I ka halabu wari o bangarɔ ye! 💚"
    ],
    wo:[
      "APS ak Dalasi — dafay yomb. APS dafa jël 3-5%, Dalasi dafa jël 0,99 € rekk. Ci €200, APS dafa jël €6-10; Dalasi €0,99. Ci kër bu kanam, danga halabu €60-120. Dalasi dafa gën ci tëëm, vitesse, ak yépp! 💸",
      "Dalasi dafa gën APS — €0.99 rekk, APS 3-5%. Dalasi am Wave, bank, ak argent espèces. Njabootam bi dafay jël xam xam instant. 💚"
    ],
    fr:[
      "APS vs Dalasi — comparaison honnête. APS prend 3–5% et retrait espèces uniquement, ta famille doit se déplacer. Dalasi = 0,99€ fixe, livraison sur Wave, banque ou espèces. Sur 200€, APS te coûte 6–10€ ; Dalasi 0,99€. Sur un an d'envois mensuels, c'est 60–120€ d'économie. Seul avantage d'APS : présence physique pour les proches qui préfèrent le cash. 💸",
      "Dalasi gagne sur les frais à chaque fois. APS = 3–5%, Dalasi = 0,99€ fixe. Vitesse similaire, meilleures options de livraison. Si ta famille est sur Wave, il n'y a aucune raison d'utiliser APS. Garde cet argent pour ta famille ! 💚"
    ]
  }
};

const AI_DEFAULT={
  en:["Good question! I can help with: exchange rates, sending money to Gambia or Senegal, NAWEC CashPower top-up, Wave Wallet, Austrian visa renewal (Aufenthaltstitel), scholarships for Gambians, community events in Vienna, and comparing Dalasi vs APS. What would you like to know? 😊","I'm here to help with anything related to Gambia, Senegal, or life in Austria. Ask me about exchange rates, how to send money, CashPower, visa renewal, scholarships, or community events! 🌍"],
  md:["N'na fɔ! N bɛ se i dɛmɛ wari ciyo, rate dɔn, NAWEC CashPower, visa yiriwali, gansan kɔlɔsilaw, ani Vienna community la. Mun bɛ i ɲini? 😊","N bɛ here — mun bɛ i ɲini wari ciyo waa rate waa Vienna la? 🌍"],
  wo:["Dafa baax! Mangi feebar ak taux bi, xaalis bi, CashPower, renouvellement visa, bourse, ak community bi ci Wien. Lu baax la? 😊","Maa ngi fi ci yaw — taux bi, xaalis bi, CashPower, visa bi, walla community bi ci Wien? 🌍"],
  fr:["Bonne question ! Je peux t'aider avec les taux de change, l'envoi d'argent en Gambie ou au Sénégal, le rechargement NAWEC CashPower, Wave Wallet, le renouvellement de visa autrichien, les bourses et les événements communautaires à Vienne. Qu'est-ce que tu voudrais savoir ? 😊","Je suis là pour tout ce qui concerne la Gambie, le Sénégal ou la vie en Autriche. Essaie de demander sur les taux de change, l'envoi d'argent, le CashPower, le visa ou les événements à Vienne ! 🌍"]
};

function matchAITopic(txt){
  const q=txt.toLowerCase();
  for(const[key,data]of Object.entries(AI_R)){
    if(data.kw.some(k=>q.includes(k)))return key;
  }
  return null;
}
function getLangKey(){
  if(currentLang==='Mandinka')return 'md';
  if(currentLang==='Wolof')return 'wo';
  if(currentLang==='Français')return 'fr';
  return 'en';
}
function pickRandom(arr){return arr[Math.floor(Math.random()*arr.length)];}

async function sendAI(){
  const inp=document.getElementById('ai-in');
  const msgs=document.getElementById('ai-msgs');
  const txt=inp.value.trim();
  if(!txt)return;
  inp.value='';
  const t=new Date().toLocaleTimeString('en',{hour:'2-digit',minute:'2-digit'});
  msgs.innerHTML+=`<div class="msg us"><div class="msg-bbl">${escHtml(txt)}</div><div class="msg-tm">${t}</div></div>`;
  msgs.innerHTML+=`<div class="typing" id="typ"><span></span><span></span><span></span></div>`;
  msgs.scrollTop=msgs.scrollHeight;
  await new Promise(r=>setTimeout(r,700+Math.random()*600));
  document.getElementById('typ')?.remove();
  const topic=matchAITopic(txt);
  const lang=getLangKey();
  const reply=topic&&AI_R[topic]?.[lang]
    ?pickRandom(AI_R[topic][lang])
    :pickRandom(AI_DEFAULT[lang]);
  msgs.innerHTML+=`<div class="msg ai"><div class="msg-bbl">${escHtml(reply).replace(/\n/g,'<br>')}</div><div class="msg-tm">${t}</div></div>`;
  msgs.scrollTop=msgs.scrollHeight;
}

function askQ(q){
  document.getElementById('ai-in').value=q;
  go('ai');
  setTimeout(sendAI,400);
}

// Invest
let investTimer=null;
function investInterest(btn){
  btn.textContent='Noted ✓';
  btn.disabled=true;
  const toast=document.getElementById('invest-toast');
  if(toast){
    toast.style.display='block';
    clearTimeout(investTimer);
    investTimer=setTimeout(()=>toast.style.display='none',3500);
  }
}

function escHtml(t){
  return t.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}
</script>
</body>
</html>
