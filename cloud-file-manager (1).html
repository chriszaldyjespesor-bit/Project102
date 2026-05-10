<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>VAULT — Cloud File Manager</title>

<!-- Firebase SDKs (v9 compat) -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/firebase/9.23.0/firebase-app-compat.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/firebase/9.23.0/firebase-auth-compat.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/firebase/9.23.0/firebase-storage-compat.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/firebase/9.23.0/firebase-firestore-compat.min.js"></script>

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Barlow+Condensed:wght@300;400;600;700;900&family=Barlow:wght@300;400;500&display=swap" rel="stylesheet"/>

<style>
:root {
  --bg: #0a0b0d;
  --surface: #111318;
  --surface2: #181b22;
  --border: #1f2430;
  --border2: #2a3040;
  --accent: #00e5ff;
  --accent2: #ff4d6d;
  --accent3: #b8ff5a;
  --text: #c8d0e0;
  --text2: #6b7890;
  --text3: #3a4258;
  --white: #eef2ff;
  --mono: 'Share Tech Mono', monospace;
  --display: 'Barlow Condensed', sans-serif;
  --body: 'Barlow', sans-serif;
  --radius: 4px;
  --glow: 0 0 20px rgba(0,229,255,0.15);
  --glow2: 0 0 20px rgba(255,77,109,0.2);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--body);
  min-height: 100vh;
  overflow-x: hidden;
  background-image:
    radial-gradient(ellipse 80% 50% at 50% -20%, rgba(0,229,255,0.06) 0%, transparent 60%),
    repeating-linear-gradient(0deg, transparent, transparent 39px, rgba(255,255,255,0.015) 39px, rgba(255,255,255,0.015) 40px),
    repeating-linear-gradient(90deg, transparent, transparent 39px, rgba(255,255,255,0.015) 39px, rgba(255,255,255,0.015) 40px);
}

/* NOISE OVERLAY */
body::before {
  content: '';
  position: fixed; inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none; z-index: 9999; opacity: 0.4;
}

/* SCROLLBAR */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--bg); }
::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }

/* ─── SETUP SCREEN ─────────────────────────────────────── */
#setup-screen {
  position: fixed; inset: 0;
  display: flex; align-items: center; justify-content: center;
  z-index: 1000; background: var(--bg);
  flex-direction: column; gap: 0;
  padding: 24px;
}
#setup-screen.hidden { display: none; }

.setup-box {
  width: 100%; max-width: 560px;
  background: var(--surface);
  border: 1px solid var(--border2);
  border-radius: 2px;
  padding: 40px;
  position: relative;
  overflow: hidden;
}
.setup-box::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 2px;
  background: linear-gradient(90deg, transparent, var(--accent), transparent);
}

.setup-logo {
  font-family: var(--display);
  font-size: 52px; font-weight: 900;
  letter-spacing: 8px;
  color: var(--white);
  text-transform: uppercase;
  line-height: 1;
  margin-bottom: 4px;
}
.setup-logo span { color: var(--accent); }

.setup-sub {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--text2);
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 32px;
}

.setup-label {
  font-family: var(--mono);
  font-size: 10px;
  color: var(--accent);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 8px;
  display: block;
}

.setup-input {
  width: 100%;
  background: var(--bg);
  border: 1px solid var(--border2);
  border-radius: var(--radius);
  padding: 12px 16px;
  color: var(--white);
  font-family: var(--mono);
  font-size: 13px;
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
  margin-bottom: 16px;
}
.setup-input:focus {
  border-color: var(--accent);
  box-shadow: var(--glow);
}
.setup-input::placeholder { color: var(--text3); }

.setup-row { display: flex; gap: 12px; margin-bottom: 24px; }

.setup-btn {
  flex: 1; padding: 14px;
  font-family: var(--display);
  font-size: 16px; font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  border: none; border-radius: var(--radius);
  cursor: pointer;
  transition: all 0.2s;
}
.setup-btn.primary {
  background: var(--accent); color: #000;
}
.setup-btn.primary:hover {
  background: #fff; box-shadow: var(--glow);
}
.setup-btn.secondary {
  background: transparent; color: var(--accent);
  border: 1px solid var(--accent);
}
.setup-btn.secondary:hover {
  background: rgba(0,229,255,0.08);
}

.setup-divider {
  display: flex; align-items: center; gap: 16px;
  margin: 20px 0;
  color: var(--text3);
  font-family: var(--mono); font-size: 10px;
}
.setup-divider::before, .setup-divider::after {
  content: ''; flex: 1; height: 1px; background: var(--border);
}

.setup-msg {
  font-family: var(--mono);
  font-size: 11px;
  padding: 10px 14px;
  border-radius: var(--radius);
  margin-bottom: 16px;
  display: none;
}
.setup-msg.error { background: rgba(255,77,109,0.1); border: 1px solid rgba(255,77,109,0.3); color: var(--accent2); }
.setup-msg.success { background: rgba(184,255,90,0.08); border: 1px solid rgba(184,255,90,0.3); color: var(--accent3); }
.setup-msg.show { display: block; }

.setup-toggle {
  font-family: var(--mono); font-size: 11px;
  color: var(--text2); text-align: center; margin-top: 20px;
}
.setup-toggle a {
  color: var(--accent); cursor: pointer; text-decoration: underline;
}

/* FIREBASE CONFIG SECTION */
.config-section {
  border: 1px solid var(--border2);
  border-radius: var(--radius);
  padding: 20px;
  margin-bottom: 24px;
  background: rgba(0,229,255,0.02);
}
.config-title {
  font-family: var(--display);
  font-size: 14px; font-weight: 700;
  letter-spacing: 2px; text-transform: uppercase;
  color: var(--accent); margin-bottom: 6px;
}
.config-desc {
  font-family: var(--mono); font-size: 10px;
  color: var(--text2); line-height: 1.6; margin-bottom: 16px;
}
.config-desc a { color: var(--accent); }
.config-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
.config-field { display: flex; flex-direction: column; gap: 4px; }
.config-field label {
  font-family: var(--mono); font-size: 9px;
  color: var(--text2); letter-spacing: 2px; text-transform: uppercase;
}

