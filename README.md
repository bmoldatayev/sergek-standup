[index (9).html](https://github.com/user-attachments/files/29235845/index.9.html)
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Процессный офис</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
:root{
  --navy:#0D2B4E;--navy2:#1a3d6b;--accent:#2E7CF6;--accent-light:#EBF3FF;
  --green:#16A34A;--green-bg:#DCFCE7;--yellow:#D97706;--yellow-bg:#FEF3C7;
  --red:#DC2626;--red-bg:#FEE2E2;--purple:#7C3AED;--purple-bg:#EDE9FE;
  --gray-50:#F8FAFC;--gray-100:#F1F5F9;--gray-200:#E2E8F0;
  --gray-400:#94A3B8;--gray-500:#64748B;--gray-700:#334155;--gray-900:#0F172A;
  --white:#FFFFFF;--radius:10px;--radius-sm:6px;
  --shadow:0 1px 3px rgba(0,0,0,.07),0 1px 2px rgba(0,0,0,.05);
  --shadow-md:0 4px 16px rgba(0,0,0,.10);
  --shadow-lg:0 10px 40px rgba(0,0,0,.15);
}
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Inter',sans-serif;background:var(--gray-50);color:var(--gray-900);font-size:14px;line-height:1.5;min-height:100vh;}

/* ─── HEADER ─── */
.hdr{background:var(--navy);height:52px;padding:0 20px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:200;box-shadow:0 2px 8px rgba(0,0,0,.2);}
.hdr-brand{display:flex;align-items:center;gap:10px;}
.hdr-dot{width:7px;height:7px;background:var(--accent);border-radius:50%;}
.hdr-title{font-size:14px;font-weight:600;color:white;letter-spacing:.2px;}
.hdr-right{display:flex;align-items:center;gap:10px;}
.hdr-date{font-size:11px;color:rgba(255,255,255,.45);}
.auth-btn{background:rgba(255,255,255,.12);color:white;border:1px solid rgba(255,255,255,.2);padding:5px 12px;border-radius:var(--radius-sm);font-size:12px;font-weight:500;cursor:pointer;transition:background .15s;}
.auth-btn:hover{background:rgba(255,255,255,.2);}
.user-chip{display:flex;align-items:center;gap:7px;font-size:12px;color:rgba(255,255,255,.85);}
.user-av{width:26px;height:26px;border-radius:50%;border:1.5px solid rgba(255,255,255,.3);}
.logout-btn{background:none;border:none;color:rgba(255,255,255,.5);font-size:11px;cursor:pointer;padding:2px 6px;}
.logout-btn:hover{color:white;}
.ro-pill{background:var(--yellow-bg);color:var(--yellow);font-size:11px;font-weight:600;padding:2px 8px;border-radius:20px;}

/* ─── NAV ─── */
.nav{background:white;border-bottom:1px solid var(--gray-200);padding:0 20px;display:flex;gap:2px;position:sticky;top:52px;z-index:190;}
.nav-item{padding:12px 16px;font-size:13px;font-weight:500;color:var(--gray-400);cursor:pointer;border-bottom:2px solid transparent;display:flex;align-items:center;gap:6px;white-space:nowrap;transition:color .15s;}
.nav-item:hover{color:var(--gray-700);}
.nav-item.active{color:var(--accent);border-bottom-color:var(--accent);}
.nav-badge{background:var(--gray-100);color:var(--gray-500);font-size:10px;font-weight:700;padding:1px 6px;border-radius:10px;}
.nav-item.active .nav-badge{background:var(--accent-light);color:var(--accent);}

/* ─── LAYOUT ─── */
.page{padding:20px;max-width:1320px;margin:0 auto;}
.view{display:none;}.view.active{display:block;}

/* ─── BUTTONS ─── */
.btn{display:inline-flex;align-items:center;gap:5px;padding:7px 14px;border-radius:var(--radius-sm);font-size:13px;font-weight:500;border:none;cursor:pointer;transition:all .15s;font-family:inherit;}
.btn-primary{background:var(--accent);color:white;}.btn-primary:hover{background:#1a6de8;}
.btn-outline{background:white;color:var(--gray-700);border:1px solid var(--gray-200);}.btn-outline:hover{background:var(--gray-50);}
.btn-ghost{background:transparent;color:var(--gray-500);border:1px solid var(--gray-200);}.btn-ghost:hover{background:var(--gray-100);}
.btn-danger{background:var(--red-bg);color:var(--red);border:none;}.btn-danger:hover{background:#fecaca;}
.btn-warn{background:var(--yellow-bg);color:var(--yellow);border:none;}
.btn-green{background:var(--green-bg);color:var(--green);border:none;}
.btn-sm{padding:4px 10px;font-size:12px;}
.btn-xs{padding:2px 8px;font-size:11px;}

/* ─── TOOLBAR ─── */
.toolbar{display:flex;align-items:center;gap:10px;margin-bottom:18px;flex-wrap:wrap;}
.toolbar-title{font-size:18px;font-weight:700;color:var(--navy);flex:1;}
.toolbar-sub{font-size:12px;color:var(--gray-400);font-weight:400;margin-left:6px;}

/* ─── TODAY SCREEN ─── */
.today-layout{display:grid;grid-template-columns:1fr;gap:16px;}

/* Yesterday banner */
.yest-banner{background:linear-gradient(135deg,#fffbeb,#fef2f2);border:1px solid #fcd34d;border-radius:var(--radius);padding:0;overflow:hidden;}
.yest-header{display:flex;align-items:center;justify-content:space-between;padding:12px 16px;cursor:pointer;}
.yest-header-left{display:flex;align-items:center;gap:10px;}
.yest-icon{font-size:16px;}
.yest-title{font-weight:600;font-size:13px;color:#92400e;}
.yest-count{background:#fde68a;color:#92400e;font-size:11px;font-weight:700;padding:2px 8px;border-radius:10px;}
.yest-actions{display:flex;gap:8px;}
.yest-body{padding:0 16px 12px;display:none;}
.yest-body.open{display:block;}
.yest-task-row{display:flex;align-items:center;gap:10px;padding:8px 0;border-bottom:1px solid rgba(0,0,0,.05);}
.yest-task-row:last-child{border-bottom:none;}
.yest-task-name{flex:1;font-size:13px;font-weight:500;}
.yest-task-sub{font-size:11px;color:var(--gray-400);}

/* Person sections */
.person-section{background:white;border-radius:var(--radius);box-shadow:var(--shadow);overflow:hidden;margin-bottom:12px;}
.person-header{display:flex;align-items:center;gap:12px;padding:14px 16px;border-bottom:1px solid var(--gray-100);}
.person-av{width:34px;height:34px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:14px;font-weight:700;color:white;flex-shrink:0;}
.person-name{font-weight:600;font-size:14px;cursor:pointer;}.person-name:hover{color:var(--accent);}
.person-role{font-size:11px;color:var(--gray-400);}
.person-stats{margin-left:auto;display:flex;gap:8px;align-items:center;}
.pstat{text-align:center;}
.pstat-num{font-size:16px;font-weight:700;color:var(--navy);}
.pstat-lbl{font-size:10px;color:var(--gray-400);text-transform:uppercase;letter-spacing:.4px;}
.pstat.g .pstat-num{color:var(--green);}
.pstat.y .pstat-num{color:var(--yellow);}
.pstat-div{width:1px;height:28px;background:var(--gray-200);}
.person-tasks{padding:8px 0;}

/* Task row */
.task-row{display:grid;grid-template-columns:1fr auto auto auto;gap:10px;align-items:center;padding:10px 16px;transition:background .1s;}
.task-row:hover{background:var(--gray-50);}
.task-row.done .task-name{text-decoration:line-through;opacity:.5;}
.task-name{font-weight:500;font-size:13px;}
.task-detail{font-size:11px;color:var(--gray-400);margin-top:2px;}
.task-parent{font-size:10px;color:var(--accent);margin-top:1px;opacity:.7;}
.tr-badge{font-size:10px;font-weight:700;background:var(--red-bg);color:var(--red);padding:2px 6px;border-radius:8px;}
.task-actions{display:flex;gap:4px;opacity:0;transition:opacity .15s;}
.task-row:hover .task-actions{opacity:1;}

/* Status select */
.ssel{border:1px solid var(--gray-200);background:white;font-size:12px;font-weight:500;cursor:pointer;outline:none;padding:4px 8px;border-radius:var(--radius-sm);font-family:inherit;color:var(--gray-700);}
.ssel:disabled{opacity:.6;cursor:default;}
.ssel.done{background:var(--green-bg);color:var(--green);border-color:var(--green-bg);}
.ssel.wip{background:var(--yellow-bg);color:var(--yellow);border-color:var(--yellow-bg);}
.ssel.partial{background:#fef9c3;color:#854d0e;border-color:#fef9c3;}

/* ─── WEEK GRID ─── */
.week-nav-row{display:flex;align-items:center;gap:10px;margin-bottom:16px;}
.week-nav-lbl{font-size:13px;font-weight:600;color:var(--navy);background:var(--gray-100);padding:6px 16px;border-radius:var(--radius-sm);min-width:140px;text-align:center;}
.nav-arrow{width:30px;height:30px;border-radius:var(--radius-sm);border:1px solid var(--gray-200);background:white;cursor:pointer;font-size:16px;display:flex;align-items:center;justify-content:center;}
.nav-arrow:hover{background:var(--gray-100);}

.week-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:10px;}
.week-day-col{background:white;border-radius:var(--radius);box-shadow:var(--shadow);overflow:hidden;}
.week-day-col.today-col{border:2px solid var(--accent);}
.week-day-hdr{padding:10px 12px;border-bottom:1px solid var(--gray-100);display:flex;align-items:center;justify-content:space-between;}
.week-day-name{font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--gray-400);}
.week-day-num{font-size:18px;font-weight:700;color:var(--navy);}
.week-day-col.today-col .week-day-num{color:var(--accent);}
.week-day-count{font-size:10px;background:var(--accent-light);color:var(--accent);padding:2px 6px;border-radius:8px;font-weight:700;}
.week-day-tasks{padding:8px;}
.week-task-chip{padding:5px 8px;border-radius:var(--radius-sm);margin-bottom:4px;font-size:11px;cursor:pointer;transition:opacity .15s;display:flex;align-items:center;gap:4px;}
.week-task-chip:hover{opacity:.8;}
.week-task-chip .chip-name{flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.week-task-chip .chip-tr{font-size:9px;font-weight:700;}
.week-empty{font-size:11px;color:var(--gray-400);text-align:center;padding:16px 8px;}
.week-add-btn{width:100%;border:none;background:transparent;color:var(--accent);font-size:12px;cursor:pointer;padding:6px;border-top:1px solid var(--gray-100);}
.week-add-btn:hover{background:var(--accent-light);}

/* ─── MASTER ─── */
.master-tree{background:white;border-radius:var(--radius);box-shadow:var(--shadow);overflow:hidden;}
.master-dir-hdr{background:var(--gray-50);padding:10px 16px;font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.8px;color:var(--gray-400);border-bottom:1px solid var(--gray-200);display:flex;align-items:center;gap:8px;}
.master-task-row{border-bottom:1px solid var(--gray-100);}
.master-task-row:last-child{border-bottom:none;}
.mtr-main{display:flex;align-items:center;gap:10px;padding:11px 16px;cursor:pointer;transition:background .1s;}
.mtr-main:hover{background:var(--gray-50);}
.mtr-expand{width:20px;height:20px;border-radius:4px;border:1px solid var(--gray-200);background:white;cursor:pointer;font-size:11px;display:flex;align-items:center;justify-content:center;flex-shrink:0;color:var(--gray-400);}
.mtr-expand:hover{background:var(--accent-light);color:var(--accent);border-color:var(--accent);}
.mtr-name{flex:1;font-weight:600;font-size:13px;}
.mtr-detail{font-size:11px;color:var(--gray-400);margin-top:1px;}
.mtr-actions{display:flex;gap:4px;opacity:0;}
.mtr-main:hover .mtr-actions{opacity:1;}

/* Dir tag */
.dtag{display:inline-block;font-size:10px;font-weight:700;padding:2px 7px;border-radius:4px;white-space:nowrap;flex-shrink:0;}
.dtag.Проекты{background:#EDE9FE;color:#6D28D9;}
.dtag.ITAI,.dtag["IT|AI"]{background:#DBEAFE;color:#1D4ED8;}
.dtag.Методология{background:#FCE7F3;color:#9D174D;}
.dtag.SimBASE{background:#FEF3C7;color:#92400E;}

/* Status badge */
.sbadge{display:inline-flex;align-items:center;font-size:11px;font-weight:600;padding:3px 9px;border-radius:20px;white-space:nowrap;flex-shrink:0;}
.sbadge.done{background:var(--green-bg);color:var(--green);}
.sbadge.wip{background:var(--yellow-bg);color:var(--yellow);}
.sbadge.partial{background:#fef9c3;color:#854d0e;}
.sbadge.todo{background:var(--gray-100);color:var(--gray-500);}

/* Progress bar in master */
.mtr-progress{height:4px;background:var(--gray-100);border-radius:2px;margin-top:4px;overflow:hidden;width:80px;}
.mtr-progress-fill{height:100%;background:var(--accent);border-radius:2px;}

/* Subtask rows */
.sub-rows{display:none;background:#fafbfd;}
.sub-rows.open{display:block;}
.sub-row{display:flex;align-items:center;gap:10px;padding:9px 16px 9px 46px;border-bottom:1px solid var(--gray-100);transition:background .1s;}
.sub-row:hover{background:var(--gray-100);}
.sub-row:last-child{border-bottom:none;}
.sub-row .mtr-actions{opacity:0;}
.sub-row:hover .mtr-actions{opacity:1;}
.sub-indent{color:var(--gray-300);font-size:12px;flex-shrink:0;}

/* Activity rows */
.act-rows{display:none;background:#f5f7fa;}
.act-rows.open{display:block;}
.act-row{display:flex;align-items:center;gap:10px;padding:8px 16px 8px 72px;border-bottom:1px solid var(--gray-100);transition:background .1s;}
.act-row:hover{background:#eef0f5;}
.act-row:last-child{border-bottom:none;}
.act-row .mtr-actions{opacity:0;}
.act-row:hover .mtr-actions{opacity:1;}

/* ─── TEAM ─── */
.team-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:14px;}
.member-card{background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:18px;transition:box-shadow .15s;cursor:pointer;}
.member-card:hover{box-shadow:var(--shadow-md);}
.member-card.vacancy{border:2px dashed var(--gray-200);background:var(--gray-50);cursor:default;}
.mc-avatar{width:48px;height:48px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:20px;font-weight:700;color:white;margin-bottom:12px;}
.mc-name{font-weight:700;font-size:15px;}.mc-role{font-size:12px;color:var(--gray-400);margin-top:2px;}
.mc-stats{margin-top:12px;padding-top:12px;border-top:1px solid var(--gray-100);display:flex;gap:12px;}
.mc-stat{text-align:center;flex:1;}
.mc-stat-num{font-size:18px;font-weight:700;color:var(--navy);}
.mc-stat-lbl{font-size:10px;color:var(--gray-400);text-transform:uppercase;letter-spacing:.4px;margin-top:1px;}
.mc-stat.g .mc-stat-num{color:var(--green);}
.mc-actions{margin-top:12px;display:flex;gap:6px;flex-wrap:wrap;}
.vlabel{font-size:11px;font-weight:600;background:var(--yellow-bg);color:var(--yellow);padding:2px 8px;border-radius:10px;display:inline-block;margin-bottom:8px;}

/* ─── HISTORY ─── */
.history-list{display:flex;flex-direction:column;gap:8px;}
.h-item{background:white;border-radius:var(--radius);box-shadow:var(--shadow);overflow:hidden;}
.h-hdr{display:flex;align-items:center;justify-content:space-between;padding:12px 16px;cursor:pointer;transition:background .1s;}
.h-hdr:hover{background:var(--gray-50);}
.h-date{font-weight:600;font-size:13px;}
.h-meta{font-size:11px;color:var(--gray-400);margin-top:2px;}
.h-body{display:none;border-top:1px solid var(--gray-100);}
.h-body.open{display:block;}
.h-task-row{display:flex;align-items:center;gap:10px;padding:8px 16px;border-bottom:1px solid var(--gray-50);font-size:12px;}
.h-task-row:last-child{border-bottom:none;}

/* ─── REPORTS ─── */
.report-cards{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:20px;}
.report-card{background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:22px;}
.rc-icon{width:46px;height:46px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:22px;margin-bottom:12px;}
.rc-title{font-weight:700;font-size:15px;color:var(--navy);margin-bottom:4px;}
.rc-desc{font-size:12px;color:var(--gray-500);line-height:1.6;margin-bottom:16px;}

/* ─── STATS BAR ─── */
.stats-bar{display:flex;gap:10px;margin-bottom:16px;flex-wrap:wrap;}
.stat-card{background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:12px 16px;flex:1;min-width:90px;}
.stat-n{font-size:22px;font-weight:700;color:var(--navy);line-height:1;}
.stat-l{font-size:10px;color:var(--gray-400);margin-top:3px;text-transform:uppercase;letter-spacing:.5px;}
.stat-card.g .stat-n{color:var(--green);}
.stat-card.y .stat-n{color:var(--yellow);}
.stat-card.r .stat-n{color:var(--red);}

/* Progress */
.prog-wrap{margin-bottom:16px;}
.prog-lbl{font-size:12px;color:var(--gray-400);margin-bottom:4px;display:flex;justify-content:space-between;}
.prog-bar{height:6px;background:var(--gray-100);border-radius:3px;overflow:hidden;}
.prog-fill{height:100%;background:var(--accent);border-radius:3px;transition:width .3s;}

/* ─── FILTER BAR ─── */
.filter-row{display:flex;gap:6px;margin-bottom:14px;flex-wrap:wrap;align-items:center;}
.filter-lbl{font-size:12px;color:var(--gray-400);}
.fchip{padding:4px 12px;border-radius:20px;border:1px solid var(--gray-200);background:white;font-size:12px;cursor:pointer;transition:all .15s;}
.fchip:hover{border-color:var(--accent);color:var(--accent);}
.fchip.active{background:var(--accent);color:white;border-color:var(--accent);}

/* ─── MODALS ─── */
.overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.4);z-index:500;align-items:center;justify-content:center;}
.overlay.open{display:flex;}
.overlay.scroll{align-items:flex-start;padding:24px;overflow-y:auto;}
.modal{background:white;border-radius:14px;box-shadow:var(--shadow-lg);padding:24px;width:90%;max-width:520px;max-height:90vh;overflow-y:auto;}
.modal.wide{max-width:720px;}
.modal-title{display:flex;align-items:center;justify-content:space-between;margin-bottom:18px;}
.modal-title span{font-size:16px;font-weight:700;color:var(--navy);}
.modal-close{background:none;border:none;font-size:22px;cursor:pointer;color:var(--gray-400);line-height:1;padding:0;}
.modal-close:hover{color:var(--gray-700);}
.fg{margin-bottom:13px;}
.fl{font-size:12px;font-weight:600;color:var(--gray-500);margin-bottom:5px;display:block;}
.fc{width:100%;border:1px solid var(--gray-200);border-radius:var(--radius-sm);padding:8px 12px;font-size:13px;font-family:inherit;outline:none;transition:border .15s;color:var(--gray-900);}
.fc:focus{border-color:var(--accent);}
.modal-footer{display:flex;gap:8px;justify-content:flex-end;margin-top:18px;}

/* Profile */
.profile-hdr{display:flex;align-items:flex-start;gap:16px;padding:16px;background:var(--gray-50);border-radius:var(--radius);margin-bottom:18px;}
.profile-av{width:54px;height:54px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:22px;font-weight:700;color:white;flex-shrink:0;}
.profile-name{font-size:18px;font-weight:700;color:var(--navy);}
.profile-role{font-size:12px;color:var(--gray-400);margin-top:2px;}
.profile-stats-row{display:flex;gap:8px;margin-top:10px;flex-wrap:wrap;}
.pst{background:white;border-radius:6px;padding:8px 12px;text-align:center;min-width:60px;box-shadow:var(--shadow);}
.pst-n{font-size:17px;font-weight:700;color:var(--navy);}
.pst-l{font-size:10px;color:var(--gray-400);text-transform:uppercase;letter-spacing:.4px;margin-top:1px;}
.pst.g .pst-n{color:var(--green);}.pst.r .pst-n{color:var(--red);}.pst.y .pst-n{color:var(--yellow);}
.profile-prog{height:5px;background:var(--gray-100);border-radius:3px;margin-top:8px;overflow:hidden;width:180px;}
.profile-prog-fill{height:100%;border-radius:3px;}
.psec-title{font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--gray-400);margin-bottom:8px;}
.psec{margin-bottom:16px;}
.pt-row{display:flex;align-items:center;gap:8px;padding:9px 12px;background:white;border-radius:var(--radius-sm);margin-bottom:4px;box-shadow:var(--shadow);}
.pt-name{flex:1;font-size:13px;font-weight:500;}
.pt-sub{font-size:11px;color:var(--gray-400);}
.dh-row{padding:10px 12px;background:white;border-radius:var(--radius-sm);margin-bottom:4px;box-shadow:var(--shadow);}
.dh-date{font-size:12px;font-weight:600;color:var(--navy);margin-bottom:4px;}
.dh-chips{display:flex;flex-wrap:wrap;gap:4px;}
.dchip{font-size:11px;padding:2px 8px;border-radius:10px;font-weight:500;}

/* Builder */
.builder-task{background:var(--gray-50);border-radius:var(--radius-sm);padding:12px;margin-bottom:8px;border:1px solid var(--gray-200);}
.builder-task-hdr{display:flex;align-items:center;gap:8px;margin-bottom:6px;}
.builder-sub{display:flex;align-items:center;gap:8px;padding:5px 0 5px 22px;font-size:12px;color:var(--gray-500);}
.preview-slide{background:white;border:1px solid var(--gray-200);border-radius:var(--radius);padding:18px;margin-bottom:10px;box-shadow:var(--shadow);}
.preview-slide-title{font-size:15px;font-weight:700;color:var(--navy);margin-bottom:3px;}
.preview-meta{font-size:11px;color:var(--gray-400);margin-bottom:10px;}
.preview-bullet{border:none;border-bottom:1px solid var(--gray-100);width:100%;font-size:13px;font-family:inherit;padding:4px 0;color:var(--gray-900);background:transparent;display:block;margin-bottom:4px;}
.preview-bullet:focus{outline:none;border-bottom-color:var(--accent);}
.preview-comment{width:100%;border:1px solid var(--gray-200);border-radius:var(--radius-sm);padding:8px;font-size:12px;font-family:inherit;margin-top:10px;resize:vertical;min-height:56px;color:var(--gray-500);}
.preview-comment:focus{outline:none;border-color:var(--accent);}
.next-steps-preview{background:var(--navy);color:white;border-radius:var(--radius);padding:16px;margin-bottom:10px;}
.next-step-input{background:transparent;border:none;border-bottom:1px solid rgba(255,255,255,.15);color:white;font-size:13px;font-family:inherit;padding:3px 4px;margin-bottom:4px;width:100%;}
.next-step-input:focus{outline:none;border-bottom-color:rgba(255,255,255,.5);}
.generating{text-align:center;padding:40px;color:var(--gray-400);}
.spin{display:inline-block;animation:spin 1s linear infinite;font-size:28px;}
@keyframes spin{from{transform:rotate(0)}to{transform:rotate(360deg)}}

/* Rollover */
.rv-banner{background:linear-gradient(135deg,#fffbeb,#fef2f2);border:1px solid #fcd34d;border-radius:var(--radius);padding:14px 16px;margin-bottom:16px;display:flex;align-items:center;justify-content:space-between;gap:12px;}
.rv-text{font-size:13px;font-weight:500;color:#92400e;}
.rv-text strong{color:var(--red);}
.rv-actions{display:flex;gap:8px;flex-shrink:0;}

/* Empty state */
.empty{text-align:center;padding:48px 24px;color:var(--gray-400);}
.empty-icon{font-size:36px;margin-bottom:10px;}
.empty-text{font-size:13px;}

/* Toast */
.toast{position:fixed;bottom:24px;right:24px;background:var(--gray-900);color:white;padding:12px 18px;border-radius:var(--radius);font-size:13px;font-weight:500;box-shadow:var(--shadow-lg);z-index:999;transform:translateY(60px);opacity:0;transition:all .25s;max-width:320px;}
.toast.show{transform:translateY(0);opacity:1;}

/* Sync dot */
.sync-dot{width:6px;height:6px;border-radius:50%;background:#4ade80;display:inline-block;margin-right:4px;animation:pulse 2s infinite;}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.4}}

@media(max-width:900px){
  .week-grid{grid-template-columns:repeat(3,1fr);}
  .report-cards{grid-template-columns:1fr;}
}
@media(max-width:600px){
  .page{padding:12px;}
  .week-grid{grid-template-columns:1fr 1fr;}
  .team-grid{grid-template-columns:1fr;}
}
</style>
</head>
<body>

<!-- HEADER -->
<div class="hdr">
  <div class="hdr-brand">
    <div class="hdr-dot"></div>
    <div class="hdr-title">Процессный офис</div>
  </div>
  <div class="hdr-right">
    <div class="hdr-date" id="hdrDate"></div>
    <div id="authArea"></div>
  </div>
</div>

<!-- NAV -->
<div class="nav">
  <div class="nav-item active" onclick="switchView('today')">☀ Сегодня <span class="nav-badge" id="nb-today">0</span></div>
  <div class="nav-item" onclick="switchView('week')">📅 Неделя <span class="nav-badge" id="nb-week">0</span></div>
  <div class="nav-item" onclick="switchView('master')">🗂 Мастер <span class="nav-badge" id="nb-master">0</span></div>
  <div class="nav-item" onclick="switchView('team')">👥 Команда <span class="nav-badge" id="nb-team">0</span></div>
  <div class="nav-item" onclick="switchView('history')">📋 История <span class="nav-badge" id="nb-history">0</span></div>
  <div class="nav-item" onclick="switchView('reports')">📊 Отчёты</div>
</div>

<div class="page">

<!-- ═══ TODAY ═══ -->
<div class="view active" id="view-today">
  <div class="toolbar">
    <div class="toolbar-title" id="today-title">Сегодня <span class="toolbar-sub"></span></div>
    <div style="display:flex;gap:8px;align-items:center">
      <button class="nav-arrow" onclick="changeDay(-1)">&#8249;</button>
      <div id="today-lbl" style="font-size:13px;font-weight:600;color:var(--navy);background:var(--gray-100);padding:6px 14px;border-radius:var(--radius-sm);min-width:140px;text-align:center"></div>
      <button class="nav-arrow" onclick="changeDay(1)">&#8250;</button>
    </div>
    <button class="btn btn-primary eo" onclick="openAddModal('day')">+ Активность</button>
    <button class="btn btn-outline eo" onclick="openFromWeek()">← Из задач</button>
  </div>
  <div id="rv-banner"></div>
  <div class="stats-bar" id="today-stats"></div>
  <div class="prog-wrap" id="today-prog"></div>
  <div id="today-content"></div>
</div>

<!-- ═══ WEEK ═══ -->
<div class="view" id="view-week">
  <div class="toolbar">
    <div class="toolbar-title">Неделя <span class="toolbar-sub" id="week-range"></span></div>
    <div style="display:flex;gap:8px;align-items:center">
      <button class="nav-arrow" onclick="changeWeek(-1)">&#8249;</button>
      <div id="week-lbl" style="font-size:13px;font-weight:600;color:var(--navy);background:var(--gray-100);padding:6px 14px;border-radius:var(--radius-sm);min-width:120px;text-align:center"></div>
      <button class="nav-arrow" onclick="changeWeek(1)">&#8250;</button>
    </div>
    <button class="btn btn-primary eo" onclick="openAddModal('week')">+ Подзадача</button>
  </div>
  <div class="stats-bar" id="week-stats"></div>
  <div class="prog-wrap" id="week-prog"></div>
  <div class="week-grid" id="week-grid"></div>
</div>

<!-- ═══ MASTER ═══ -->
<div class="view" id="view-master">
  <div class="toolbar">
    <div class="toolbar-title">Мастер трекер <span class="toolbar-sub"><span class="sync-dot"></span>онлайн</span></div>
    <button class="btn btn-primary eo" onclick="openAddModal('master')">+ Основная задача</button>
  </div>
  <div class="filter-row" id="master-filters"></div>
  <div class="master-tree" id="master-tree"></div>
</div>

<!-- ═══ TEAM ═══ -->
<div class="view" id="view-team">
  <div class="toolbar">
    <div class="toolbar-title">Команда</div>
    <button class="btn btn-primary eo" onclick="openTeamModal()">+ Добавить</button>
  </div>
  <div class="team-grid" id="team-grid"></div>
</div>

<!-- ═══ HISTORY ═══ -->
<div class="view" id="view-history">
  <div class="toolbar"><div class="toolbar-title">История стендапов</div></div>
  <div id="history-list"></div>
</div>

<!-- ═══ REPORTS ═══ -->
<div class="view" id="view-reports">
  <div class="toolbar"><div class="toolbar-title">Отчёты</div></div>
  <div class="report-cards">
    <div class="report-card">
      <div class="rc-icon" style="background:var(--navy)">📊</div>
      <div class="rc-title">2-недельный статус</div>
      <div class="rc-desc">Презентация PowerPoint для куратора/CEO. AI генерирует текст из твоих задач.</div>
      <div style="margin-bottom:12px">
        <label class="fl">Период</label>
        <div style="display:flex;gap:8px;align-items:center">
          <input type="date" id="rpt-from" class="fc" style="flex:1"/>
          <span style="color:var(--gray-400)">—</span>
          <input type="date" id="rpt-to" class="fc" style="flex:1"/>
        </div>
      </div>
      <button class="btn btn-primary" style="width:100%" onclick="openBuilder()">Открыть конструктор →</button>
    </div>
    <div class="report-card">
      <div class="rc-icon" style="background:var(--green)">📝</div>
      <div class="rc-title">Еженедельный отчёт</div>
      <div class="rc-desc">Текст "Что сделано за неделю" по направлениям. Готово к копированию.</div>
      <div style="margin-bottom:12px">
        <label class="fl">Неделя</label>
        <div style="display:flex;gap:8px;align-items:center">
          <button class="nav-arrow" onclick="changeRptWeek(-1)">&#8249;</button>
          <div id="rpt-week-lbl" style="flex:1;text-align:center;font-size:13px;font-weight:600;color:var(--navy)"></div>
          <button class="nav-arrow" onclick="changeRptWeek(1)">&#8250;</button>
        </div>
      </div>
      <button class="btn btn-primary" style="width:100%;background:var(--green)" onclick="generateWeeklyText()">Сформировать отчёт →</button>
    </div>
  </div>
  <div id="weekly-text-output" style="display:none;background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:20px;"></div>
</div>

</div><!-- /page -->

<!-- MODAL: TASK -->
<div class="overlay" id="mTask">
  <div class="modal">
    <div class="modal-title"><span id="mTaskTitle">Добавить задачу</span><button class="modal-close" onclick="closeM('mTask')">&#215;</button></div>
    <div class="fg"><label class="fl">Направление</label>
      <select class="fc" id="f-dir"><option>Проекты</option><option>IT|AI</option><option>Методология</option><option>SimBASE</option></select></div>
    <div class="fg"><label class="fl">Название</label><input class="fc" id="f-name" placeholder="Название задачи"/></div>
    <div class="fg"><label class="fl">Детали / что конкретно</label><input class="fc" id="f-detail" placeholder="Уточнение..."/></div>
    <div class="fg" id="f-parent-grp"><label class="fl">🔗 Привязать к <span id="f-parent-lbl"></span></label>
      <select class="fc" id="f-parent"><option value="">— без привязки —</option></select></div>
    <div class="fg"><label class="fl">Ответственный</label>
      <select class="fc" id="f-owner"><option value="">— выбрать —</option></select></div>
    <div class="fg"><label class="fl">Скорость (1=быстро, 5=долго)</label>
      <select class="fc" id="f-speed"><option value="1">1 — быстрее часа</option><option value="2">2 — полдня</option><option value="3" selected>3 — день</option><option value="4">4 — несколько дней</option><option value="5">5 — неделя+</option></select></div>
    <div class="fg" id="f-deadline-grp"><label class="fl">Дедлайн</label><input class="fc" id="f-deadline" type="date"/></div>
    <div class="fg"><label class="fl">Комментарий</label><input class="fc" id="f-comment" placeholder="Результат, уточнение..."/></div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeM('mTask')">Отмена</button>
      <button class="btn btn-primary" onclick="saveTask()">Сохранить</button>
    </div>
  </div>
</div>

<!-- MODAL: SUBTASK -->
<div class="overlay" id="mSubtask">
  <div class="modal">
    <div class="modal-title"><span id="mSubtaskTitle">+ Подзадача</span><button class="modal-close" onclick="closeM('mSubtask')">&#215;</button></div>
    <div style="background:var(--accent-light);border-radius:var(--radius-sm);padding:10px 12px;margin-bottom:16px;font-size:12px;color:var(--accent)">
      К задаче: <strong id="stParentName"></strong>
    </div>
    <div class="fg"><label class="fl">Название подзадачи</label><input class="fc" id="st-name" placeholder="Что нужно сделать"/></div>
    <div class="fg"><label class="fl">Детали</label><input class="fc" id="st-detail" placeholder="Уточнение..."/></div>
    <div class="fg"><label class="fl">Ответственный</label><select class="fc" id="st-owner"><option value="">— выбрать —</option></select></div>
    <div class="fg"><label class="fl">Скорость</label>
      <select class="fc" id="st-speed"><option value="1">1 — быстрее часа</option><option value="2">2 — полдня</option><option value="3" selected>3 — день</option><option value="4">4 — несколько дней</option><option value="5">5 — неделя+</option></select></div>
    <div class="fg"><label class="fl">Добавить сразу в</label>
      <select class="fc" id="st-target"><option value="master">Только в Мастер</option><option value="week">Мастер + Неделя</option><option value="day">Мастер + Неделя + День</option></select></div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeM('mSubtask')">Отмена</button>
      <button class="btn btn-primary" onclick="saveSubtask()">Создать</button>
    </div>
  </div>
</div>

<!-- MODAL: FROM WEEK -->
<div class="overlay" id="mFromWeek">
  <div class="modal">
    <div class="modal-title"><span>← Добавить из задач</span><button class="modal-close" onclick="closeM('mFromWeek')">&#215;</button></div>
    <div id="from-week-list"></div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeM('mFromWeek')">Отмена</button>
      <button class="btn btn-primary" onclick="confirmFromWeek()">Добавить выбранные</button>
    </div>
  </div>
</div>

<!-- MODAL: TEAM -->
<div class="overlay" id="mTeam">
  <div class="modal">
    <div class="modal-title"><span id="mTeamTitle">Добавить</span><button class="modal-close" onclick="closeM('mTeam')">&#215;</button></div>
    <div class="fg"><label class="fl">Тип</label>
      <select class="fc" id="tm-type" onchange="toggleVac()"><option value="active">Сотрудник</option><option value="vacancy">Вакансия</option></select></div>
    <div id="tm-name-grp" class="fg"><label class="fl">Имя</label><input class="fc" id="tm-name" placeholder="Имя"/></div>
    <div class="fg"><label class="fl">Должность</label><input class="fc" id="tm-role" placeholder="Специалист"/></div>
    <div class="fg"><label class="fl">Цвет</label>
      <select class="fc" id="tm-color"><option value="#2E7CF6">Синий</option><option value="#16A34A">Зелёный</option><option value="#7C3AED">Фиолетовый</option><option value="#D97706">Жёлтый</option><option value="#DC2626">Красный</option><option value="#0D2B4E">Тёмно-синий</option></select></div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeM('mTeam')">Отмена</button>
      <button class="btn btn-primary" onclick="saveMember()">Сохранить</button>
    </div>
  </div>
</div>

<!-- MODAL: PROFILE -->
<div class="overlay scroll" id="mProfile">
  <div class="modal wide">
    <div class="modal-title"><span id="mProfileTitle">Профиль</span><button class="modal-close" onclick="closeM('mProfile')">&#215;</button></div>
    <div id="profile-content"></div>
  </div>
</div>

<!-- MODAL: REPORT BUILDER -->
<div class="overlay scroll" id="mBuilder">
  <div class="modal wide">
    <div class="modal-title"><span id="mBuilderTitle">Конструктор отчёта</span><button class="modal-close" onclick="closeM('mBuilder')">&#215;</button></div>
    <div id="builder-step1">
      <div style="font-size:13px;color:var(--gray-500);margin-bottom:14px">Выбери задачи для презентации. AI сформирует текст на основе подзадач.</div>
      <div id="builder-list"></div>
      <div class="modal-footer">
        <button class="btn btn-ghost" onclick="closeM('mBuilder')">Отмена</button>
        <button class="btn btn-primary" onclick="generateReport()">✨ Сгенерировать</button>
      </div>
    </div>
    <div id="builder-step2" style="display:none">
      <div style="background:var(--accent-light);border-radius:var(--radius-sm);padding:12px;margin-bottom:16px;font-size:13px;color:var(--accent);display:flex;gap:8px;align-items:center">
        <span>✨</span><span>AI сгенерировал текст. Отредактируй если нужно, потом скачай.</span>
      </div>
      <div id="builder-preview"></div>
      <div class="modal-footer">
        <button class="btn btn-ghost" onclick="backToStep1()">← Назад</button>
        <button class="btn btn-primary" id="dl-btn" onclick="downloadPPTX()">⬇ Скачать PPTX</button>
      </div>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script type="module">
import{initializeApp}from'https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js';
import{getFirestore,collection,doc,setDoc,updateDoc,deleteDoc,onSnapshot}from'https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js';
import{getAuth,signInWithPopup,GoogleAuthProvider,signOut,onAuthStateChanged}from'https://www.gstatic.com/firebasejs/10.12.0/firebase-auth.js';

const FB={apiKey:"AIzaSyBoMbn728PYIu19XRW4vznlhMHD0af0qEg",authDomain:"sergek-tracker.firebaseapp.com",projectId:"sergek-tracker",storageBucket:"sergek-tracker.firebasestorage.app",messagingSenderId:"133904852598",appId:"1:133904852598:web:5a1a8b1d7d091d8bdda157"};
const ADMIN="b.moldatayev@sergek.com";
const app=initializeApp(FB);
const db=getFirestore(app);
const auth=getAuth(app);

// STATE
let isAdmin=false,dayOff=0,weekOff=0,rptWeekOff=0;
let mCtx='master',stParentId='',editTeamId=null;
let masterFilter='all';
let expandedIds=new Set();
let C={master:[],week:[],day:{},team:[]};
let generatedData=null,builderSels={};

// FIREBASE HELPERS
async function fsSet(col,id,data){await setDoc(doc(db,col,id),data);}
async function fsUpd(col,id,data){try{await updateDoc(doc(db,col,id),data);}catch(e){await setDoc(doc(db,col,id),data);}}
async function fsDel(col,id){await deleteDoc(doc(db,col,id));}

// AUTH
window.loginGoogle=async()=>{try{await signInWithPopup(auth,new GoogleAuthProvider());}catch(e){toast('Ошибка входа');}};
window.logoutUser=async()=>{await signOut(auth);};

onAuthStateChanged(auth,u=>{
  if(u&&u.email===ADMIN){
    isAdmin=true;
    document.getElementById('authArea').innerHTML=`<div class="user-chip"><img class="user-av" src="${u.photoURL||''}" onerror="this.style.display='none'"><span>${u.displayName||u.email}</span><button class="logout-btn" onclick="logoutUser()">Выйти</button></div>`;
  }else if(u){
    isAdmin=false;
    document.getElementById('authArea').innerHTML=`<div class="user-chip"><span class="ro-pill">Только просмотр</span><button class="logout-btn" onclick="logoutUser()">Выйти</button></div>`;
  }else{
    isAdmin=false;
    document.getElementById('authArea').innerHTML=`<button class="auth-btn" onclick="loginGoogle()">Войти через Google</button>`;
  }
  document.querySelectorAll('.eo').forEach(e=>e.style.display=isAdmin?'':'none');
  renderAll();
});

// LISTENERS
function startListeners(){
  onSnapshot(collection(db,'master'),s=>{C.master=s.docs.map(d=>({id:d.id,...d.data()}));renderMaster();renderTeam();renderToday();});
  onSnapshot(collection(db,'week'),s=>{C.week=s.docs.map(d=>({id:d.id,...d.data()}));renderWeek();renderToday();});
  onSnapshot(collection(db,'day'),s=>{
    C.day={};s.docs.forEach(d=>{const dt=d.data();if(!C.day[dt.dayKey])C.day[dt.dayKey]=[];C.day[dt.dayKey].push({id:d.id,...dt});});
    renderToday();renderHistory();updateBadges();
  });
  onSnapshot(collection(db,'team'),s=>{C.team=s.docs.map(d=>({id:d.id,...d.data()}));renderTeam();renderToday();document.getElementById('nb-team').textContent=C.team.length;});
}

// DATE HELPERS
function toKey(d){return d.toISOString().slice(0,10);}
function todayK(){return toKey(new Date());}
function curDayK(){const d=new Date();d.setDate(d.getDate()+dayOff);return toKey(d);}
function wkKey(off){const d=new Date();const dy=d.getDay()||7;d.setDate(d.getDate()-dy+1+off*7);return toKey(d);}
function wkRange(off){const d=new Date();const dy=d.getDay()||7;const m=new Date(d);m.setDate(d.getDate()-dy+1+off*7);const f=new Date(m);f.setDate(m.getDate()+4);const fmt=x=>x.toLocaleDateString('ru-RU',{day:'numeric',month:'short'});return fmt(m)+' – '+fmt(f);}
function fmtDay(k){return new Date(k+'T12:00:00').toLocaleDateString('ru-RU',{weekday:'long',day:'numeric',month:'long'});}
function fmtDayShort(k){return new Date(k+'T12:00:00').toLocaleDateString('ru-RU',{weekday:'short',day:'numeric',month:'long'});}
function dlCls(s){if(!s)return'';const t=new Date();t.setHours(0,0,0,0);const dl=new Date(s+'T00:00:00');const diff=Math.ceil((dl-t)/86400000);return diff<0?'overdue':diff<=2?'soon':'';}
function genId(){return Date.now().toString(36)+Math.random().toString(36).slice(2,5);}

// STATUS HELPERS
function statusClass(s){return{Выполнено:'done','В работе':'wip',Частично:'partial','Не начато':'todo'}[s]||'todo';}
function sbg(s){return{'Выполнено':'var(--green-bg)','В работе':'var(--yellow-bg)','Частично':'#fef9c3','Не начато':'var(--gray-100)'}[s]||'var(--gray-100)';}
function sfc(s){return{'Выполнено':'var(--green)','В работе':'var(--yellow)','Частично':'#854d0e','Не начато':'var(--gray-500)'}[s]||'var(--gray-500)';}
function statusSel(id,cur,ctx){
  const dis=isAdmin?'':'disabled';
  const cls=statusClass(cur);
  let h=`<select class="ssel ${cls}" ${dis} onchange="updateStatus('${ctx}','${id}',this.value)">`;
  ['Не начато','В работе','Частично','Выполнено'].forEach(o=>h+=`<option${o===cur?' selected':''}>${o}</option>`);
  return h+'</select>';
}
function ownerChips(owner){
  if(!owner)return'';
  return owner.split('/').map(n=>n.trim()).filter(Boolean)
    .map(n=>`<span style="background:var(--gray-100);color:var(--gray-500);font-size:11px;padding:2px 8px;border-radius:10px;cursor:pointer;margin-right:2px" onclick="showProfile('${n}')">${n}</span>`).join('');
}
function dirTag(dir){const c=dir==='IT|AI'?'ITAI':dir;return`<span class="dtag ${c}">${dir}</span>`;}
function owners(){return C.team.filter(m=>m.type==='active').map(m=>m.name);}

// BADGES
function updateBadges(){
  const key=curDayK();
  document.getElementById('nb-today').textContent=(C.day[key]||[]).length;
  const wk=wkKey(weekOff);
  document.getElementById('nb-week').textContent=C.week.filter(t=>t.weekKey===wk).length;
  document.getElementById('nb-master').textContent=C.master.filter(t=>!t.parentId||!C.master.find(m=>m.id===t.parentId)).length;
  document.getElementById('nb-history').textContent=Object.keys(C.day).length;
}

// STATS
function renderStats(tasks,sid,pid){
  const total=tasks.length,done=tasks.filter(t=>t.status==='Выполнено').length;
  const wip=tasks.filter(t=>t.status==='В работе'||t.status==='Частично').length;
  const todo=tasks.filter(t=>t.status==='Не начато').length;
  const trs=tasks.filter(t=>(t.transfers||0)>0).length;
  const pct=total?Math.round(done/total*100):0;
  const el=document.getElementById(sid);if(!el)return;
  el.innerHTML=`<div class="stat-card"><div class="stat-n">${total}</div><div class="stat-l">Всего</div></div><div class="stat-card g"><div class="stat-n">${done}</div><div class="stat-l">Выполнено</div></div><div class="stat-card y"><div class="stat-n">${wip}</div><div class="stat-l">В работе</div></div><div class="stat-card"><div class="stat-n">${todo}</div><div class="stat-l">Не начато</div></div>${trs?`<div class="stat-card r"><div class="stat-n">${trs}</div><div class="stat-l">Переносов</div></div>`:''}`;
  const pe=document.getElementById(pid);if(!pe)return;
  pe.innerHTML=`<div class="prog-lbl"><span>Прогресс дня</span><span>${pct}%</span></div><div class="prog-bar"><div class="prog-fill" style="width:${pct}%"></div></div>`;
}

// ═══ TODAY ═══
function renderToday(){
  const key=curDayK();
  const tasks=C.day[key]||[];
  const isToday=dayOff===0;
  document.getElementById('today-lbl').textContent=fmtDayShort(key);
  document.getElementById('today-title').innerHTML=isToday?'<span style="color:var(--accent)">☀</span> Сегодня <span class="toolbar-sub">— ежедневный стендап</span>':'<span>📋</span> '+fmtDayShort(key);
  document.getElementById('nb-today').textContent=tasks.length;
  renderStats(tasks,'today-stats','today-prog');
  if(isAdmin&&isToday)checkRollover();else document.getElementById('rv-banner').innerHTML='';

  const content=document.getElementById('today-content');
  if(!tasks.length){
    content.innerHTML=`<div class="empty"><div class="empty-icon">☀</div><div class="empty-text">${isAdmin?'Нажми «← Из задач» чтобы добавить активности на сегодня':'Задачи на этот день не добавлены'}</div></div>`;
    return;
  }

  // Group by owner
  const byOwner={};
  tasks.forEach(t=>{
    const owners2=t.owner?t.owner.split('/').map(n=>n.trim()).filter(Boolean):['—'];
    owners2.forEach(o=>{if(!byOwner[o])byOwner[o]=[];byOwner[o].push(t);});
  });

  let html='';
  // Sort: team members first, then unknown
  const teamNames=C.team.filter(m=>m.type==='active').map(m=>m.name);
  const sortedOwners=[...teamNames.filter(n=>byOwner[n]),...Object.keys(byOwner).filter(n=>!teamNames.includes(n))];

  sortedOwners.forEach(ownerName=>{
    const ownerTasks=byOwner[ownerName]||[];
    const member=C.team.find(m=>m.name===ownerName);
    const color=member?member.color:'#94A3B8';
    const done=ownerTasks.filter(t=>t.status==='Выполнено').length;
    const total=ownerTasks.length;

    html+=`<div class="person-section">
      <div class="person-header">
        <div class="person-av" style="background:${color}">${ownerName.slice(0,1)}</div>
        <div>
          <div class="person-name" onclick="showProfile('${ownerName}')">${ownerName}</div>
          <div class="person-role">${member?member.role:''}</div>
        </div>
        <div class="person-stats">
          <div class="pstat g"><div class="pstat-num">${done}</div><div class="pstat-lbl">Выполнено</div></div>
          <div class="pstat-div"></div>
          <div class="pstat"><div class="pstat-num">${total}</div><div class="pstat-lbl">Всего</div></div>
        </div>
      </div>
      <div class="person-tasks">`;

    ownerTasks.forEach(t=>{
      const tr=t.transfers||0;
      const parentWeek=t.parentId?C.week.find(w=>w.id===t.parentId):null;
      const parentMaster=parentWeek&&parentWeek.parentId?C.master.find(m=>m.id===parentWeek.parentId):null;
      const parentLabel=parentMaster?`<div class="task-parent">↑ ${parentMaster.main}${parentWeek?' › '+parentWeek.main:''}</div>`:'';
      html+=`<div class="task-row${t.status==='Выполнено'?' done':''}">
        <div>
          <div class="task-name">${t.name||t.main}</div>
          ${t.detail?`<div class="task-detail">${t.detail}</div>`:''}
          ${parentLabel}
        </div>
        ${tr>0?`<span class="tr-badge">↩${tr}</span>`:''}
        ${statusSel(t.id,t.status,'day')}
        <div class="task-actions">
          ${isAdmin?`<button class="btn btn-warn btn-xs" onclick="rollOne('${t.id}')" title="На завтра">→</button><button class="btn btn-danger btn-xs" onclick="delTask('day','${t.id}')">✕</button>`:''}
        </div>
      </div>`;
    });
    html+='</div></div>';
  });
  content.innerHTML=html;
  updateBadges();
}

// ROLLOVER
function checkRollover(){
  const today=todayK();const d=new Date();d.setDate(d.getDate()-1);const yest=toKey(d);
  const yTasks=C.day[yest]||[];const tTasks=C.day[today]||[];
  const pending=yTasks.filter(t=>t.status!=='Выполнено'&&!tTasks.some(x=>(x.name||x.main)===(t.name||t.main)&&x.dir===t.dir));
  const banner=document.getElementById('rv-banner');
  if(!pending.length){banner.innerHTML='';return;}
  banner.innerHTML=`<div class="rv-banner"><div class="rv-text">Вчера осталось невыполненных: <strong>${pending.length}</strong>. Перенести на сегодня?</div><div class="rv-actions"><button class="btn btn-warn btn-sm" onclick="doRollover()">Перенести все</button><button class="btn btn-ghost btn-sm" onclick="document.getElementById('rv-banner').innerHTML=''">Пропустить</button></div></div>`;
}
window.doRollover=async()=>{
  const today=todayK();const d=new Date();d.setDate(d.getDate()-1);const yest=toKey(d);
  const pending=(C.day[yest]||[]).filter(t=>t.status!=='Выполнено');
  const tTasks=C.day[today]||[];let cnt=0;
  for(const t of pending){
    if(!tTasks.some(x=>(x.name||x.main)===(t.name||t.main)&&x.dir===t.dir)){
      const id=genId();
      await fsSet('day',id,{...t,id,dayKey:today,status:'Не начато',transfers:(t.transfers||0)+1});cnt++;
    }
  }
  document.getElementById('rv-banner').innerHTML='';toast(`↩ Перенесено ${cnt} задач`);
};
window.rollOne=async(id)=>{
  const key=curDayK();const t=(C.day[key]||[]).find(x=>x.id===id);if(!t)return;
  const d=new Date(key+'T12:00:00');d.setDate(d.getDate()+1);const nk=toKey(d);
  if((C.day[nk]||[]).some(x=>(x.name||x.main)===(t.name||t.main))){toast('Уже есть на завтра');return;}
  const nid=genId();
  await fsSet('day',nid,{...t,id:nid,dayKey:nk,status:'Не начато',transfers:(t.transfers||0)+1});
  toast('→ Задача перенесена на завтра');
};

// ═══ WEEK ═══
function renderWeek(){
  const wk=wkKey(weekOff);
  document.getElementById('week-lbl').textContent=weekOff===0?'Текущая':weekOff>0?`+${weekOff} нед.`:`${weekOff} нед.`;
  document.getElementById('week-range').textContent='— '+wkRange(weekOff);
  const allWk=C.week.filter(t=>t.weekKey===wk);
  document.getElementById('nb-week').textContent=allWk.length;
  renderStats(allWk,'week-stats','week-prog');

  const grid=document.getElementById('week-grid');
  const today=todayK();
  const d=new Date();const dy=d.getDay()||7;
  const mon=new Date(d);mon.setDate(d.getDate()-dy+1+weekOff*7);
  const days=['Пн','Вт','Ср','Чт','Пт'];
  let html='';
  days.forEach((dayName,i)=>{
    const dd=new Date(mon);dd.setDate(mon.getDate()+i);
    const key=toKey(dd);
    const dayTasks=C.day[key]||[];
    const isT=key===today;
    html+=`<div class="week-day-col${isT?' today-col':''}">
      <div class="week-day-hdr">
        <div><div class="week-day-name">${dayName}</div><div class="week-day-num${isT?' style="color:var(--accent)"':''}">${dd.getDate()}</div></div>
        ${dayTasks.length?`<span class="week-day-count">${dayTasks.length}</span>`:''}
      </div>
      <div class="week-day-tasks">`;
    if(!dayTasks.length){html+=`<div class="week-empty">—</div>`;}
    else{
      dayTasks.slice(0,5).forEach(t=>{
        const tr=t.transfers||0;
        html+=`<div class="week-task-chip" style="background:${sbg(t.status)};color:${sfc(t.status)}" onclick="dayOff=${Math.round((dd-new Date())/86400000)};switchView('today')">
          ${tr>0?`<span class="chip-tr">↩${tr}</span>`:''}
          <span class="chip-name">${t.name||t.main}</span>
        </div>`;
      });
      if(dayTasks.length>5)html+=`<div style="font-size:11px;color:var(--gray-400);padding:4px">+${dayTasks.length-5} ещё</div>`;
    }
    html+=`</div>
      ${isAdmin?`<button class="week-add-btn" onclick="dayOff=${Math.round((dd-new Date())/86400000)};openAddModal('day')">+ добавить</button>`:''}
    </div>`;
  });
  grid.innerHTML=html;
}

// ═══ MASTER ═══
function renderMaster(){
  // Filter bar
  const fb=document.getElementById('master-filters');
  let fh='<span class="filter-lbl">Фильтр:</span>';
  ['all',...owners()].forEach(o=>{const lbl=o==='all'?'Все':o;fh+=`<span class="fchip${masterFilter===o?' active':''}" onclick="masterFilter='${o}';renderMaster()">${lbl}</span>`;});
  fb.innerHTML=fh;

  // Top-level tasks (no parent or parent not in master)
  let topTasks=C.master.filter(t=>!t.parentId||!C.master.find(m=>m.id===t.parentId));
  if(masterFilter!=='all')topTasks=topTasks.filter(t=>t.owner===masterFilter||t.owner.includes(masterFilter));
  document.getElementById('nb-master').textContent=topTasks.length;

  if(!topTasks.length){
    document.getElementById('master-tree').innerHTML='<div class="empty"><div class="empty-icon">🗂</div><div class="empty-text">Бэклог пуст. Добавь первую задачу.</div></div>';return;
  }

  const groups={};
  topTasks.forEach(t=>{if(!groups[t.dir])groups[t.dir]=[];groups[t.dir].push(t);});
  let html='';
  Object.entries(groups).forEach(([dir,items])=>{
    html+=`<div class="master-dir-hdr">${dirTag(dir)} ${dir} <span style="margin-left:4px;font-weight:400;color:var(--gray-400)">(${items.length})</span></div>`;
    items.forEach(t=>{
      const subs=C.master.filter(x=>x.parentId===t.id);
      const isExp=expandedIds.has(t.id);
      const doneSubs=subs.filter(s=>s.status==='Выполнено').length;
      const pct=subs.length?Math.round(doneSubs/subs.length*100):0;

      html+=`<div class="master-task-row">
        <div class="mtr-main" onclick="toggleExpand('${t.id}')">
          <button class="mtr-expand" onclick="event.stopPropagation();toggleExpand('${t.id}')">${subs.length?isExp?'▾':'▸':'·'}</button>
          <div style="flex:1;min-width:0">
            <div class="mtr-name">${t.name||t.main}</div>
            ${t.detail?`<div class="mtr-detail">${t.detail}</div>`:''}
            ${subs.length?`<div class="mtr-progress"><div class="mtr-progress-fill" style="width:${pct}%"></div></div>`:''}
          </div>
          ${ownerChips(t.owner)}
          <span class="sbadge ${statusClass(t.status)}">${t.status}</span>
          <div class="mtr-actions">
            ${isAdmin?`<button class="btn btn-green btn-xs" onclick="event.stopPropagation();openSubtask('${t.id}')" title="+ Подзадача">＋</button>
            <button class="btn btn-ghost btn-xs" onclick="event.stopPropagation();pushToWeek('${t.id}')" title="В неделю">📅</button>
            ${statusSel(t.id,t.status,'master')}
            <button class="btn btn-danger btn-xs" onclick="event.stopPropagation();delTask('master','${t.id}')">✕</button>`
            :statusSel(t.id,t.status,'master')}
          </div>
        </div>`;

      // Subtasks
      if(isExp&&subs.length){
        html+=`<div class="sub-rows open">`;
        subs.forEach(st=>{
          const acts=C.day[curDayK()]?C.day[curDayK()].filter(a=>a.parentId===st.id):[];
          const isExpSt=expandedIds.has(st.id);
          html+=`<div>
            <div class="sub-row" onclick="toggleExpand('${st.id}')">
              <span class="sub-indent">└─</span>
              <button class="mtr-expand" onclick="event.stopPropagation();toggleExpand('${st.id}')">${acts.length?isExpSt?'▾':'▸':'·'}</button>
              <div style="flex:1;min-width:0">
                <div style="font-weight:500;font-size:13px">${st.name||st.main}</div>
                ${st.detail?`<div class="mtr-detail">${st.detail}</div>`:''}
              </div>
              ${ownerChips(st.owner)}
              <span class="sbadge ${statusClass(st.status)}">${st.status}</span>
              <div class="mtr-actions">
                ${isAdmin?`${statusSel(st.id,st.status,'master')}<button class="btn btn-ghost btn-xs" onclick="event.stopPropagation();pushToDay('${st.id}')" title="В день">☀</button><button class="btn btn-danger btn-xs" onclick="event.stopPropagation();delTask('master','${st.id}')">✕</button>`:statusSel(st.id,st.status,'master')}
              </div>
            </div>`;
          // Activities
          if(isExpSt&&acts.length){
            html+=`<div class="act-rows open">`;
            acts.forEach(a=>{
              html+=`<div class="act-row">
                <span style="color:var(--gray-300);font-size:12px">└─</span>
                <div style="flex:1;min-width:0"><div style="font-size:12px;font-weight:500">${a.name||a.main}</div>${a.detail?`<div class="mtr-detail">${a.detail}</div>`:''}</div>
                <span class="sbadge ${statusClass(a.status)}" style="font-size:10px">${a.status}</span>
                <div class="mtr-actions">${isAdmin?`<button class="btn btn-danger btn-xs" onclick="delTask('day','${a.id}')">✕</button>`:''}</div>
              </div>`;
            });
            html+='</div>';
          }
          html+='</div>';
        });
        html+='</div>';
      }
      html+='</div>';
    });
  });
  document.getElementById('master-tree').innerHTML=html;
}

window.toggleExpand=id=>{if(expandedIds.has(id))expandedIds.delete(id);else expandedIds.add(id);renderMaster();};

// ═══ TEAM ═══
function renderTeam(){
  const g=document.getElementById('team-grid');
  if(!C.team.length){g.innerHTML='<div class="empty"><div class="empty-icon">👥</div><div>Добавь сотрудников</div></div>';return;}
  let html='';
  C.team.forEach(m=>{
    const dTasks=(C.day[todayK()]||[]).filter(t=>t.owner===m.name||t.owner.includes(m.name));
    const done=dTasks.filter(t=>t.status==='Выполнено').length;
    const allT=C.master.filter(t=>t.owner===m.name||t.owner.includes(m.name));
    if(m.type==='vacancy'){
      html+=`<div class="member-card vacancy"><span class="vlabel">🔍 Вакансия</span><div class="mc-name" style="color:var(--gray-400)">${m.role}</div><div class="mc-stats" style="justify-content:center;color:var(--gray-400);font-size:13px">Позиция открыта</div>${isAdmin?`<div class="mc-actions"><button class="btn btn-ghost btn-sm" onclick="editMember('${m.id}')">✏</button><button class="btn btn-danger btn-sm" onclick="delMember('${m.id}')">✕</button></div>`:''}</div>`;
    }else{
      html+=`<div class="member-card" onclick="showProfile('${m.name}')">
        <div class="mc-avatar" style="background:${m.color}">${m.name.slice(0,1)}</div>
        <div class="mc-name">${m.name}</div>
        <div class="mc-role">${m.role}</div>
        <div class="mc-stats">
          <div class="mc-stat"><div class="mc-stat-num">${allT.length}</div><div class="mc-stat-lbl">В мастере</div></div>
          <div class="mc-stat g"><div class="mc-stat-num">${done}</div><div class="mc-stat-lbl">Сегодня ✓</div></div>
          <div class="mc-stat"><div class="mc-stat-num">${dTasks.length}</div><div class="mc-stat-lbl">Сегодня</div></div>
        </div>
        <div class="mc-actions" onclick="event.stopPropagation()">
          ${isAdmin?`<button class="btn btn-ghost btn-sm" onclick="editMember('${m.id}')">✏</button><button class="btn btn-danger btn-sm" onclick="delMember('${m.id}')">✕</button>`:''}
        </div>
      </div>`;
    }
  });
  g.innerHTML=html;
}

// ═══ HISTORY ═══
function renderHistory(){
  const keys=Object.keys(C.day).sort().reverse();
  document.getElementById('nb-history').textContent=keys.length;
  const c=document.getElementById('history-list');
  if(!keys.length){c.innerHTML='<div class="empty"><div class="empty-icon">📋</div><div>История пуста</div></div>';return;}
  let html='<div class="history-list">';
  keys.forEach(key=>{
    const tasks=C.day[key]||[];
    const done=tasks.filter(t=>t.status==='Выполнено').length;
    const total=tasks.length;const pct=total?Math.round(done/total*100):0;
    const trs=tasks.filter(t=>(t.transfers||0)>0).length;
    let rows='';
    tasks.forEach(t=>{const tr=t.transfers||0;rows+=`<div class="h-task-row"><span style="flex:1;font-weight:500">${t.name||t.main}</span>${ownerChips(t.owner)}<span style="font-size:11px;font-weight:600;padding:2px 8px;border-radius:10px;background:${sbg(t.status)};color:${sfc(t.status)}">${t.status}</span>${tr>0?`<span class="tr-badge">↩${tr}</span>`:''}</div>`;});
    html+=`<div class="h-item"><div class="h-hdr" onclick="toggleH('hb-${key}')"><div><div class="h-date">${fmtDay(key)}</div><div class="h-meta">${total} задач · ${done} выполнено · ${pct}%${trs?' · ↩ '+trs:''}</div></div><span style="color:var(--gray-400);font-size:18px">›</span></div><div class="h-body" id="hb-${key}">${rows}</div></div>`;
  });
  html+='</div>';c.innerHTML=html;
}
window.toggleH=id=>document.getElementById(id).classList.toggle('open');

// ═══ PROFILE ═══
window.showProfile=name=>{
  const m=C.team.find(x=>x.name===name||name.includes(x.name));
  if(!m)return;
  const isM=t=>t.owner===m.name||t.owner.includes(m.name);
  const masterT=C.master.filter(isM);
  const wk=wkKey(weekOff);
  const weekT=C.week.filter(t=>t.weekKey===wk&&isM(t));
  const todayT=(C.day[todayK()]||[]).filter(isM);
  const allDays=Object.keys(C.day).sort().reverse();
  const histDays=allDays.map(k=>({key:k,tasks:(C.day[k]||[]).filter(isM)})).filter(x=>x.tasks.length);
  const wDone=weekT.filter(t=>t.status==='Выполнено').length;
  const wTotal=weekT.length;
  const wPct=wTotal?Math.round(wDone/wTotal*100):0;
  const totalTrs=histDays.reduce((s,d)=>s+d.tasks.reduce((ss,t)=>ss+(t.transfers||0),0),0);
  const totalDone=histDays.reduce((s,d)=>s+d.tasks.filter(t=>t.status==='Выполнено').length,0);
  const pColor=wPct>=80?'var(--green)':wPct>=50?'var(--accent)':'var(--yellow)';
  const tRow=t=>`<div class="pt-row"><div style="flex:1"><div class="pt-name">${t.name||t.main}</div>${t.detail?`<div class="pt-sub">${t.detail}</div>`:''}</div>${(t.transfers||0)>0?`<span class="tr-badge">↩${t.transfers}</span>`:''}<span style="font-size:11px;font-weight:600;padding:2px 8px;border-radius:10px;background:${sbg(t.status)};color:${sfc(t.status)}">${t.status}</span></div>`;
  let h=`<div class="profile-hdr"><div class="profile-av" style="background:${m.color}">${m.name.slice(0,1)}</div><div style="flex:1"><div class="profile-name">${m.name}</div><div class="profile-role">${m.role}</div><div class="profile-stats-row"><div class="pst"><div class="pst-n">${masterT.length}</div><div class="pst-l">Мастер</div></div><div class="pst y"><div class="pst-n">${wTotal}</div><div class="pst-l">Неделя</div></div><div class="pst g"><div class="pst-n">${wDone}</div><div class="pst-l">Выполнено</div></div><div class="pst"><div class="pst-n">${wPct}%</div><div class="pst-l">Прогресс</div></div><div class="pst r"><div class="pst-n">${totalTrs}</div><div class="pst-l">Переносов</div></div><div class="pst g"><div class="pst-n">${totalDone}</div><div class="pst-l">Всего сделано</div></div></div><div class="profile-prog"><div class="profile-prog-fill" style="width:${wPct}%;background:${pColor}"></div></div></div></div>`;
  if(todayT.length){h+=`<div class="psec"><div class="psec-title">☀ Сегодня (${todayT.length})</div>`;todayT.forEach(t=>h+=tRow(t));h+='</div>';}
  if(weekT.length){h+=`<div class="psec"><div class="psec-title">📅 Текущая неделя (${wDone}/${wTotal})</div>`;weekT.forEach(t=>h+=tRow(t));h+='</div>';}
  if(masterT.length){h+=`<div class="psec"><div class="psec-title">🗂 В мастере (${masterT.length})</div>`;masterT.forEach(t=>h+=tRow(t));h+='</div>';}
  if(histDays.length){h+=`<div class="psec"><div class="psec-title">📋 История по дням</div>`;histDays.forEach(({key,tasks})=>{const done2=tasks.filter(t=>t.status==='Выполнено').length;const pct2=tasks.length?Math.round(done2/tasks.length*100):0;h+=`<div class="dh-row"><div class="dh-date">${fmtDayShort(key)} — ${done2}/${tasks.length} (${pct2}%)</div><div class="dh-chips">`;tasks.forEach(t=>{const tr=t.transfers||0;h+=`<span class="dchip" style="background:${sbg(t.status)};color:${sfc(t.status)}">${t.name||t.main}${tr>0?' ↩'+tr:''}</span>`;});h+='</div></div>';});h+='</div>';}
  document.getElementById('mProfileTitle').textContent=m.name+' — профиль';
  document.getElementById('profile-content').innerHTML=h;
  document.getElementById('mProfile').classList.add('open');
};

// ═══ STATUS UPDATE ═══
window.updateStatus=async(ctx,id,val)=>{
  if(!isAdmin)return;
  if(ctx==='master'){await fsUpd('master',id,{status:val});}
  else if(ctx==='week'){await fsUpd('week',id,{status:val});const t=C.week.find(x=>x.id===id);if(t)await syncUp(t.name||t.main,t.dir,val);}
  else if(ctx==='day'){
    await fsUpd('day',id,{status:val});
    const t=(C.day[curDayK()]||[]).find(x=>x.id===id);
    if(t){await syncUp(t.name||t.main,t.dir,val);if(val==='Выполнено')toast('✅ Выполнено! Обновлено в задачах');}
  }
};
async function syncUp(name,dir,val){
  const wt=C.week.find(x=>(x.name||x.main)===name&&x.dir===dir);
  if(wt){if(val==='Выполнено')await fsUpd('week',wt.id,{status:'Выполнено'});else if(val==='В работе'&&wt.status==='Не начато')await fsUpd('week',wt.id,{status:'В работе'});}
  const mt=C.master.find(x=>(x.name||x.main)===name&&x.dir===dir);
  if(mt){if(val==='Выполнено')await fsUpd('master',mt.id,{status:'Выполнено'});else if(val==='В работе'&&mt.status==='Не начато')await fsUpd('master',mt.id,{status:'В работе'});}
}

// PUSH TASKS
window.pushToWeek=async(mid)=>{
  const t=C.master.find(x=>x.id===mid);if(!t)return;
  const wk=wkKey(weekOff);
  if(C.week.some(x=>x.weekKey===wk&&(x.name||x.main)===(t.name||t.main))){toast('Уже есть в неделе');return;}
  const id=genId();
  await fsSet('week',id,{id,weekKey:wk,dir:t.dir,name:t.name||t.main,main:t.name||t.main,detail:t.detail||'',owner:t.owner||'',speed:3,status:'Не начато',comment:'',parentId:mid});
  toast('📅 Добавлено в неделю');switchView('week');
};
window.pushToDay=async(sid)=>{
  const t=C.master.find(x=>x.id===sid)||C.week.find(x=>x.id===sid);if(!t)return;
  const key=curDayK();
  if((C.day[key]||[]).some(x=>(x.name||x.main)===(t.name||t.main))){toast('Уже есть сегодня');return;}
  const id=genId();
  await fsSet('day',id,{id,dayKey:key,dir:t.dir,name:t.name||t.main,main:t.name||t.main,detail:t.detail||'',owner:t.owner||'',speed:t.speed||3,status:'Не начато',deadline:'',transfers:0,parentId:sid});
  switchView('today');toast('☀ Добавлено на сегодня');
};

// FROM WEEK MODAL
window.openFromWeek=()=>{
  const wk=wkKey(weekOff);const wTasks=C.week.filter(t=>t.weekKey===wk&&t.status!=='Выполнено');
  const dk=curDayK();const dTasks=C.day[dk]||[];
  let h='';
  if(!wTasks.length)h='<div class="empty"><div>Нет незавершённых задач в неделе</div></div>';
  else wTasks.forEach(t=>{
    const already=dTasks.some(x=>(x.name||x.main)===(t.name||t.main));
    h+=`<label style="display:flex;align-items:center;gap:10px;padding:10px;border-bottom:1px solid var(--gray-100);cursor:pointer"><input type="checkbox" value="${t.id}" ${already?'disabled checked':''} style="width:16px;height:16px"><div><div style="font-weight:500;font-size:13px">${t.name||t.main}</div><div style="font-size:11px;color:var(--gray-400)">${t.dir}${t.detail?' · '+t.detail:''} ${already?'<span style="color:var(--green)">— уже добавлено</span>':''}</div></div></label>`;
  });
  // Also show master tasks
  const masterActives=C.master.filter(t=>t.status!=='Выполнено'&&(!t.parentId||!C.master.find(m=>m.id===t.parentId)));
  if(masterActives.length){
    h+=`<div style="font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--gray-400);padding:12px 0 6px">🗂 Из мастера</div>`;
    masterActives.forEach(t=>{
      const already=dTasks.some(x=>(x.name||x.main)===(t.name||t.main));
      h+=`<label style="display:flex;align-items:center;gap:10px;padding:10px;border-bottom:1px solid var(--gray-100);cursor:pointer"><input type="checkbox" value="m-${t.id}" ${already?'disabled checked':''} style="width:16px;height:16px"><div><div style="font-weight:500;font-size:13px">${t.name||t.main}</div><div style="font-size:11px;color:var(--gray-400)">${t.dir} ${already?'<span style="color:var(--green)">— уже добавлено</span>':''}</div></div></label>`;
    });
  }
  document.getElementById('from-week-list').innerHTML=h;
  document.getElementById('mFromWeek').classList.add('open');
};
window.confirmFromWeek=async()=>{
  const checks=document.querySelectorAll('#from-week-list input:checked:not(:disabled)');
  const key=curDayK();let added=0;
  for(const cb of checks){
    const isMaster=cb.value.startsWith('m-');
    const realId=isMaster?cb.value.slice(2):cb.value;
    const t=isMaster?C.master.find(x=>x.id===realId):C.week.find(x=>x.id===realId);
    if(t){const id=genId();await fsSet('day',id,{id,dayKey:key,dir:t.dir,name:t.name||t.main,main:t.name||t.main,detail:t.detail||'',owner:t.owner||'',speed:t.speed||3,status:'Не начато',deadline:'',transfers:0,parentId:realId});added++;}
  }
  closeM('mFromWeek');if(added)toast('☀ Добавлено '+added+' задач');
};

// ADD TASK MODAL
window.openAddModal=ctx=>{
  mCtx=ctx;
  document.getElementById('mTaskTitle').textContent=ctx==='master'?'+ Основная задача':ctx==='week'?'+ Подзадача':'+ Активность';
  ['f-name','f-detail','f-comment'].forEach(id=>{const el=document.getElementById(id);if(el)el.value='';});
  document.getElementById('f-dir').value='Проекты';
  document.getElementById('f-speed').value='3';
  const fdl=document.getElementById('f-deadline');if(fdl)fdl.value='';
  document.getElementById('f-deadline-grp').style.display=ctx==='day'?'':'none';
  const pg=document.getElementById('f-parent-grp');
  const ps=document.getElementById('f-parent');
  ps.innerHTML='<option value="">— без привязки —</option>';
  if(ctx==='week'){pg.style.display='';document.getElementById('f-parent-lbl').textContent='основной задаче';C.master.filter(t=>!t.parentId||!C.master.find(m=>m.id===t.parentId)).forEach(t=>ps.innerHTML+=`<option value="${t.id}">${t.name||t.main}</option>`);}
  else if(ctx==='day'){pg.style.display='';document.getElementById('f-parent-lbl').textContent='подзадаче';C.week.filter(t=>t.weekKey===wkKey(weekOff)).forEach(t=>ps.innerHTML+=`<option value="${t.id}">${t.name||t.main}</option>`);}
  else pg.style.display='none';
  const sel=document.getElementById('f-owner');sel.innerHTML='<option value="">— выбрать —</option>';
  owners().forEach(n=>sel.innerHTML+=`<option>${n}</option>`);
  document.getElementById('mTask').classList.add('open');
};
window.saveTask=async()=>{
  const dir=document.getElementById('f-dir').value;
  const name=document.getElementById('f-name').value.trim();
  const detail=document.getElementById('f-detail').value.trim();
  const owner=document.getElementById('f-owner').value;
  const speed=parseInt(document.getElementById('f-speed').value);
  const deadline=document.getElementById('f-deadline')?document.getElementById('f-deadline').value:'';
  const comment=document.getElementById('f-comment').value.trim();
  const parentId=document.getElementById('f-parent').value||'';
  if(!name){alert('Введите название');return;}
  const id=genId();
  if(mCtx==='master')await fsSet('master',id,{id,dir,name,main:name,detail,owner,status:'Не начато',comment,parentId:''});
  else if(mCtx==='week')await fsSet('week',id,{id,weekKey:wkKey(weekOff),dir,name,main:name,detail,owner,speed,status:'Не начато',comment,parentId});
  else if(mCtx==='day'){const key=curDayK();await fsSet('day',id,{id,dayKey:key,dir,name,main:name,detail,owner,speed,status:'Не начато',deadline,transfers:0,parentId});}
  closeM('mTask');toast('✅ Задача добавлена');
};
window.delTask=async(ctx,id)=>{if(!confirm('Удалить?'))return;await fsDel(ctx,id);};

// SUBTASK
window.openSubtask=parentId=>{
  const p=C.master.find(x=>x.id===parentId);if(!p)return;
  stParentId=parentId;
  document.getElementById('mSubtaskTitle').textContent='+ Подзадача к: '+(p.name||p.main);
  document.getElementById('stParentName').textContent=(p.name||p.main);
  ['st-name','st-detail'].forEach(id=>document.getElementById(id).value='');
  document.getElementById('st-speed').value='3';
  document.getElementById('st-target').value='week';
  const sel=document.getElementById('st-owner');sel.innerHTML='<option value="">— выбрать —</option>';
  owners().forEach(n=>sel.innerHTML+=`<option>${n}</option>`);
  document.getElementById('mSubtask').classList.add('open');
};
window.saveSubtask=async()=>{
  const name=document.getElementById('st-name').value.trim();
  if(!name){alert('Введите название');return;}
  const p=C.master.find(x=>x.id===stParentId);if(!p)return;
  const detail=document.getElementById('st-detail').value.trim();
  const owner=document.getElementById('st-owner').value;
  const speed=parseInt(document.getElementById('st-speed').value);
  const target=document.getElementById('st-target').value;
  const mid=genId();
  await fsSet('master',mid,{id:mid,dir:p.dir,name,main:name,detail,owner,status:'Не начато',comment:'',parentId:stParentId});
  if(target==='week'||target==='day'){
    const wid=genId();
    await fsSet('week',wid,{id:wid,weekKey:wkKey(weekOff),dir:p.dir,name,main:name,detail,owner,speed,status:'Не начато',comment:'',parentId:mid});
    if(target==='day'){const did=genId();const key=curDayK();await fsSet('day',did,{id:did,dayKey:key,dir:p.dir,name,main:name,detail,owner,speed,status:'Не начато',deadline:'',transfers:0,parentId:wid});}
  }
  expandedIds.add(stParentId);
  closeM('mSubtask');toast('Подзадача создана');
};

// TEAM
window.openTeamModal=()=>{editTeamId=null;document.getElementById('mTeamTitle').textContent='Добавить';['tm-name','tm-role'].forEach(id=>document.getElementById(id).value='');document.getElementById('tm-type').value='active';document.getElementById('tm-color').value='#2E7CF6';document.getElementById('mTeam').classList.add('open');};
window.editMember=id=>{const m=C.team.find(x=>x.id===id);if(!m)return;editTeamId=id;document.getElementById('mTeamTitle').textContent='Редактировать';document.getElementById('tm-type').value=m.type;document.getElementById('tm-name').value=m.name||'';document.getElementById('tm-role').value=m.role||'';document.getElementById('tm-color').value=m.color||'#2E7CF6';document.getElementById('mTeam').classList.add('open');};
window.saveMember=async()=>{const type=document.getElementById('tm-type').value,name=document.getElementById('tm-name').value.trim(),role=document.getElementById('tm-role').value.trim(),color=document.getElementById('tm-color').value;if(!role){alert('Введите должность');return;}const id=editTeamId||genId();await fsSet('team',id,{id,type,name,role,color});closeM('mTeam');toast('Сохранено');};
window.delMember=async id=>{if(!confirm('Удалить?'))return;await fsDel('team',id);};
window.toggleVac=()=>{document.getElementById('tm-name-grp').style.display=document.getElementById('tm-type').value==='vacancy'?'none':'';};

// NAV
window.changeDay=d=>{dayOff+=d;renderToday();};
window.changeWeek=d=>{weekOff+=d;renderWeek();};
window.changeRptWeek=d=>{rptWeekOff+=d;updateRptWeekLabel();};

// REPORTS
function updateRptWeekLabel(){
  const el=document.getElementById('rpt-week-lbl');if(el)el.textContent=wkRange(rptWeekOff);
}
function initReportDates(){
  const today=new Date();
  const to=new Date(today);
  const from=new Date(today);from.setDate(today.getDate()-13);
  const f=document.getElementById('rpt-from');const t2=document.getElementById('rpt-to');
  if(f)f.value=toKey(from);if(t2)t2.value=toKey(to);
  updateRptWeekLabel();
}

window.generateWeeklyText=()=>{
  const wk=wkKey(rptWeekOff);
  const wTasks=C.week.filter(t=>t.weekKey===wk);
  const output=document.getElementById('weekly-text-output');
  if(!wTasks.length){output.style.display='block';output.innerHTML='<div class="empty">Нет задач за эту неделю</div>';return;}
  const groups={};
  wTasks.forEach(t=>{if(!groups[t.dir])groups[t.dir]=[];groups[t.dir].push(t);});
  let html=`<div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:16px"><div style="font-weight:700;font-size:15px;color:var(--navy)">Отчёт за неделю: ${wkRange(rptWeekOff)}</div><button class="btn btn-outline btn-sm" onclick="copyWeeklyText()">📋 Скопировать</button></div>`;
  Object.entries(groups).forEach(([dir,tasks])=>{
    html+=`<div style="margin-bottom:14px"><div style="font-size:12px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--gray-400);margin-bottom:8px">${dir}</div>`;
    tasks.forEach(t=>{
      const cls=statusClass(t.status);
      html+=`<div style="display:flex;align-items:center;gap:8px;padding:6px 0;border-bottom:1px solid var(--gray-100)"><span style="font-size:13px;flex:1">${t.name||t.main}${t.detail?' — '+t.detail:''}</span><span class="sbadge ${cls}">${t.status}</span></div>`;
    });
    html+='</div>';
  });
  output.style.display='block';output.innerHTML=html;
};
window.copyWeeklyText=()=>{
  const wk=wkKey(rptWeekOff);const wTasks=C.week.filter(t=>t.weekKey===wk);
  let text=`Отчёт за неделю: ${wkRange(rptWeekOff)}\n\n`;
  const groups={};wTasks.forEach(t=>{if(!groups[t.dir])groups[t.dir]=[];groups[t.dir].push(t);});
  Object.entries(groups).forEach(([dir,tasks])=>{text+=dir+':\n';tasks.forEach(t=>{text+=`• ${t.name||t.main}${t.detail?' — '+t.detail:''} [${t.status}]\n`;});text+='\n';});
  navigator.clipboard.writeText(text).then(()=>toast('📋 Скопировано')).catch(()=>toast('Не удалось скопировать'));
};

// REPORT BUILDER
window.openBuilder=()=>{
  const from=document.getElementById('rpt-from').value;
  const to=document.getElementById('rpt-to').value;
  const dayKeys=Object.keys(C.day).filter(k=>k>=from&&k<=to);
  const activeMasterIds=new Set();
  dayKeys.forEach(dk=>(C.day[dk]||[]).forEach(t=>{const wt=C.week.find(w=>w.id===t.parentId);if(wt&&wt.parentId)activeMasterIds.add(wt.parentId);else if(wt)activeMasterIds.add(wt.id);}));
  C.week.filter(t=>t.weekKey>=from&&t.weekKey<=to).forEach(t=>{if(t.parentId)activeMasterIds.add(t.parentId);else activeMasterIds.add(t.id);});
  let masterTasks=C.master.filter(t=>!t.parentId||!C.master.find(m=>m.id===t.parentId));
  if(activeMasterIds.size>0)masterTasks=masterTasks.filter(t=>activeMasterIds.has(t.id));
  builderSels={};
  masterTasks.forEach(mt=>{const subs=C.master.filter(t=>t.parentId===mt.id);const subSel={};subs.forEach(st=>subSel[st.id]=true);builderSels[mt.id]={include:true,subtasks:subSel};});
  let h='';
  if(!masterTasks.length)h='<div class="empty"><div>Нет задач за выбранный период</div></div>';
  else masterTasks.forEach(mt=>{
    const subs=C.master.filter(t=>t.parentId===mt.id);
    h+=`<div class="builder-task" id="btb-${mt.id}"><div class="builder-task-hdr"><input type="checkbox" id="bchk-${mt.id}" checked onchange="toggleBSel('${mt.id}',this.checked)" style="width:15px;height:15px;cursor:pointer">${dirTag(mt.dir)}<span style="font-weight:600;font-size:13px;flex:1">${mt.name||mt.main}</span><span class="sbadge ${statusClass(mt.status)}">${mt.status}</span></div>`;
    subs.forEach(st=>{h+=`<div class="builder-sub"><input type="checkbox" id="bchk-${st.id}" checked onchange="toggleBSubSel('${mt.id}','${st.id}',this.checked)" style="width:13px;height:13px;cursor:pointer"><span style="font-size:11px">└─</span><span style="flex:1">${st.name||st.main}</span><span class="sbadge ${statusClass(st.status)}" style="font-size:10px">${st.status}</span></div>`;});
    h+='</div>';
  });
  document.getElementById('builder-list').innerHTML=h;
  document.getElementById('builder-step1').style.display='';
  document.getElementById('builder-step2').style.display='none';
  document.getElementById('mBuilderTitle').textContent='📊 Конструктор презентации';
  document.getElementById('mBuilder').classList.add('open');
};
window.toggleBSel=(id,v)=>{if(builderSels[id])builderSels[id].include=v;const b=document.getElementById('btb-'+id);if(b)b.style.opacity=v?'1':'0.4';};
window.toggleBSubSel=(pid,sid,v)=>{if(builderSels[pid])builderSels[pid].subtasks[sid]=v;};
window.backToStep1=()=>{document.getElementById('builder-step1').style.display='';document.getElementById('builder-step2').style.display='none';};

window.generateReport=async()=>{
  document.getElementById('builder-step1').innerHTML='<div class="generating"><div class="spin">⚙️</div><div style="margin-top:16px;font-size:14px;color:var(--gray-500)">AI генерирует текст...</div></div>';
  const selected=[];
  for(const[mtId,sel]of Object.entries(builderSels)){
    if(!sel.include)continue;
    const mt=C.master.find(t=>t.id===mtId);if(!mt)continue;
    const selectedSubs=C.master.filter(t=>t.parentId===mtId&&sel.subtasks[t.id]);
    selected.push({master:mt,subs:selectedSubs});
  }
  if(!selected.length){toast('Выбери хотя бы одну задачу');return;}
  const from=document.getElementById('rpt-from').value;
  const to=document.getElementById('rpt-to').value;
  const taskDesc=selected.map(({master,subs})=>{let d=`Задача: ${master.name||master.main} (${master.dir}, статус: ${master.status})`;if(subs.length)d+='\nПодзадачи:\n'+subs.map(s=>`  - ${s.name||s.main} [${s.status}]`).join('\n');return d;}).join('\n\n');
  const prompt=`Ты помогаешь руководителю Процессного офиса казахстанской компании Sergek Group подготовить презентацию для куратора и CEO.\n\nДля каждой задачи напиши 3-4 конкретных bullet point на русском языке о том что было сделано за период ${from} – ${to}. Пиши профессионально, кратко, используй глаголы в прошедшем времени. Не упоминай имена сотрудников.\n\nТакже для последнего слайда напиши по одному предложению "следующий шаг" для каждой задачи.\n\nЗадачи:\n${taskDesc}\n\nОтветь строго в формате JSON без markdown:\n{"tasks":[{"id":"0","bullets":["пункт 1","пункт 2","пункт 3"],"nextStep":"следующий шаг"}]}`;
  try{
    const resp=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({model:'claude-sonnet-4-6',max_tokens:1000,messages:[{role:'user',content:prompt}]})});
    const data=await resp.json();
    const text=data.content.map(c=>c.text||'').join('');
    const clean=text.replace(/```json|```/g,'').trim();
    const aiResult=JSON.parse(clean);
    generatedData={tasks:selected.map(({master,subs},i)=>{const ai=aiResult.tasks.find(t=>parseInt(t.id)===i)||{bullets:[],nextStep:''};return{id:master.id,name:master.name||master.main,dir:master.dir,status:master.status,bullets:ai.bullets||[],nextStep:ai.nextStep||'',comment:''};})};
  }catch(e){
    generatedData={tasks:selected.map(({master,subs})=>({id:master.id,name:master.name||master.main,dir:master.dir,status:master.status,bullets:subs.filter(s=>s.status!=='Не начато').map(s=>s.name||s.main),nextStep:subs.filter(s=>s.status!=='Выполнено').map(s=>s.name||s.main).join(', ')||'Продолжить работу',comment:''}))};
  }
  showBuilderStep2();
};

function showBuilderStep2(){
  const from=document.getElementById('rpt-from').value;const to=document.getElementById('rpt-to').value;
  const period=`${from} – ${to}`;
  const today=new Date().toLocaleDateString('ru-RU',{day:'numeric',month:'long',year:'numeric'});
  let h=`<div class="preview-slide"><div style="font-size:11px;color:var(--gray-400);margin-bottom:4px">СЛАЙД 1 · Титульный</div><div class="preview-slide-title">Процессный офис</div><div class="preview-meta">${today} · ${period}</div><div style="font-size:12px;color:var(--gray-600)">${generatedData.tasks.map((t,i)=>`${i+1}. ${t.name}`).join(' · ')}</div></div>`;
  generatedData.tasks.forEach((task,i)=>{
    h+=`<div class="preview-slide"><div style="font-size:11px;color:var(--gray-400);margin-bottom:4px">СЛАЙД ${i+2} · ${task.dir}</div><div class="preview-slide-title">${task.name}</div><div class="preview-meta" style="display:flex;gap:6px">${dirTag(task.dir)}<span class="sbadge ${statusClass(task.status)}">${task.status}</span></div><div style="font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:var(--accent);margin:10px 0 6px">ЧТО СДЕЛАНО</div>`;
    task.bullets.forEach((b,bi)=>{h+=`<input class="preview-bullet" value="${b}" onchange="generatedData.tasks[${i}].bullets[${bi}]=this.value"/>`;});
    h+=`<div style="margin-top:4px"><span style="font-size:11px;color:var(--gray-400)">+ добавить пункт</span> <button onclick="generatedData.tasks[${i}].bullets.push('');showBuilderStep2()" style="border:none;background:none;color:var(--accent);cursor:pointer;font-size:12px">＋</button></div>
    <textarea class="preview-comment" placeholder="Комментарий (необязательно)..." onchange="generatedData.tasks[${i}].comment=this.value">${task.comment}</textarea></div>`;
  });
  h+=`<div class="next-steps-preview"><div style="font-size:11px;color:rgba(255,255,255,.5);margin-bottom:8px;text-transform:uppercase;letter-spacing:.6px">ПОСЛЕДНИЙ СЛАЙД · Ближайшие шаги</div>`;
  generatedData.tasks.forEach((task,i)=>{h+=`<div style="display:flex;align-items:center;gap:8px;margin-bottom:4px"><span style="color:var(--accent)">●</span><input class="next-step-input" value="${task.name}: ${task.nextStep}" onchange="generatedData.tasks[${i}].nextStep=this.value.replace(/^[^:]+: ?/,'')"/></div>`;});
  h+='</div>';
  document.getElementById('builder-step1').style.display='none';
  document.getElementById('builder-step2').style.display='';
  document.getElementById('builder-preview').innerHTML=h;
}

window.downloadPPTX=async()=>{
  const btn=document.getElementById('dl-btn');btn.textContent='⏳ Создаём...';btn.disabled=true;
  try{
    if(!window.PptxGenJS){
      await new Promise((res,rej)=>{const s=document.createElement('script');s.src='https://cdn.jsdelivr.net/npm/pptxgenjs@3.12.0/dist/pptxgen.bundle.js';s.onload=res;s.onerror=rej;document.head.appendChild(s);});
    }
    const from=document.getElementById('rpt-from').value;const to=document.getElementById('rpt-to').value;
    const period=`${from} – ${to}`;
    const today=new Date().toLocaleDateString('ru-RU',{day:'numeric',month:'long',year:'numeric'});
    const nextFrom=new Date(to+'T12:00:00');nextFrom.setDate(nextFrom.getDate()+1);
    const nextTo=new Date(nextFrom);nextTo.setDate(nextFrom.getDate()+13);
    const fmt=x=>x.toLocaleDateString('ru-RU',{day:'numeric',month:'short'});
    const nextPeriod=fmt(nextFrom)+' – '+fmt(nextTo);
    const N='0D2B4E',W='FFFFFF',A='2E7CF6',GR='64748B',GN='16A34A',YL='D97706';
    const pres=new window.PptxGenJS();pres.layout='LAYOUT_16x9';
    // SLIDE 1
    const s1=pres.addSlide();s1.background={color:N};
    s1.addText('sergek group',{x:.5,y:.35,w:9,h:.3,fontSize:10,color:'7AAEF5',charSpacing:3,fontFace:'Calibri',margin:0});
    s1.addText('Процессный офис',{x:.5,y:.85,w:9,h:.7,fontSize:32,color:W,bold:true,fontFace:'Calibri',margin:0});
    s1.addText(today,{x:.5,y:1.55,w:9,h:.4,fontSize:16,color:'94B8E8',fontFace:'Calibri',margin:0});
    s1.addText(period,{x:.5,y:1.95,w:9,h:.3,fontSize:13,color:'7AAEF5',fontFace:'Calibri',margin:0});
    s1.addShape(pres.ShapeType.rect,{x:.5,y:2.45,w:9,h:.02,fill:{color:A,transparency:40},line:{color:A,transparency:40}});
    generatedData.tasks.forEach((t,i)=>{
      s1.addShape(pres.ShapeType.ellipse,{x:.5,y:2.65+i*.38,w:.28,h:.28,fill:{color:A},line:{color:A}});
      s1.addText(String(i+1).padStart(2,'0'),{x:.5,y:2.64+i*.38,w:.28,h:.3,fontSize:9,color:W,bold:true,align:'center',valign:'middle',fontFace:'Calibri',margin:0});
      s1.addText(t.name,{x:.9,y:2.65+i*.38,w:8.1,h:.3,fontSize:13,color:'D1E4FF',fontFace:'Calibri',margin:0,valign:'middle'});
    });
    // TASK SLIDES
    const dC={'Проекты':{bg:'EDE9FE',tx:'6D28D9'},'IT|AI':{bg:'DBEAFE',tx:'1D4ED8'},'Методология':{bg:'FCE7F3',tx:'9D174D'},'SimBASE':{bg:'FEF3C7',tx:'92400E'}};
    const sC={'Выполнено':{bg:'DCFCE7',tx:GN},'В работе':{bg:'FEF3C7',tx:YL},'Не начато':{bg:'F1F5F9',tx:GR}};
    for(const task of generatedData.tasks){
      const sl=pres.addSlide();sl.background={color:W};
      sl.addShape(pres.ShapeType.rect,{x:0,y:0,w:10,h:1.35,fill:{color:N},line:{color:N}});
      sl.addText('Процессный офис  ·  '+period,{x:.5,y:.12,w:9,h:.25,fontSize:9,color:'7AAEF5',charSpacing:1,fontFace:'Calibri',margin:0});
      sl.addText(task.name,{x:.5,y:.38,w:7.5,h:.55,fontSize:22,color:W,bold:true,fontFace:'Calibri',margin:0,valign:'middle'});
      const dc=dC[task.dir]||{bg:'F1F5F9',tx:'475569'};
      sl.addShape(pres.ShapeType.roundRect,{x:.5,y:1,w:1.3,h:.26,fill:{color:dc.bg},line:{color:dc.bg},rectRadius:.04});
      sl.addText(task.dir,{x:.5,y:1,w:1.3,h:.26,fontSize:9,color:dc.tx,bold:true,align:'center',valign:'middle',fontFace:'Calibri',margin:0});
      const sc=sC[task.status]||{bg:'F1F5F9',tx:GR};
      sl.addShape(pres.ShapeType.roundRect,{x:1.95,y:1,w:1.4,h:.26,fill:{color:sc.bg},line:{color:sc.bg},rectRadius:.04});
      sl.addText(task.status,{x:1.95,y:1,w:1.4,h:.26,fontSize:9,color:sc.tx,bold:true,align:'center',valign:'middle',fontFace:'Calibri',margin:0});
      const hasC=task.comment&&task.comment.trim();const cW=hasC?5.8:9.2;
      sl.addText('ЧТО СДЕЛАНО',{x:.5,y:1.55,w:cW,h:.28,fontSize:9,color:A,bold:true,charSpacing:1.5,fontFace:'Calibri',margin:0});
      const bullets=(task.bullets||[]).filter(Boolean);
      if(bullets.length)sl.addText(bullets.map((b,idx)=>({text:b,options:{bullet:true,breakLine:idx<bullets.length-1,fontSize:13,color:'1E293B',fontFace:'Calibri',paraSpaceAfter:4}})),{x:.5,y:1.87,w:cW,h:3.3,valign:'top',fontFace:'Calibri'});
      if(hasC){sl.addShape(pres.ShapeType.roundRect,{x:6.8,y:1.55,w:2.8,h:3.6,fill:{color:'F8FAFC'},line:{color:'E2E8F0',width:1},rectRadius:.1});sl.addText('КОММЕНТАРИЙ',{x:6.9,y:1.7,w:2.6,h:.25,fontSize:8,color:GR,bold:true,charSpacing:1,fontFace:'Calibri',margin:0});sl.addText(task.comment,{x:6.9,y:2,w:2.6,h:3,fontSize:12,color:'334155',valign:'top',fontFace:'Calibri',margin:0});}
    }
    // LAST SLIDE
    const ls=pres.addSlide();ls.background={color:N};
    ls.addText('sergek group',{x:.5,y:.35,w:9,h:.3,fontSize:10,color:'7AAEF5',charSpacing:3,fontFace:'Calibri',margin:0});
    ls.addText('Ближайшие шаги',{x:.5,y:.8,w:9,h:.6,fontSize:28,color:W,bold:true,fontFace:'Calibri',margin:0});
    ls.addText(nextPeriod,{x:.5,y:1.42,w:9,h:.3,fontSize:13,color:'7AAEF5',fontFace:'Calibri',margin:0});
    ls.addShape(pres.ShapeType.rect,{x:.5,y:1.82,w:9,h:.02,fill:{color:A,transparency:40},line:{color:A,transparency:40}});
    generatedData.tasks.forEach((task,i)=>{
      ls.addShape(pres.ShapeType.ellipse,{x:.5,y:2.07+i*.38,w:.24,h:.24,fill:{color:A},line:{color:A}});
      ls.addText(`${task.name}: ${task.nextStep}`,{x:.85,y:2.05+i*.38,w:8.6,h:.3,fontSize:13,color:'D1E4FF',valign:'middle',fontFace:'Calibri',margin:0});
    });
    await pres.writeFile({fileName:`Процессный_офис_${today.replace(/ /g,'_')}.pptx`});
    toast('✅ Презентация скачана!');
  }catch(e){toast('Ошибка: '+e.message);}
  finally{btn.textContent='⬇ Скачать PPTX';btn.disabled=false;}
};

// VIEW
window.switchView=v=>{
  document.querySelectorAll('.view').forEach(x=>x.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(x=>x.classList.remove('active'));
  document.getElementById('view-'+v).classList.add('active');
  document.querySelectorAll('.nav-item').forEach(t=>{if(t.getAttribute('onclick')===`switchView('${v}')`)t.classList.add('active');});
  if(v==='reports')initReportDates();
};

// MODAL
window.closeM=id=>document.getElementById(id).classList.remove('open');
document.querySelectorAll('.overlay').forEach(el=>el.addEventListener('click',e=>{if(e.target===el)el.classList.remove('open');}));

// TOAST
let tTimer;
window.toast=msg=>{const el=document.getElementById('toast');el.textContent=msg;el.classList.add('show');clearTimeout(tTimer);tTimer=setTimeout(()=>el.classList.remove('show'),2800);};

function renderAll(){renderToday();renderWeek();renderMaster();renderTeam();renderHistory();updateBadges();}

// INIT
document.getElementById('hdrDate').textContent=new Date().toLocaleDateString('ru-RU',{weekday:'long',day:'numeric',month:'long',year:'numeric'});
startListeners();
</script>
</body>
</html>