/* DEMO MODE */
.demo-btn {
  width: 100%;
  background: rgba(184,255,90,0.06);
  border: 1px dashed rgba(184,255,90,0.4);
  color: var(--accent3);
  font-family: var(--display); font-size: 15px; font-weight: 700;
  letter-spacing: 2px; text-transform: uppercase;
  padding: 12px; border-radius: var(--radius);
  cursor: pointer; transition: all 0.2s;
}
.demo-btn:hover { background: rgba(184,255,90,0.12); }

/* ─── MAIN APP ─────────────────────────────────────────── */
#app { display: none; min-height: 100vh; flex-direction: column; }
#app.visible { display: flex; }

/* TOPBAR */
.topbar {
  height: 56px;
  background: var(--surface);
  border-bottom: 1px solid var(--border);
  display: flex; align-items: center;
  padding: 0 24px;
  gap: 16px;
  position: sticky; top: 0; z-index: 100;
}

.topbar-logo {
  font-family: var(--display);
  font-size: 26px; font-weight: 900;
  letter-spacing: 5px;
  color: var(--white);
  text-transform: uppercase;
}
.topbar-logo span { color: var(--accent); }

.topbar-spacer { flex: 1; }

.topbar-user {
  display: flex; align-items: center; gap: 10px;
  font-family: var(--mono); font-size: 11px; color: var(--text2);
}
.user-avatar {
  width: 28px; height: 28px;
  background: linear-gradient(135deg, var(--accent), #0070ff);
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: var(--display); font-size: 13px; font-weight: 700;
  color: #000;
}

.topbar-btn {
  background: transparent;
  border: 1px solid var(--border2);
  color: var(--text2);
  padding: 6px 14px;
  border-radius: var(--radius);
  font-family: var(--mono); font-size: 10px;
  letter-spacing: 1px; text-transform: uppercase;
  cursor: pointer; transition: all 0.2s;
}
.topbar-btn:hover { border-color: var(--accent2); color: var(--accent2); }

/* STATS BAR */
.statsbar {
  background: var(--surface2);
  border-bottom: 1px solid var(--border);
  padding: 10px 24px;
  display: flex; gap: 32px; align-items: center;
}
.stat-item { display: flex; align-items: center; gap: 10px; }
.stat-label {
  font-family: var(--mono); font-size: 9px;
  color: var(--text3); letter-spacing: 2px; text-transform: uppercase;
}
.stat-value {
  font-family: var(--display); font-size: 18px; font-weight: 700;
  color: var(--white);
}
.stat-unit {
  font-family: var(--mono); font-size: 9px; color: var(--accent);
}
.stat-divider { width: 1px; height: 28px; background: var(--border); }

/* STORAGE BAR */
.storage-bar-wrap { flex: 1; max-width: 300px; }
.storage-bar-labels {
  display: flex; justify-content: space-between;
  font-family: var(--mono); font-size: 9px;
  color: var(--text3); margin-bottom: 5px;
}
.storage-bar-track {
  height: 4px; background: var(--border2); border-radius: 2px; overflow: hidden;
}
.storage-bar-fill {
  height: 100%; background: linear-gradient(90deg, var(--accent), #0070ff);
  border-radius: 2px;
  transition: width 0.6s ease;
}

/* TOOLBAR */
.toolbar {
  padding: 14px 24px;
  display: flex; align-items: center; gap: 12px;
  flex-wrap: wrap;
}

.path-breadcrumb {
  font-family: var(--mono); font-size: 11px;
  color: var(--text2);
  display: flex; align-items: center; gap: 6px;
}
.path-breadcrumb span { color: var(--text3); }
.path-current { color: var(--accent); }

.toolbar-sep { flex: 1; }

.search-wrap {
  position: relative;
  display: flex; align-items: center;
}
.search-input {
  background: var(--surface2);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 7px 14px 7px 34px;
  color: var(--text);
  font-family: var(--mono); font-size: 11px;
  width: 220px; outline: none;
  transition: border-color 0.2s;
}
.search-input:focus { border-color: var(--accent); }
.search-input::placeholder { color: var(--text3); }
.search-icon {
  position: absolute; left: 10px;
  color: var(--text3); font-size: 13px; pointer-events: none;
}

.view-toggle { display: flex; gap: 2px; }
.view-btn {
  background: transparent; border: 1px solid var(--border);
  color: var(--text3); width: 32px; height: 32px;
  display: flex; align-items: center; justify-content: center;
  cursor: pointer; font-size: 14px; transition: all 0.2s;
  border-radius: var(--radius);
}
.view-btn.active { background: var(--surface2); border-color: var(--accent); color: var(--accent); }
.view-btn:hover:not(.active) { border-color: var(--border2); color: var(--text); }

.action-btn {
  display: flex; align-items: center; gap: 6px;
  background: var(--accent); color: #000;
  border: none; border-radius: var(--radius);
  padding: 8px 16px;
  font-family: var(--display); font-size: 13px; font-weight: 700;
  letter-spacing: 1px; text-transform: uppercase;
  cursor: pointer; transition: all 0.2s;
  white-space: nowrap;
}
.action-btn:hover { background: #fff; box-shadow: var(--glow); }
.action-btn.danger {
  background: transparent; border: 1px solid var(--accent2);
  color: var(--accent2);
}
.action-btn.danger:hover { background: rgba(255,77,109,0.1); box-shadow: var(--glow2); }

/* MAIN CONTENT */
.main {
  flex: 1;
  padding: 0 24px 24px;
  overflow-y: auto;
}

/* DROP ZONE */
.drop-zone {
  border: 2px dashed var(--border2);
  border-radius: 2px;
  padding: 32px;
  text-align: center;
  margin-bottom: 24px;
  transition: all 0.3s;
  cursor: pointer;
  position: relative; overflow: hidden;
}
.drop-zone.dragging {
  border-color: var(--accent);
  background: rgba(0,229,255,0.04);
  box-shadow: var(--glow);
}
.drop-zone-icon {
  font-size: 36px; margin-bottom: 12px;
  display: block; opacity: 0.5;
}
.drop-zone-title {
  font-family: var(--display); font-size: 18px; font-weight: 600;
  letter-spacing: 2px; text-transform: uppercase;
  color: var(--text); margin-bottom: 4px;
}
.drop-zone-sub {
  font-family: var(--mono); font-size: 10px;
  color: var(--text3); letter-spacing: 1px;
}
#file-input { display: none; }

/* UPLOAD PROGRESS */
.upload-queue {
  display: flex; flex-direction: column; gap: 8px;
  margin-bottom: 20px;
}
.upload-item {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 12px 16px;
  display: flex; align-items: center; gap: 12px;
  animation: slideIn 0.3s ease;
}
@keyframes slideIn {
  from { opacity: 0; transform: translateY(-8px); }
  to { opacity: 1; transform: translateY(0); }
}
.upload-item-name {
  font-family: var(--mono); font-size: 11px; color: var(--text);
  flex: 1; overflow: hidden; text-overflow: ellipsis; white-space: nowrap;
}
.upload-item-size {
  font-family: var(--mono); font-size: 10px; color: var(--text3);
}
.upload-progress-wrap {
  width: 120px; height: 3px;
  background: var(--border); border-radius: 2px; overflow: hidden;
}
.upload-progress-bar {
  height: 100%; background: var(--accent);
  border-radius: 2px; transition: width 0.3s;
}
.upload-status {
  font-family: var(--mono); font-size: 10px;
  color: var(--accent); min-width: 36px; text-align: right;
}
.upload-status.done { color: var(--accent3); }
.upload-status.error { color: var(--accent2); }

/* FILE GRID */
.file-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 12px;
}
.file-grid.list-view {
  grid-template-columns: 1fr;
  gap: 4px;
}

.file-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 20px 16px 16px;
  cursor: pointer;
  transition: all 0.2s;
  position: relative;
  overflow: hidden;
  animation: fadeUp 0.3s ease both;
  display: flex; flex-direction: column; align-items: center; gap: 10px;
}
.file-card:hover {
  border-color: var(--accent);
  background: var(--surface2);
  transform: translateY(-2px);
  box-shadow: var(--glow);
}
.file-card.selected {
  border-color: var(--accent);
  background: rgba(0,229,255,0.05);
}

.file-grid.list-view .file-card {
  flex-direction: row; padding: 10px 16px;
  gap: 14px; align-items: center;
}
.file-grid.list-view .file-card:hover { transform: none; }

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

.file-icon {
  font-size: 36px; line-height: 1;
  filter: drop-shadow(0 0 8px rgba(0,229,255,0.2));
}
.file-grid.list-view .file-icon { font-size: 22px; }

.file-name {
  font-family: var(--mono); font-size: 10px;
  color: var(--text); text-align: center;
  word-break: break-all;
  line-height: 1.4;
  max-width: 100%;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
.file-grid.list-view .file-name {
  text-align: left; flex: 1;
  -webkit-line-clamp: 1;
}

.file-meta {
  font-family: var(--mono); font-size: 9px;
  color: var(--text3); text-align: center;
  display: flex; flex-direction: column; gap: 2px;
}
.file-grid.list-view .file-meta {
  flex-direction: row; gap: 16px; text-align: right;
}

.file-actions {
  position: absolute; top: 6px; right: 6px;
  display: flex; gap: 4px; opacity: 0;
  transition: opacity 0.2s;
}
.file-card:hover .file-actions { opacity: 1; }

.file-grid.list-view .file-actions { position: static; opacity: 1; }

.file-action-btn {
  width: 24px; height: 24px;
  background: var(--surface2); border: 1px solid var(--border2);
  border-radius: 2px;
  display: flex; align-items: center; justify-content: center;
  cursor: pointer; font-size: 11px;
  transition: all 0.15s; color: var(--text2);
}
.file-action-btn:hover { border-color: var(--accent); color: var(--accent); }
.file-action-btn.del:hover { border-color: var(--accent2); color: var(--accent2); }

/* EMPTY STATE */
.empty-state {
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  padding: 80px 20px; color: var(--text3);
  gap: 12px;
}
.empty-icon { font-size: 48px; opacity: 0.3; }
.empty-title {
  font-family: var(--display); font-size: 20px; font-weight: 600;
  letter-spacing: 3px; text-transform: uppercase; color: var(--text2);
}
.empty-sub { font-family: var(--mono); font-size: 11px; color: var(--text3); }

/* SECTION HEADER */
.section-header {
  display: flex; align-items: center; gap: 12px;
  margin-bottom: 16px;
}
.section-title {
  font-family: var(--display); font-size: 13px; font-weight: 700;
  letter-spacing: 3px; text-transform: uppercase; color: var(--text2);
}
.section-line { flex: 1; height: 1px; background: var(--border); }
.section-count {
  font-family: var(--mono); font-size: 10px;
  color: var(--text3); letter-spacing: 1px;
}

/* MODAL */
.modal-overlay {
  position: fixed; inset: 0;
  background: rgba(0,0,0,0.7);
  backdrop-filter: blur(4px);
  display: flex; align-items: center; justify-content: center;
  z-index: 500; opacity: 0; pointer-events: none;
  transition: opacity 0.2s;
}
.modal-overlay.show { opacity: 1; pointer-events: all; }

.modal {
  background: var(--surface);
  border: 1px solid var(--border2);
  border-radius: 2px;
  padding: 32px;
  width: 100%; max-width: 420px;
  position: relative;
  transform: translateY(10px);
  transition: transform 0.2s;
}
.modal-overlay.show .modal { transform: translateY(0); }
.modal::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 2px;
  background: linear-gradient(90deg, transparent, var(--accent2), transparent);
}
.modal-title {
  font-family: var(--display); font-size: 22px; font-weight: 700;
  letter-spacing: 3px; text-transform: uppercase;
  color: var(--white); margin-bottom: 16px;
}
.modal-text {
  font-family: var(--mono); font-size: 11px;
  color: var(--text2); line-height: 1.6; margin-bottom: 24px;
}
.modal-actions { display: flex; gap: 10px; justify-content: flex-end; }
.modal-cancel {
  background: transparent; border: 1px solid var(--border2);
  color: var(--text2); padding: 8px 20px; border-radius: var(--radius);
  font-family: var(--mono); font-size: 11px; cursor: pointer; transition: all 0.2s;
}
.modal-cancel:hover { border-color: var(--text); color: var(--text); }
.modal-confirm {
  background: var(--accent2); color: white; border: none;
  padding: 8px 20px; border-radius: var(--radius);
  font-family: var(--display); font-size: 14px; font-weight: 700;
  letter-spacing: 2px; cursor: pointer; transition: all 0.2s;
  text-transform: uppercase;
}
.modal-confirm:hover { box-shadow: var(--glow2); }

/* TOAST */
.toast-container {
  position: fixed; bottom: 24px; right: 24px;
  display: flex; flex-direction: column; gap: 8px;
  z-index: 9998;
}
.toast {
  background: var(--surface2);
  border: 1px solid var(--border2);
  border-radius: var(--radius);
  padding: 12px 18px;
  font-family: var(--mono); font-size: 11px;
  color: var(--text);
  display: flex; align-items: center; gap: 10px;
  min-width: 260px;
  animation: toastIn 0.3s ease;
  box-shadow: 0 4px 24px rgba(0,0,0,0.4);
}
.toast.success { border-left: 3px solid var(--accent3); }
.toast.error { border-left: 3px solid var(--accent2); }
.toast.info { border-left: 3px solid var(--accent); }
@keyframes toastIn {
  from { opacity: 0; transform: translateX(20px); }
  to { opacity: 1; transform: translateX(0); }
}

/* LOADING SPINNER */
.spinner {
  display: inline-block; width: 16px; height: 16px;
  border: 2px solid rgba(0,229,255,0.2);
  border-top-color: var(--accent);
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }

/* WATERMARK */
.watermark {
  position: fixed; bottom: 12px; left: 50%; transform: translateX(-50%);
  font-family: var(--mono); font-size: 9px;
  color: var(--text3); letter-spacing: 2px; pointer-events: none;
  z-index: 1;
}

/* RESPONSIVE */
@media (max-width: 640px) {
  .statsbar { flex-wrap: wrap; gap: 12px; padding: 12px 16px; }
  .storage-bar-wrap { flex: 1 0 100%; max-width: 100%; }
  .file-grid { grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); }
  .config-grid { grid-template-columns: 1fr; }
  .topbar { padding: 0 16px; }
  .main { padding: 0 16px 16px; }
}
</style>
</head>
<body>

<!-- ══════════════════════════════════════════════════════ -->
<!--  SETUP / AUTH SCREEN                                   -->
<!-- ══════════════════════════════════════════════════════ -->
<div id="setup-screen">
  <!-- AUTH FORM — shown immediately since Firebase is pre-configured -->
  <div class="setup-box" style="margin-bottom:0;">
    <div class="setup-logo">V<span>AU</span>LT</div>
    <div class="setup-sub">Cloud File Manager — Powered by Firebase</div>
    <!-- Firebase status badge -->
    <div id="firebase-status" style="
      display:flex; align-items:center; gap:8px;
      background:rgba(0,229,255,0.06); border:1px solid rgba(0,229,255,0.2);
      border-radius:4px; padding:8px 14px; margin-bottom:24px;
      font-family:var(--mono); font-size:10px; color:var(--accent); letter-spacing:1px;">
      <span id="fb-dot" style="width:7px;height:7px;border-radius:50%;background:var(--text3);display:inline-block;"></span>
      <span id="fb-status-text">Connecting to Firebase…</span>
    </div>
  </div>

  <div class="setup-box" id="auth-form" style="display:none; margin-top:12px;"></div>
</div>

<!-- ══════════════════════════════════════════════════════ -->
<!--  MAIN APP                                              -->
<!-- ══════════════════════════════════════════════════════ -->
<div id="app">
  <!-- TOPBAR -->
  <header class="topbar">
    <div class="topbar-logo">V<span>AU</span>LT</div>
    <div class="topbar-spacer"></div>
    <div class="topbar-user">
      <div class="user-avatar" id="user-avatar">?</div>
      <span id="user-display-name">User</span>
    </div>
    <button class="topbar-btn" onclick="handleSignOut()">⏻ Sign Out</button>
  </header>

  <!-- STATS BAR -->
  <div class="statsbar">
    <div class="stat-item">
      <div>
        <div class="stat-label">Files</div>
        <div><span class="stat-value" id="stat-files">0</span> <span class="stat-unit">items</span></div>
      </div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-item">
      <div>
        <div class="stat-label">Used Space</div>
        <div><span class="stat-value" id="stat-used">0</span> <span class="stat-unit" id="stat-unit">KB</span></div>
      </div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-item">
      <div>
        <div class="stat-label">Storage</div>
        <div><span class="stat-value" id="stat-provider">—</span></div>
      </div>
    </div>
    <div class="stat-divider"></div>
    <div class="storage-bar-wrap">
      <div class="storage-bar-labels">
        <span>Storage Usage</span>
        <span id="storage-pct">0%</span>
      </div>
      <div class="storage-bar-track">
        <div class="storage-bar-fill" id="storage-bar" style="width:0%"></div>
      </div>
    </div>
  </div>

  <!-- TOOLBAR -->
  <div class="toolbar">
    <div class="path-breadcrumb">
      <span>◈</span>
      <span>My Vault</span>
      <span>/</span>
      <span class="path-current">All Files</span>
    </div>
    <div class="toolbar-sep"></div>
    <div class="search-wrap">
      <span class="search-icon">⌕</span>
      <input class="search-input" id="search-input" placeholder="Search files..." oninput="filterFiles(this.value)"/>
    </div>
    <div class="view-toggle">
      <button class="view-btn active" id="btn-grid" onclick="setView('grid')" title="Grid">⊞</button>
      <button class="view-btn" id="btn-list" onclick="setView('list')" title="List">≡</button>
    </div>
    <button class="action-btn" onclick="document.getElementById('file-input').click()">
      ↑ Upload Files
    </button>
    <input type="file" id="file-input" multiple onchange="handleFileSelect(this.files)"/>
  </div>

  <!-- MAIN CONTENT -->
  <main class="main">
    <!-- UPLOAD QUEUE -->
    <div class="upload-queue" id="upload-queue"></div>

    <!-- DROP ZONE -->
    <div class="drop-zone" id="drop-zone"
         onclick="document.getElementById('file-input').click()"
         ondragover="handleDragOver(event)"
         ondragleave="handleDragLeave(event)"
         ondrop="handleDrop(event)">
      <span class="drop-zone-icon">⬇</span>
      <div class="drop-zone-title">Drop Files Here</div>
      <div class="drop-zone-sub">or click to browse — any file type accepted</div>
    </div>

    <!-- FILES -->
    <div class="section-header">
      <div class="section-title">Files</div>
      <div class="section-line"></div>
      <div class="section-count" id="file-count">0 files</div>
    </div>

    <div class="file-grid" id="file-grid"></div>
  </main>
</div>

<!-- DELETE MODAL -->
<div class="modal-overlay" id="delete-modal">
  <div class="modal">
    <div class="modal-title">Delete File</div>
    <div class="modal-text" id="modal-text">Are you sure you want to permanently delete this file? This action cannot be undone.</div>
    <div class="modal-actions">
      <button class="modal-cancel" onclick="closeModal()">Cancel</button>
      <button class="modal-confirm" onclick="confirmDelete()">Delete</button>
    </div>
  </div>
</div>

<!-- TOAST CONTAINER -->
<div class="toast-container" id="toast-container"></div>

<!-- WATERMARK -->
<div class="watermark">VAULT — CLOUD FILE MANAGER</div>

<!-- ══════════════════════════════════════════════════════ -->
<!--  JAVASCRIPT                                            -->
<!-- ══════════════════════════════════════════════════════ -->
<script>
// ─── STATE ────────────────────────────────────────────────
let STATE = {
  mode: null,         // 'firebase' | 'demo'
  user: null,
  files: [],          // { id, name, size, type, url, uploadedAt, storagePath }
  filteredFiles: [],
  view: 'grid',
  deleteTarget: null,
  firebaseApp: null,
  auth: null,
  storage: null,
  db: null,
  DEMO_LIMIT_MB: 50
};

const FIREBASE_STORAGE_LIMIT_MB = 1024; // Firebase free tier: 5 GB, showing 1 GB

// ─── FIREBASE CONFIG (pre-configured) ────────────────────
const FIREBASE_CONFIG = {
  apiKey:            "AIzaSyBfqxhP_lmL5x5k8jEB8ijPouFDM2KE94o",
  authDomain:        "project-f66d8.firebaseapp.com",
  projectId:         "project-f66d8",
  storageBucket:     "project-f66d8.firebasestorage.app",
  messagingSenderId: "646077418570",
  appId:             "1:646077418570:web:f637be8dca8b05cb0deab3",
  measurementId:     "G-XVVR61K2RR"
};

// ─── AUTO FIREBASE INIT on page load ─────────────────────
function setFirebaseStatus(ok, msg) {
  const dot  = document.getElementById('fb-dot');
  const text = document.getElementById('fb-status-text');
  if (!dot || !text) return;
  dot.style.background  = ok ? 'var(--accent3)' : 'var(--accent2)';
  text.textContent = msg;
  const wrap = document.getElementById('firebase-status');
  if (wrap) {
    wrap.style.borderColor = ok ? 'rgba(184,255,90,0.3)' : 'rgba(255,77,109,0.3)';
    wrap.style.background  = ok ? 'rgba(184,255,90,0.06)' : 'rgba(255,77,109,0.06)';
    wrap.style.color       = ok ? 'var(--accent3)' : 'var(--accent2)';
    dot.style.boxShadow    = ok ? '0 0 6px var(--accent3)' : '0 0 6px var(--accent2)';
  }
}

function initFirebase() {
  try {
    if (firebase.apps.length) firebase.app().delete();
    STATE.firebaseApp = firebase.initializeApp(FIREBASE_CONFIG);
    STATE.auth    = firebase.auth();
    STATE.storage = firebase.storage();
    STATE.db      = firebase.firestore();
    STATE.mode    = 'firebase';

    setFirebaseStatus(true, '● project-f66d8 — Connected');
    document.getElementById('stat-provider').textContent = 'Firebase';

    // Auth state listener — shows login form or goes straight to app
    STATE.auth.onAuthStateChanged(user => {
      if (user) {
        onUserSignedIn(user);
      } else {
        showAuthForm();
      }
    });
  } catch(e) {
    setFirebaseStatus(false, '✕ Connection failed: ' + e.message);
    showToast('Firebase error: ' + e.message, 'error');
    // Fallback to demo mode automatically
    startDemoMode();
  }
}

// ─── DEMO MODE ────────────────────────────────────────────
function startDemoMode() {
  STATE.mode = 'demo';
  document.getElementById('auth-form').style.display = 'block';
  document.getElementById('stat-provider').textContent = 'Local Demo';
  setFirebaseStatus(false, '◈ Running in Demo Mode (local storage)');
}

// ─── AUTH HANDLERS ────────────────────────────────────────
async function handleLogin() {
  if (STATE.mode === 'demo') {
    const email = document.getElementById('login-email').value.trim();
    if (!email) { showMsg('Enter an email address', 'error'); return; }
    const name = email.split('@')[0];
    onUserSignedIn({ uid: 'demo-' + Date.now(), email, displayName: name });
    return;
  }
  const email = document.getElementById('login-email').value.trim();
  const pass  = document.getElementById('login-pass').value;
  if (!email || !pass) { showMsg('Fill in email and password', 'error'); return; }
  try {
    await STATE.auth.signInWithEmailAndPassword(email, pass);
  } catch(e) { showMsg(e.message, 'error'); }
}

async function handleGuestLogin() {
  if (STATE.mode === 'demo') {
    onUserSignedIn({ uid: 'guest-' + Date.now(), email: 'guest@vault.app', displayName: 'Guest' });
    return;
  }
  try {
    await STATE.auth.signInAnonymously();
  } catch(e) { showMsg(e.message, 'error'); }
}

async function handleRegister() {
  if (STATE.mode === 'demo') {
    showMsg('In demo mode, just sign in with any email', 'info'); return;
  }
  const name  = document.getElementById('reg-name').value.trim();
  const email = document.getElementById('reg-email').value.trim();
  const pass  = document.getElementById('reg-pass').value;
  if (!name || !email || !pass) { showMsg('Fill in all fields', 'error'); return; }
  try {
    const cred = await STATE.auth.createUserWithEmailAndPassword(email, pass);
    await cred.user.updateProfile({ displayName: name });
    await onUserSignedIn(cred.user);
  } catch(e) { showMsg(e.message, 'error'); }
}

async function handleSignOut() {
  if (STATE.mode === 'firebase' && STATE.auth) await STATE.auth.signOut();
  STATE.user = null; STATE.files = []; STATE.filteredFiles = [];
  document.getElementById('app').classList.remove('visible');
  showAuthForm();
}

function switchToRegister() {
  document.getElementById('login-view').style.display = 'none';
  document.getElementById('register-view').style.display = 'block';
}
function switchToLogin() {
  document.getElementById('register-view').style.display = 'none';
  document.getElementById('login-view').style.display = 'block';
}

// ─── ON USER SIGNED IN ────────────────────────────────────
async function onUserSignedIn(user) {
  STATE.user = user;
  const name = user.displayName || user.email?.split('@')[0] || 'User';
  document.getElementById('user-display-name').textContent = name;
  document.getElementById('user-avatar').textContent = name.charAt(0).toUpperCase();
  document.getElementById('setup-screen').classList.add('hidden');
  document.getElementById('app').classList.add('visible');

  if (STATE.mode === 'firebase') {
    await loadFilesFromFirestore();
  } else {
    STATE.files = JSON.parse(localStorage.getItem('vault_files_' + user.uid) || '[]');
    renderFiles();
    updateStats();
  }
  showToast('Welcome back, ' + name + '!', 'success');
}

function showAuthForm() {
  const authForm = document.getElementById('auth-form');
  authForm.style.display = 'block';
  authForm.innerHTML = `
    <div id="setup-msg" class="setup-msg"></div>
    <div id="login-view">
      <div class="setup-logo" style="font-size:32px;margin-bottom:4px;">Welcome Back</div>
      <div class="setup-sub" style="margin-bottom:24px;">Sign in to your vault</div>
      <label class="setup-label">Email Address</label>
      <input class="setup-input" id="login-email" type="email" placeholder="you@example.com"/>
      <label class="setup-label">Password</label>
      <input class="setup-input" id="login-pass" type="password" placeholder="••••••••"/>
      <div class="setup-row">
        <button class="setup-btn primary" onclick="handleLogin()">Sign In</button>
        <button class="setup-btn secondary" onclick="handleGuestLogin()">Guest</button>
      </div>
      <div class="setup-toggle">No account? <a onclick="switchToRegister()">Create one</a></div>
    </div>
    <div id="register-view" style="display:none;">
      <div class="setup-logo" style="font-size:32px;margin-bottom:4px;">Create Account</div>
      <div class="setup-sub" style="margin-bottom:24px;">Join the vault</div>
      <label class="setup-label">Display Name</label>
      <input class="setup-input" id="reg-name" type="text" placeholder="Your Name"/>
      <label class="setup-label">Email Address</label>
      <input class="setup-input" id="reg-email" type="email" placeholder="you@example.com"/>
      <label class="setup-label">Password</label>
      <input class="setup-input" id="reg-pass" type="password" placeholder="Min 6 characters"/>
      <div class="setup-row">
        <button class="setup-btn primary" onclick="handleRegister()">Create Account</button>
      </div>
      <div class="setup-toggle">Already have an account? <a onclick="switchToLogin()">Sign in</a></div>
    </div>`;
  document.getElementById('setup-screen').classList.remove('hidden');
  document.getElementById('app').classList.remove('visible');
}

// ─── AUTO-INIT FIREBASE ON PAGE LOAD ─────────────────────
document.addEventListener('DOMContentLoaded', () => {
  initFirebase();
});

// ─── FIRESTORE FILE METADATA ──────────────────────────────
async function loadFilesFromFirestore() {
  try {
    const snap = await STATE.db.collection('users').doc(STATE.user.uid)
                               .collection('files').orderBy('uploadedAt', 'desc').get();
    STATE.files = snap.docs.map(d => ({ id: d.id, ...d.data() }));
    renderFiles(); updateStats();
  } catch(e) {
    // Fallback if Firestore rules not set up
    STATE.files = JSON.parse(localStorage.getItem('vault_files_' + STATE.user.uid) || '[]');
    renderFiles(); updateStats();
  }
}

function saveFilesLocally() {
  if (STATE.mode === 'demo' || !STATE.db) {
    localStorage.setItem('vault_files_' + STATE.user.uid, JSON.stringify(STATE.files));
  }
}

// ─── FILE UPLOAD ──────────────────────────────────────────
function handleFileSelect(files) { uploadFiles(Array.from(files)); }

function handleDragOver(e) {
  e.preventDefault();
  document.getElementById('drop-zone').classList.add('dragging');
}
function handleDragLeave(e) {
  document.getElementById('drop-zone').classList.remove('dragging');
}
function handleDrop(e) {
  e.preventDefault();
  document.getElementById('drop-zone').classList.remove('dragging');
  const files = Array.from(e.dataTransfer.files);
  if (files.length) uploadFiles(files);
}

async function uploadFiles(files) {
  for (const file of files) {
    await uploadSingleFile(file);
  }
}

async function uploadSingleFile(file) {
  const id = 'f_' + Date.now() + '_' + Math.random().toString(36).slice(2);
  const queueEl = addToUploadQueue(id, file.name, file.size);

  if (STATE.mode === 'demo') {
    // Simulate upload with local object URL
    let progress = 0;
    await new Promise(res => {
      const iv = setInterval(() => {
        progress = Math.min(progress + Math.random() * 25, 100);
        updateQueueItem(id, progress);
        if (progress >= 100) { clearInterval(iv); res(); }
      }, 120);
    });
    const url = URL.createObjectURL(file);
    const record = { id, name: file.name, size: file.size, type: file.type, url, uploadedAt: new Date().toISOString(), storagePath: null };
    STATE.files.unshift(record);
    saveFilesLocally();
    markQueueDone(id);
    renderFiles(); updateStats();
    showToast(file.name + ' uploaded', 'success');
  } else {
    // Firebase Storage upload
    const path = `users/${STATE.user.uid}/files/${id}_${file.name}`;
    const ref  = STATE.storage.ref(path);
    const task = ref.put(file);

    task.on('state_changed',
      snap => {
        const pct = (snap.bytesTransferred / snap.totalBytes) * 100;
        updateQueueItem(id, pct);
      },
      err => {
        markQueueError(id);
        showToast('Upload failed: ' + err.message, 'error');
      },
      async () => {
        const url = await task.snapshot.ref.getDownloadURL();
        const record = { id, name: file.name, size: file.size, type: file.type, url, uploadedAt: new Date().toISOString(), storagePath: path };

        // Save to Firestore (best effort)
        try {
          await STATE.db.collection('users').doc(STATE.user.uid).collection('files').doc(id).set(record);
        } catch {
          localStorage.setItem('vault_files_' + STATE.user.uid, JSON.stringify([record, ...STATE.files]));
        }

        STATE.files.unshift(record);
        markQueueDone(id);
        renderFiles(); updateStats();
        showToast(file.name + ' uploaded', 'success');
      }
    );
  }
}

// ─── UPLOAD QUEUE UI ──────────────────────────────────────
function addToUploadQueue(id, name, size) {
  const q = document.getElementById('upload-queue');
  const el = document.createElement('div');
  el.className = 'upload-item';
  el.id = 'qi_' + id;
  el.innerHTML = `
    <span style="font-size:18px;">${fileIcon({type:'application/octet-stream',name})}</span>
    <span class="upload-item-name">${escHtml(name)}</span>
    <span class="upload-item-size">${formatSize(size)}</span>
    <div class="upload-progress-wrap"><div class="upload-progress-bar" id="pb_${id}" style="width:0%"></div></div>
    <span class="upload-status" id="ps_${id}">0%</span>
  `;
  q.appendChild(el);
  return el;
}
function updateQueueItem(id, pct) {
  const bar = document.getElementById('pb_' + id);
  const stat = document.getElementById('ps_' + id);
  if (bar) bar.style.width = pct + '%';
  if (stat) stat.textContent = Math.round(pct) + '%';
}
function markQueueDone(id) {
  const stat = document.getElementById('ps_' + id);
  if (stat) { stat.textContent = '✓'; stat.className = 'upload-status done'; }
  setTimeout(() => {
    const el = document.getElementById('qi_' + id);
    if (el) el.remove();
  }, 1800);
}
function markQueueError(id) {
  const stat = document.getElementById('ps_' + id);
  if (stat) { stat.textContent = '✗'; stat.className = 'upload-status error'; }
}

// ─── DELETE FILE ──────────────────────────────────────────
function requestDelete(id, name) {
  STATE.deleteTarget = id;
  document.getElementById('modal-text').textContent = `Permanently delete "${name}"? This cannot be undone.`;
  document.getElementById('delete-modal').classList.add('show');
}
function closeModal() {
  document.getElementById('delete-modal').classList.remove('show');
  STATE.deleteTarget = null;
}
async function confirmDelete() {
  const id = STATE.deleteTarget;
  if (!id) return;
  const file = STATE.files.find(f => f.id === id);
  if (!file) { closeModal(); return; }

  if (STATE.mode === 'firebase' && file.storagePath) {
    try { await STATE.storage.ref(file.storagePath).delete(); } catch {}
    try { await STATE.db.collection('users').doc(STATE.user.uid).collection('files').doc(id).delete(); } catch {}
  }

  STATE.files = STATE.files.filter(f => f.id !== id);
  saveFilesLocally();
  renderFiles(); updateStats();
  closeModal();
  showToast(file.name + ' deleted', 'info');
}

// ─── DOWNLOAD FILE ────────────────────────────────────────
function downloadFile(file) {
  const a = document.createElement('a');
  a.href = file.url;
  a.download = file.name;
  a.target = '_blank';
  document.body.appendChild(a); a.click(); document.body.removeChild(a);
  showToast('Downloading ' + file.name, 'info');
}

// ─── RENDER FILES ─────────────────────────────────────────
function renderFiles(list) {
  const files = list || STATE.files;
  const grid = document.getElementById('file-grid');
  const count = document.getElementById('file-count');
  count.textContent = files.length + ' file' + (files.length !== 1 ? 's' : '');

  if (!files.length) {
    grid.innerHTML = `
      <div class="empty-state" style="grid-column:1/-1">
        <div class="empty-icon">◈</div>
        <div class="empty-title">No Files Yet</div>
        <div class="empty-sub">Upload files using the drop zone above</div>
      </div>`;
    return;
  }

  const viewClass = STATE.view === 'list' ? 'file-grid list-view' : 'file-grid';
  grid.className = viewClass;

  grid.innerHTML = files.map((f, i) => `
    <div class="file-card" style="animation-delay:${i*30}ms">
      <span class="file-icon">${fileIcon(f)}</span>
      <span class="file-name" title="${escHtml(f.name)}">${escHtml(f.name)}</span>
      <div class="file-meta">
        <span>${formatSize(f.size)}</span>
        <span>${formatDate(f.uploadedAt)}</span>
      </div>
      <div class="file-actions">
        <button class="file-action-btn" onclick="downloadFile(STATE.files.find(x=>x.id==='${f.id}'))" title="Download">↓</button>
        <button class="file-action-btn del" onclick="requestDelete('${f.id}','${escAttr(f.name)}')" title="Delete">✕</button>
      </div>
    </div>
  `).join('');
}

function filterFiles(q) {
  const lower = q.toLowerCase();
  const filtered = STATE.files.filter(f => f.name.toLowerCase().includes(lower));
  renderFiles(filtered);
}

function setView(v) {
  STATE.view = v;
  document.getElementById('btn-grid').classList.toggle('active', v === 'grid');
  document.getElementById('btn-list').classList.toggle('active', v === 'list');
  renderFiles();
}

// ─── STATS ────────────────────────────────────────────────
function updateStats() {
  const totalBytes = STATE.files.reduce((s, f) => s + (f.size || 0), 0);
  document.getElementById('stat-files').textContent = STATE.files.length;

  let used, unit;
  if (totalBytes < 1024 * 1024) {
    used = (totalBytes / 1024).toFixed(1); unit = 'KB';
  } else if (totalBytes < 1024 * 1024 * 1024) {
    used = (totalBytes / (1024*1024)).toFixed(2); unit = 'MB';
  } else {
    used = (totalBytes / (1024*1024*1024)).toFixed(2); unit = 'GB';
  }
  document.getElementById('stat-used').textContent = used;
  document.getElementById('stat-unit').textContent = unit;

  const limitMB = STATE.mode === 'firebase' ? FIREBASE_STORAGE_LIMIT_MB : STATE.DEMO_LIMIT_MB;
  const usedMB  = totalBytes / (1024*1024);
  const pct     = Math.min((usedMB / limitMB) * 100, 100).toFixed(1);
  document.getElementById('storage-bar').style.width = pct + '%';
  document.getElementById('storage-pct').textContent = pct + '%';
}

// ─── HELPERS ──────────────────────────────────────────────
function fileIcon(f) {
  const n = (f.name || '').toLowerCase();
  const t = (f.type || '').toLowerCase();
  if (t.startsWith('image/') || /\.(png|jpg|jpeg|gif|svg|webp|bmp|ico)$/.test(n)) return '🖼';
  if (t.startsWith('video/') || /\.(mp4|mov|avi|mkv|webm)$/.test(n))              return '🎬';
  if (t.startsWith('audio/') || /\.(mp3|wav|ogg|flac|aac)$/.test(n))              return '🎵';
  if (/\.(pdf)$/.test(n))                                                          return '📄';
  if (/\.(doc|docx)$/.test(n))                                                     return '📝';
  if (/\.(xls|xlsx|csv)$/.test(n))                                                 return '📊';
  if (/\.(ppt|pptx)$/.test(n))                                                     return '📋';
  if (/\.(zip|tar|gz|rar|7z)$/.test(n))                                            return '🗜';
  if (/\.(js|ts|jsx|tsx|html|css|json|py|java|cpp|c|go|rs|php)$/.test(n))        return '💾';
  if (/\.(txt|md|log)$/.test(n))                                                   return '📃';
  return '📁';
}

function formatSize(bytes) {
  if (!bytes) return '—';
  if (bytes < 1024) return bytes + ' B';
  if (bytes < 1024*1024) return (bytes/1024).toFixed(1) + ' KB';
  if (bytes < 1024*1024*1024) return (bytes/(1024*1024)).toFixed(2) + ' MB';
  return (bytes/(1024*1024*1024)).toFixed(2) + ' GB';
}

function formatDate(iso) {
  if (!iso) return '—';
  const d = new Date(iso);
  return d.toLocaleDateString('en-US', { month:'short', day:'numeric', year:'2-digit' });
}

function escHtml(s) {
  return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}
function escAttr(s) {
  return String(s).replace(/'/g,"\\'").replace(/"/g,'&quot;');
}

function showMsg(msg, type) {
  const el = document.getElementById('setup-msg');
  el.textContent = msg; el.className = 'setup-msg ' + type + ' show';
  setTimeout(() => el.classList.remove('show'), 4000);
}

function showToast(msg, type = 'info') {
  const ct = document.getElementById('toast-container');
  const el = document.createElement('div');
  el.className = 'toast ' + type;
  const icon = type === 'success' ? '✓' : type === 'error' ? '✕' : 'ℹ';
  el.innerHTML = `<span style="font-size:14px;">${icon}</span><span>${escHtml(msg)}</span>`;
  ct.appendChild(el);
  setTimeout(() => el.remove(), 3500);
}

// ─── CLOSE MODAL ON OVERLAY CLICK ─────────────────────────
document.getElementById('delete-modal').addEventListener('click', function(e) {
  if (e.target === this) closeModal();
});

// ─── KEYBOARD SHORTCUT ────────────────────────────────────
document.addEventListener('keydown', e => {
  if (e.key === 'Escape') closeModal();
  if ((e.ctrlKey || e.metaKey) && e.key === 'u') {
    e.preventDefault();
    document.getElementById('file-input').click();
  }
});
</script>
</body>
</html>
