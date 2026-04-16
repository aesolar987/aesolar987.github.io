# aesolar987.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AEPS-Electric HSSE Form E</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Times New Roman',Times,serif;font-size:11px;color:#000;background:#f0f2f5}
.page-wrap{max-width:480px;margin:0 auto;padding:10px 8px 40px}

/* UTIL BAR */
.util-bar{background:#fff;border:1px solid #dde1e7;border-radius:10px;padding:14px 18px;margin-bottom:14px;display:flex;align-items:center;gap:12px;flex-wrap:wrap}
.util-bar-left{flex:1;min-width:180px}
.util-bar-left strong{display:block;font-size:13px;font-family:'Segoe UI',Arial,sans-serif;color:#185FA5;margin-bottom:2px}
.util-bar-left span{font-size:11px;color:#6b7280;font-family:'Segoe UI',Arial,sans-serif}
#file-input{display:none}
.btn-upload{background:#185FA5;color:#fff;border:none;border-radius:7px;padding:8px 16px;font-size:13px;font-weight:600;cursor:pointer;font-family:'Segoe UI',Arial,sans-serif;white-space:nowrap}
.btn-upload:hover{background:#0f4a8a}
#loaded-badge{display:none;font-size:12px;color:#15803d;background:#f0fdf4;border:1px solid #bbf7d0;border-radius:20px;padding:3px 12px;font-weight:600;font-family:'Segoe UI',Arial,sans-serif}
.btn-print{background:#fff;color:#185FA5;border:1px solid #BFDBFE;border-radius:7px;padding:8px 16px;font-size:13px;font-weight:600;cursor:pointer;font-family:'Segoe UI',Arial,sans-serif}
.btn-print:hover{background:#EFF6FF}
.btn-submit{background:#15803d;color:#fff;border:none;border-radius:7px;padding:8px 16px;font-size:13px;font-weight:600;cursor:pointer;font-family:'Segoe UI',Arial,sans-serif}
.btn-submit:hover{background:#166534}

/* FORM PAPER */
.form-paper{background:#fff;border:2px solid #000;padding:6px 7px}

/* TITLE */
.form-title-row{text-align:center;margin-bottom:3px}
.form-title-row h1{font-size:14px;font-weight:bold;font-family:'Times New Roman',Times,serif}
.warning-banner{text-align:center;font-size:13px;font-weight:bold;margin:3px 0 5px;letter-spacing:.02em}

/* TABLES */
table.ft{width:100%;border-collapse:collapse;table-layout:fixed}
table.ft td,table.ft th{border:1px solid #000;padding:2px 4px;vertical-align:top;font-size:10.5px}
table.ft input[type=text],table.ft input[type=date],table.ft input[type=email]{
  width:100%;border:none;outline:none;font-size:10px;font-family:'Times New Roman',Times,serif;
  background:transparent;padding:1px 2px;color:#000}
table.ft select{width:100%;border:1px solid #ccc;border-radius:3px;background:#fff;font-size:10px;font-family:'Times New Roman',Times,serif;padding:2px 3px;outline:none;color:#000}
table.ft input[type=checkbox]{width:13px;height:13px;cursor:pointer;accent-color:#185FA5;vertical-align:middle}

/* CREW SIGNATURE ROWS */
.crew-sig-row{display:flex;align-items:stretch;border-bottom:1px dotted #999;padding:2px 0;gap:3px;min-height:48px}
.crew-sig-row:last-child{border-bottom:none}
.crew-name-col{width:48%;display:flex;flex-direction:column;justify-content:flex-end;gap:2px}
.crew-name-col input{border:none;border-bottom:1px solid #ccc;outline:none;font-size:10px;font-family:'Times New Roman',Times,serif;background:transparent;width:100%;padding:1px 2px}
.crew-sig-col{flex:1;position:relative;display:flex;flex-direction:column;justify-content:flex-end}
canvas.crew-canvas{display:block;width:100%;height:46px;cursor:crosshair;touch-action:none;border-bottom:1px solid #ccc}
.crew-clear-btn{position:absolute;top:0;right:0;background:none;border:none;font-size:9px;color:#9ca3af;cursor:pointer;padding:1px 4px;line-height:1}
.crew-clear-btn:hover{color:#cc0000}

/* PERSONNEL SELECTS */
.personnel-sel{width:100%;border:1px solid #ccc;border-radius:3px;background:#fff;font-size:10px;font-family:'Times New Roman',Times,serif;padding:2px;outline:none;color:#000;margin-bottom:2px}
.personnel-phone{font-size:9px;color:#555;margin-top:1px}

/* SECTION HEADER */
.sec-hdr{text-align:center;font-weight:bold;font-size:11px;background:#e8e8e8;padding:3px;border:1px solid #000}

/* JOB SPECIFIC SECTION */
.job-spec-wrap{border:1px solid #000;border-top:none;background:#fff;font-family:'Segoe UI',Arial,sans-serif}
.job-spec-inner{padding:8px 10px}
.js-sec-title{font-size:13px;font-weight:600;color:#1a1a1a;margin-bottom:10px}
.js-label{font-size:11px;color:#6b7280;margin-bottom:5px;display:block;font-weight:500}

/* TASK CHIPS */
.chips-wrap{min-height:32px;margin-bottom:8px;display:flex;flex-wrap:wrap;gap:5px;align-items:center}
.task-chip{display:inline-flex;align-items:center;gap:5px;background:#EFF6FF;border:1px solid #BFDBFE;border-radius:20px;padding:3px 10px;font-size:11px;color:#1e40af;font-weight:500}
.task-chip button{background:none;border:none;cursor:pointer;padding:0;font-size:13px;color:#60a5fa;line-height:1}
.task-chip button:hover{color:#1e40af}
.chips-empty{font-size:11px;color:#9ca3af;font-style:italic}
.task-add-row{display:flex;align-items:center;gap:8px;margin-bottom:4px}
.task-add-row select{flex:1;padding:7px 10px;border:1px solid #d1d5db;border-radius:6px;font-size:12px;font-family:'Segoe UI',Arial,sans-serif;outline:none;color:#1a1a1a;background:#fff}
.task-add-row select:focus{border-color:#185FA5;box-shadow:0 0 0 3px rgba(24,95,165,.1)}

/* HAZARD CARDS */
.task-group-label{font-size:13px;font-weight:700;color:#1a1a1a;letter-spacing:.01em;margin:14px 0 7px;padding:5px 0 5px 0;display:flex;align-items:center;gap:0}.task-group-label-text{flex-shrink:0;padding-right:12px}.task-group-label-line{height:2px;background:#185FA5;width:33%;border-radius:2px;display:inline-block;margin-left:10px;vertical-align:middle}
.hazard-card{display:flex;align-items:flex-start;gap:8px;padding:7px 10px;border:1px solid #e5e7eb;border-radius:7px;margin-bottom:6px;cursor:pointer;transition:border-color .12s,background .12s}
.hazard-card:hover{border-color:#bfdbfe;background:#f8fbff}
.hazard-card.checked{border-color:#185FA5;background:#EFF6FF;border-left:3px solid #185FA5}
.hazard-card input[type=checkbox]{width:14px;height:14px;margin-top:2px;flex-shrink:0;accent-color:#185FA5;cursor:pointer}
.hazard-card-body{flex:1}
.hazard-card-top{display:flex;align-items:center;gap:7px;flex-wrap:wrap;margin-bottom:3px}
.hazard-card-name{font-size:12px;font-weight:600;color:#1a1a1a}
.badge{font-size:10px;padding:1px 7px;border-radius:4px;font-weight:600;display:inline-block}
.badge-high{background:#FEE2E2;color:#991B1B}
.badge-medium{background:#FEF3C7;color:#92400E}
.badge-low{background:#DCFCE7;color:#166534}
.hazard-card-mit{font-size:11px;color:#4b5563;line-height:1.5;margin-bottom:3px}
.hazard-card-barriers{font-size:10px;color:#9ca3af}

/* BARRIER REFERENCE LIST */
.barrier-section{margin-top:10px;padding-top:8px;border-top:1px solid #e5e7eb}
.barrier-section-title{font-size:9.5px;font-weight:600;color:#374151;margin-bottom:4px}
.barrier-group{margin-bottom:6px}
.barrier-group-label{font-size:8.5px;color:#6b7280;font-weight:600;margin-bottom:3px;text-transform:uppercase;letter-spacing:.03em}
.barrier-item{font-size:8.5px;color:#374151;margin-bottom:2px;line-height:1.3;padding-left:8px;position:relative}
.barrier-item::before{content:"•";position:absolute;left:0;color:#185FA5;font-weight:700}

/* BOTTOM SIGS */
canvas.sig-canvas{border-bottom:1px solid #000;width:100%;height:56px;cursor:crosshair;touch-action:none;display:block}
.sig-field{display:flex;align-items:center;gap:4px;margin-top:3px;font-size:10px}
.sig-field input{flex:1;border:none;border-bottom:1px solid #888;outline:none;font-size:10px;font-family:'Times New Roman',Times,serif;background:transparent}

/* FOOTER */
.form-footer{display:flex;justify-content:space-between;align-items:flex-end;font-size:9.5px;padding:4px 8px;border-top:1px solid #000}

/* MODAL */
#submit-modal{display:none;position:fixed;inset:0;background:rgba(0,0,0,.45);z-index:500;align-items:center;justify-content:center}
#submit-modal.open{display:flex}
.modal-box{background:#fff;border-radius:12px;padding:28px 32px;max-width:460px;width:90%}
.modal-title{font-size:16px;font-weight:700;color:#1a1a1a;margin-bottom:4px;font-family:'Segoe UI',Arial,sans-serif}
.modal-sub{font-size:13px;color:#6b7280;margin-bottom:16px;line-height:1.5;font-family:'Segoe UI',Arial,sans-serif}
.modal-label{font-size:12px;color:#6b7280;margin-bottom:4px;display:block;font-family:'Segoe UI',Arial,sans-serif}
.modal-input{width:100%;padding:8px 12px;border:1px solid #d1d5db;border-radius:6px;font-size:14px;outline:none;font-family:'Segoe UI',Arial,sans-serif}
.modal-input:focus{border-color:#185FA5;box-shadow:0 0 0 3px rgba(24,95,165,.1)}
.modal-btn-row{display:flex;gap:10px;justify-content:flex-end;margin-top:16px}
.modal-cancel{background:#fff;color:#6b7280;border:1px solid #d1d5db;border-radius:7px;padding:9px 16px;font-size:14px;cursor:pointer;font-family:'Segoe UI',Arial,sans-serif}
.modal-send{background:#15803d;color:#fff;border:none;border-radius:7px;padding:9px 20px;font-size:14px;font-weight:600;cursor:pointer;font-family:'Segoe UI',Arial,sans-serif}

/* PRINT */
@media print{
  body{background:#fff}
  .page-wrap{padding:0;max-width:100%}
  .util-bar,.no-print,.crew-clear-btn{display:none !important}
  .page-wrap{max-width:100% !important;padding:0 !important}
  .form-paper{border:1px solid #000;padding:5px 7px;transform:scale(0.85);transform-origin:top left;width:117.6%;}
  canvas{border-bottom:1px solid #000 !important}
  .hazard-card:not(.checked){display:none !important}
  .hazard-card{page-break-inside:avoid !important}
  .task-group-label{display:none;page-break-inside:avoid}
  .task-group-label.has-checked{display:flex !important}
  select{border:none !important;background:transparent !important;-webkit-appearance:none;appearance:none}
  @page{margin:8mm;size:letter portrait;@bottom-left{content:none}}
  .form-footer{page-break-inside:avoid}
  #page-number::before{content:"Page " counter(page)}
  body{counter-reset:page}
  .form-paper{counter-increment:page}
}

/* ── MOBILE RESPONSIVE ── */
@media screen and (max-width:500px){
  /* Util bar stacks */
  .util-bar{padding:10px 12px;gap:8px}
  .util-bar-left{min-width:100%;margin-bottom:2px}
  .btn-upload,.btn-print,.btn-submit{padding:8px 12px;font-size:12px}

  /* Header table: stack Daily Job Plan / EC Info vertically */
  table.ft{table-layout:auto}
  table.ft td,table.ft th{padding:2px 3px;font-size:10px}

  /* Crew+Approved+EC: stack into 2 columns (hide EC labels, show inline) */
  .crew-sig-row{min-height:44px}
  .crew-name-col{width:48%}

  /* Job spec */
  .job-spec-inner{padding:6px 8px}
  .js-sec-title{font-size:12px;margin-bottom:7px}
  .task-add-row select{padding:6px 8px;font-size:11px}
  .task-chip{font-size:10px;padding:2px 8px}

  /* Hazard cards */
  .hazard-card{padding:6px 8px;gap:6px}

  /* Barrier grid: already 1 col, just tighten */
  .barrier-group{margin-bottom:4px}

  /* Sigs */
  canvas.sig-canvas{height:48px}
  canvas.crew-canvas{height:40px}

  /* Footer */
  .form-footer{font-size:8.5px;padding:3px 5px}
}
</style>
</head>
<body>

<!-- MODAL -->
<div id="submit-modal">
  <div class="modal-box">
    <div class="modal-title">Submit &amp; save form</div>
    <div class="modal-sub" id="modal-sub-text">Sign in with your Microsoft account to save this form directly to the shared OneDrive folder, and send an email summary to the safety team.</div>
    <div id="modal-signin-row" style="margin-bottom:12px;display:none">
      <button class="modal-send" style="background:#185FA5" onclick="signIn()">&#x1F511; Sign in with Microsoft</button>
    </div>
    <div id="modal-od-row" style="margin-bottom:12px">
      <div id="modal-od-status" style="font-size:12px;color:#6b7280;font-family:'Segoe UI',Arial,sans-serif;margin-bottom:8px"></div>
      <label class="modal-label">OneDrive folder path (e.g. AEPS HSSE Forms/Completed)</label>
      <input class="modal-input" type="text" id="od-folder" value="AEPS HSSE Forms/Completed" style="margin-bottom:8px">
    </div>
    <label class="modal-label">Also send email summary to:</label>
    <input class="modal-input" type="email" id="sender-email" placeholder="safety@aeps-electric.com" value="safety@aeps-electric.com">
    <div class="modal-btn-row">
      <button class="modal-cancel" onclick="closeModal()">Cancel</button>
      <button class="modal-send" id="btn-save-submit" onclick="doSubmit()">Save to OneDrive &amp; email ↗</button>
    </div>
    <div id="modal-save-status" style="margin-top:10px;font-size:12px;font-family:'Segoe UI',Arial,sans-serif;text-align:center"></div>
  </div>
</div>

<div class="page-wrap">

<!-- UTIL BAR -->
<div class="util-bar no-print">
  <div class="util-bar-left">
    <strong>AEPS-Electric — HSSE Form E</strong>
    <span>Complete the form, then use Print / PDF to save a copy.</span>
  </div>
  <button class="btn-print" onclick="window.print()">&#x1F5A8; Print / PDF</button>
  <button id="btn-signin" class="btn-upload" onclick="signIn()" style="display:none">&#x1F511; Sign in to OneDrive</button>
  <span id="od-status" style="font-size:11px;color:#6b7280;font-family:'Segoe UI',Arial,sans-serif"></span>
</div>

<!-- FORM PAPER -->
<div class="form-paper">

  <!-- TITLE -->
  <div class="form-title-row">
    <h1>HSSE Form E: &nbsp;<u>Daily Job HSSE Plan</u> – Considerations</h1>
  </div>
  <div class="warning-banner">IF CONDITIONS CHANGE…REVIEW AND REVISE THE PLAN.</div>
  <div style="text-align:center;font-size:10px;font-style:italic;color:#333;margin:3px 6px 5px;line-height:1.4;border-bottom:1px solid #ccc;padding-bottom:4px">This form is not intended to be comprehensive and is supplemental to the project Site Safety Plan. Employees and supervisors are always encouraged to err on the side of caution and stop work if anyone feels that conditions are unsafe.</div>

  <!-- ROW 1: Daily Job Plan header + JP Evaluation -->
  <table class="ft" style="margin-bottom:0">
    <colgroup><col style="width:38%"><col style="width:32%"><col style="width:30%"></colgroup>
    <tr>
      <td rowspan="2" style="text-align:center;font-size:14px;font-style:italic;font-weight:bold;vertical-align:middle;border-right:2px solid #000">
        Daily Job Plan<br><span style="font-size:10px;font-weight:normal;font-style:normal">General Information</span>
      </td>
      <td colspan="2" style="font-size:10px">
        JP Evaluation — Acceptable&nbsp;<input type="checkbox" id="jp-ok">&nbsp;&nbsp;
        Needs Improvement&nbsp;<input type="checkbox" id="jp-imp">&nbsp;&nbsp;
        Coaching completed&nbsp;<input type="checkbox" id="jp-coach">
      </td>
    </tr>
    <tr>
      <td style="font-size:10px">Conducted by: <input type="text" id="conducted-by" style="width:58%"></td>
      <td style="font-size:10px">On Site:&nbsp;<input type="checkbox" id="onsite">&nbsp;&nbsp;Off Site:&nbsp;<input type="checkbox" id="offsite"></td>
    </tr>
    <tr>
      <td colspan="2"><strong>JP Prepared By:</strong> <select id="prepared-by" style="width:68%;border:1px solid #ccc;border-radius:3px;background:#fff;font-size:10px;font-family:'Times New Roman',Times,serif;padding:2px;outline:none;color:#000" onchange="syncPreparer()"><option value="">— load data file —</option></select></td>
      <td style="vertical-align:top"><strong>Project Name:</strong><br><input type="text" id="work-location" placeholder="Project name" style="font-size:13px;font-weight:500;width:100%;border:none;border-bottom:1px solid #888;outline:none;background:transparent;padding:2px 0;font-family:'Times New Roman',Times,serif"></td>
    </tr>
    <tr>
      <td colspan="2"><strong>Date:</strong> <input type="date" id="job-date" style="width:auto"></td>
      <td style="background:#e8e8e8;font-weight:bold;text-align:center;font-size:9px;vertical-align:middle;padding:2px 3px" rowspan="2">Emergency<br>Contact<br>Info</td>
    </tr>
    <tr>
      <td colspan="2" style="font-size:10px">
        <strong>Office:</strong>&nbsp;732-792-0700
      </td>
    </tr>
  </table>

  <!-- ROW 2: Crew Signatures | Approved By | Emergency Contacts -->
  <table class="ft" style="border-top:none;margin-bottom:0">
    <colgroup><col style="width:44%"><col style="width:26%"><col style="width:16%"><col style="width:14%"></colgroup>
    <tr>
      <td style="font-weight:bold;font-size:10.5px;vertical-align:top;border-right:2px solid #000" rowspan="2">
        <div style="font-weight:bold;margin-bottom:4px">Crew Members (Sign)</div>
        <div id="crew-sigs-container"></div>
      </td>
      <td style="vertical-align:top">
        <div style="font-weight:bold;margin-bottom:4px;font-size:10.5px">Approved By:</div>

        <div style="margin-bottom:5px">
          <div style="font-weight:bold;font-size:10px;margin-bottom:2px">Supervisor:</div>
          <select class="personnel-sel" id="approved-sup" onchange="onPersonnelChange('approved-sup','phone-sup')">
            <option value="">— select —</option>
          </select>
          <div class="personnel-phone" id="phone-sup"></div>
        </div>

        <div style="margin-bottom:5px">
          <div style="font-weight:bold;font-size:10px;margin-bottom:2px">Crew Leader:</div>
          <select class="personnel-sel" id="approved-mgr" onchange="onPersonnelChange('approved-mgr','phone-mgr')">
            <option value="">— select —</option>
          </select>
          <div class="personnel-phone" id="phone-mgr"></div>
        </div>

        <div>
          <div style="font-weight:bold;font-size:10px;margin-bottom:2px">Director:</div>
          <select class="personnel-sel" id="approved-dir" onchange="onPersonnelChange('approved-dir','phone-dir')">
            <option value="">— select —</option>
          </select>
          <div class="personnel-phone" id="phone-dir"></div>
        </div>
      </td>
      <td style="font-size:11.5px;font-weight:500;vertical-align:top">
        <div>Fire, Police, Amb.</div>
        <br><br>
        <div>Office</div>
        <br><br>
        <div>Supervisor</div>
        <br><br><br>
        <div>Crew Leader</div>
        <br><br>
        <div>Director</div>
      </td>
      <td style="font-size:11.5px;font-weight:500;vertical-align:top">
        <div>911</div>
        <br><br>
        <div>732-792-0700</div>
        <br><br>
        <div id="ec-sup-display">—</div>
        <br><br>
        <div id="ec-mgr-display">—</div>
        <br><br>
        <div id="ec-dir-display">—</div>
      </td>
    </tr>
  </table>

  <!-- PPE + ASSEMBLY -->
  <table class="ft" style="border-top:none;margin-bottom:0">
    <tr>
      <td style="width:55%"><strong>Minimum Required PPE</strong> (Additional PPE AS Required): Hard Hat, Safety Shoes, Safety Glasses, Safety Vest</td>
      <td style="width:45%"><strong>Emergency Assembly Location:</strong> <input type="text" id="assembly-loc" value="Behind the Manager's Truck" style="width:58%"></td>
    </tr>
  </table>

  <!-- JOB SPECIFIC SECTION -->
  <div class="sec-hdr">Job Specific Information</div>
  <div class="job-spec-wrap">
    <div class="job-spec-inner">
      <div class="js-sec-title">Select tasks for today's work</div>
      <div class="chips-wrap" id="task-chips"></div>
      <div class="task-add-row no-print">
        <select id="task-select-main" onchange="addTask(this.value)" disabled>
          <option value="">— choose a task —</option>
        </select>
      </div>
      <div id="hazard-list" style="margin-top:4px"></div>

      <div class="barrier-section" id="barrier-section" style="display:none">
        <div class="barrier-section-title">Barrier Reference</div>
        <div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:6px">
          <div class="barrier-group">
            <div class="barrier-group-label"><u>Control Barriers</u></div>
            <div class="barrier-item">1-Eliminate the Hazard/Threat</div>
            <div class="barrier-item">2-Reduce Energy to a Safe Level</div>
            <div class="barrier-item">3-Physical Barrier</div>
          </div>
          <div class="barrier-group">
            <div class="barrier-group-label"><u>Protective Barriers</u></div>
            <div class="barrier-item">4-Additional PPE</div>
            <div class="barrier-item">5-Warning Device</div>
            <div class="barrier-item">6-Minimize Chances for Error</div>
          </div>
          <div class="barrier-group">
            <div class="barrier-group-label"><u>Support Barriers</u></div>
            <div class="barrier-item">7-Written Procedures</div>
            <div class="barrier-item">8-Training</div>
            <div class="barrier-item">9-Designated Observer</div>
          </div>
        </div>
      </div>

    </div>
  </div>

  <!-- FURTHER COMMENTS -->
  <table class="ft" style="border-top:1px solid #000;margin-top:0;margin-bottom:0">
    <tr>
      <td style="padding:5px 7px">
        <div style="font-size:10.5px;font-weight:bold;margin-bottom:4px">Further Comments:</div>
        <textarea id="further-comments" rows="5" style="width:100%;font-size:10.5px;font-family:'Times New Roman',Times,serif;border:none;border-bottom:1px solid #ccc;resize:none;outline:none;line-height:1.8;background:transparent;padding:2px" placeholder="Additional thoughts, observations, or notes…"></textarea>
      </td>
    </tr>
  </table>

  <!-- BOTTOM SIGNATURES -->
  <table class="ft" style="border-top:2px solid #000;margin-top:0;margin-bottom:0">
    <tr>
      <td style="width:50%;padding:4px 6px">
        <div style="font-size:10px;font-weight:bold;margin-bottom:1px">JP Preparer Signature:</div>
        <div style="font-size:9px;color:#555;margin-bottom:3px;font-style:italic">Person who prepared this form</div>
        <div style="position:relative">
          <canvas class="sig-canvas" id="sig-employee"></canvas>
          <button class="no-print" onclick="clearSig('sig-employee')" style="position:absolute;top:2px;right:2px;background:none;border:none;font-size:9px;color:#9ca3af;cursor:pointer">Clear</button>
        </div>
        <div class="sig-field"><strong>Name:</strong><input type="text" id="sig-emp-name" placeholder="Printed name"></div>
        <div class="sig-field"><strong>Email:</strong><input type="email" id="sig-emp-email" placeholder="email@aeps-electric.com"></div>
      </td>
      <td style="width:50%;padding:4px 6px">
        <div style="font-size:10px;font-weight:bold;margin-bottom:2px">Signature:</div>
        <div style="position:relative">
          <canvas class="sig-canvas" id="sig-supervisor"></canvas>
          <button class="no-print" onclick="clearSig('sig-supervisor')" style="position:absolute;top:2px;right:2px;background:none;border:none;font-size:9px;color:#9ca3af;cursor:pointer">Clear</button>
        </div>
        <div class="sig-field"><strong>Name:</strong><input type="text" id="sig-sup-name" placeholder="Printed name"></div>
        <div class="sig-field"><strong>Email:</strong><input type="email" id="sig-sup-email" placeholder="email@aeps-electric.com"></div>
      </td>
    </tr>
  </table>

  <!-- FOOTER -->
  <div class="form-footer">
    <span id="page-number"></span>
    <span style="font-weight:bold;text-align:center">AEPS-Electric<br><span style="font-weight:normal;font-style:italic">-Proprietary-</span></span>
    <span>Issue date: April 13, 2026</span>
  </div>

</div><!-- /form-paper -->
</div><!-- /page-wrap -->

<script>
// ── EMBEDDED DATA (from AEPS_HSSE_Data_4_13_26_DL.xlsx) ─────────────────────
const TASKS=[{"name": "Bright Sunlight", "active": true}, {"name": "Working on a ground array", "active": true}, {"name": "Extreme cold", "active": true}, {"name": "Extreme heat", "active": true}, {"name": "Ladder access", "active": true}, {"name": "Loading/off Loading LANDSCAPE Trailer", "active": true}, {"name": "Loading/off Loading TRACTOR Trailer", "active": true}, {"name": "Scissor Lift Roof Access", "active": true}, {"name": "Using a Crane to move materials", "active": true}, {"name": "Using a telehandler to move materials", "active": true}, {"name": "Working at height flat roof", "active": true}, {"name": "Electrically isolating solar panels", "active": true}, {"name": "Mechanically removing/attaching solar panels", "active": true}, {"name": "Working in an inverter", "active": true}, {"name": "Working in a DC Combiner", "active": true}, {"name": "IR viewing panels", "active": true}];
const HAZARDS=[{"task": "Extreme heat", "category": "Extreme heat/cold", "risk": "Medium", "barriers": "9. Supervisor/observer", "mit": "Keep an eye on the people around you, look for signs of heat stroke", "active": true}, {"task": "Extreme heat", "category": "Extreme heat/cold", "risk": "Medium", "barriers": "1. Eliminate the hazard/threat", "mit": "Shift to an earlier work day", "active": true}, {"task": "Extreme heat", "category": "Extreme heat/cold", "risk": "Medium", "barriers": "1. Eliminate the hazard/threat", "mit": "Take breaks in shady area", "active": true}, {"task": "Extreme heat", "category": "Hot surfaces", "risk": "Medium", "barriers": "4.PPE", "mit": "Roof surfaces, especially dark ones can become very hot.  Wear gloves that are thick enough to insulate from heat.", "active": true}, {"task": "Extreme cold", "category": "Extreme heat/cold", "risk": "Medium", "barriers": "9. Supervisor/observer", "mit": "Keep an eye on the people around you, look for cold stress symptoms", "active": true}, {"task": "Extreme cold", "category": "Electrical contact", "risk": "Medium", "barriers": "1. Eliminate the hazard/threat; 4. PPE", "mit": "Wear layers, make sure cold weather clothing does not compromise arc protective clothing", "active": true}, {"task": "Extreme cold", "category": "Extreme heat/cold", "risk": "Medium", "barriers": "1. Eliminate the hazard/threat", "mit": "Delay work if reduced dexterity will affect job safety", "active": true}, {"task": "Bright Sunlight", "category": "UV exposure", "risk": "High", "barriers": "4. PPE", "mit": "Wear safety glasses rated to block UV", "active": true}, {"task": "Bright Sunlight", "category": "UV exposure", "risk": "Medium", "barriers": "4. PPE", "mit": "Use sweat resistant sunblock on all exposed skin, re-apply per manufacturer instructions", "active": true}, {"task": "Scissor Lift Roof Access", "category": "Vehicle instability", "risk": "High", "barriers": "1. Eliminate hazard; 5. Warning Device; 8. Training", "mit": "Only allow employees certified by AEPS to drive lifts, setup on solid ground, use outriggers, do not override tilt alarms", "active": true}, {"task": "Scissor Lift Roof Access", "category": "Equipment failure", "risk": "Medium", "barriers": "5. Warning Device; 8. Training", "mit": "Inspected daily. Equipment must be put out of service immediately if warning lights are lit or machine damage is evident", "active": true}, {"task": "Scissor Lift Roof Access", "category": "Traffic collisions", "risk": "High", "barriers": "3. Physical Barriers; 5. Warning Device", "mit": "Use cones to mark out work area around stationary lifts, walkers required when lift is moving", "active": true}, {"task": "Scissor Lift Roof Access", "category": "Falling from height", "risk": "High", "barriers": "3. Physical Barriers", "mit": "Remain aware at all times when in basket, keep entire body inside of basket railing", "active": true}, {"task": "Scissor Lift Roof Access", "category": "Electrical contact", "risk": "High", "barriers": "8. Training", "mit": "Be aware of what is around and above scissor lift when operating, especially power lines", "active": true}, {"task": "Ladder access", "category": "Equipment failure", "risk": "High", "barriers": "1. Eliminate hazard; 6. Minimize error; 8. Training", "mit": "Ladders inspections need to be done daily and they should be put out of use at first sign of failure, never erect a ladder over a doorway", "active": true}, {"task": "Ladder access", "category": "Falling from height", "risk": "High", "barriers": "4. PPE; 8. Training", "mit": "Erect Ladders on stable footings, correct angle, tied up, not used past usable reach, 3ft above landing surface", "active": true}, {"task": "Ladder access", "category": "Climbing", "risk": "High", "barriers": "6. Minimize error; 8. Training", "mit": "Maintain 3 points of contact when climbing ladders — no carrying material or tools up ladders", "active": true}, {"task": "Ladder access", "category": "Falling objects", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE; 8. Training", "mit": "Only one worker is allowed on a ladder at a time, cones should be in place to keep people from walking under ladders were they could be struck by falling objects.", "active": true}, {"task": "Working at height flat roof", "category": "Falling from height", "risk": "High", "barriers": "4.PPE; 8. Training", "mit": "Inspect work area, including access and egress points, for holes, damdged roof deck areas, and skylights.  Baracade off areas of concern and notify crew members.", "active": true}, {"task": "Working at height flat roof", "category": "Damage to building contents", "risk": "Medium", "barriers": "8. Training", "mit": "If a potential leak point is created, or pre-existing, mark it with an oil pencil, enter it in SF, and report to the work manager", "active": true}, {"task": "Working at height flat roof", "category": "Falling from height", "risk": "High", "barriers": "3. Physical Barriers; 4. PPE; 8. Training", "mit": "Use guardrails, safety monitor, and warning lines where feasible — fall arrest systems if called for", "active": true}, {"task": "Working at height flat roof", "category": "Falling objects", "risk": "High", "barriers": "1. Eliminate hazard; 9. Supervisor/observer", "mit": "Stow material and tools safely, be particularly careful when working near the edge of the roof", "active": true}, {"task": "Working at height flat roof", "category": "Falling objects", "risk": "High", "barriers": "3. Physical Barriers", "mit": "Be aware of pedestrians and workers on the ground. Restrict access to base of building under work area using cones and tape", "active": true}, {"task": "Working on a ground array", "category": "Slippery areas", "risk": "Medium", "barriers": "6. Minimize chances of error", "mit": "Watch for uneven turane, trip fall hazards covered by grass", "active": true}, {"task": "Working on a ground array", "category": "Poisonous/dangerous animals", "risk": "Medium", "barriers": "1. Eliminate the hazard/threat", "mit": "Spray deet based bug spray, following product directions, especially around pants and shoes to reduce the possibility of tick bites.", "active": true}, {"task": "Working on a ground array", "category": "Traffic collisions", "risk": "Medium", "barriers": "6. Minimize chances of error; 8. Training", "mit": "Drive slowly and cautiously when driving a vehicle inside of a ground array, obsticles, uneven terrain, and wet ground can be hidden by ground cover", "active": true}, {"task": "Working on a ground array", "category": "Forest fires", "risk": "High", "barriers": "1. Eliminate the hazard/threat; 8. Training", "mit": "Be extra careful of igniting dry grass, SMOKING IS NOT ALLOWED INSIDE OF A GROUND ARRAY!", "active": true}, {"task": "Working on a ground array", "category": "Disturbing wildlife", "risk": "Medium", "barriers": "9.Supervisor/observer", "mit": "Be aware of the animals in the surounding habitat and their needs.  Our goal is to impact the environment as little as possible.", "active": true}, {"task": "Working on a ground array", "category": "Change in normal/natural draining/flow patterns", "risk": "Medium", "barriers": "", "mit": "Be aware of storm water flow patterns when moving dirt, or plants", "active": true}, {"task": "Working on a ground array", "category": "Erosion", "risk": "Medium", "barriers": "", "mit": "Plan for the potential of newly disturbed dirt to erode.  Be particularly careful to protect streams and other waterways from dirt erosion.  Call Project Manager with quesitons/concerns", "active": true}, {"task": "Using a telehandler to move materials", "category": "Vehicle instability", "risk": "High", "barriers": "6. Minimize error; 8. Training", "mit": "Only allow employees certified by AEPS to drive lifts, setup on solid ground, use outriggers, do not override tilt alarms. Follow lift tables, drive slowly", "active": true}, {"task": "Using a telehandler to move materials", "category": "Equipment failure", "risk": "High", "barriers": "8. Training", "mit": "Inspect telehandlers daily, and put out of service immediately if warning lights are lit or machine damage is evident", "active": true}, {"task": "Using a telehandler to move materials", "category": "Shifting loads", "risk": "High", "barriers": "6. Minimize error; 8. Training", "mit": "Balance and secure loads, carry loads as low to the ground as possible", "active": true}, {"task": "Using a telehandler to move materials", "category": "Falling from height", "risk": "High", "barriers": "3. Physical Barriers; 5. Warning Device; 8. Training", "mit": "Cordon off roof loading area to comply with proper fall protection and make sure that staging does not interfere with roof egress", "active": true}, {"task": "Using a telehandler to move materials", "category": "Falling structures", "risk": "High", "barriers": "8. Training; 9. Supervisor/observer", "mit": "Ensure that the roof structure is sound AND approved for maximum point and total load before loading materials onto it", "active": true}, {"task": "Using a telehandler to move materials", "category": "Falling structures", "risk": "High", "barriers": "8. Training; 9. Supervisor/observer", "mit": "Place loads on roof support members close to the intersection of I beams, or support walls", "active": true}, {"task": "Using a telehandler to move materials", "category": "Falling objects", "risk": "High", "barriers": "4.PPE; 8. Training", "mit": "Keep hard hats on!  Telehandler driver must watch for pedestrians, but pedestrians must also watch for telehandler.  Use cones, flag walkers when needed", "active": true}, {"task": "Using a Crane to move materials", "category": "Overhead cranes", "risk": "High", "barriers": "6. Minimize chances of error; 9.Supervisor/observer", "mit": "Crane opperating company has primary responsibility for rigging, and craning safety, however, anyone can stop a craning activity if they do not feel that it is progressing safely!", "active": true}, {"task": "Using a Crane to move materials", "category": "Falling objects", "risk": "High", "barriers": "1. Eliminate the hazard/threat; 6. Minimize chances of error; 9.Supervisor/observer", "mit": "Confirm the maximum potential weight being picked with crane operator.  Craning crew should be using their own rigging equipment!", "active": true}, {"task": "Using a Crane to move materials", "category": "Falling objects", "risk": "High", "barriers": "3. Physical Barriers; 5. Warning Device; 8. Training", "mit": "Keep craned loads from traveling over persons — use cones, caution tape, monitors, and communication with building occupants", "active": true}, {"task": "Using a Crane to move materials", "category": "Overhead cranes", "risk": "Medium", "barriers": "6. Minimize error; 8. Training", "mit": "Reminded AEPS Employees of the weight of a crane pick load and told not to go near or touch a load that is in the air", "active": true}, {"task": "Using a Crane to move materials", "category": "Electrical contact", "risk": "Medium", "barriers": "1. Eliminate hazard; 5. Warning Device; 9. Supervisor/observer", "mit": "Ensure that craning team is aware of all electrical power lines that could interfere with their craning activity", "active": true}, {"task": "Using a Crane to move materials", "category": "Falling structures", "risk": "High", "barriers": "8. Training; 9. Supervisor/observer", "mit": "Vissually check that the roof structure is sound AND approved for maximum point and total load before loading", "active": true}, {"task": "Using a Crane to move materials", "category": "Falling structures", "risk": "High", "barriers": "8. Training; 9. Supervisor/observer", "mit": "Place loads on roof support members close to the intersection of I beams, or support walls", "active": true}, {"task": "Loading/off Loading TRACTOR Trailer", "category": "Falling objects", "risk": "High", "barriers": "1. Eliminate hazard; 6. Minimize error", "mit": "Employees should distance themselves from loads being moved — palletized materials can shift and fall when being loaded", "active": true}, {"task": "Loading/off Loading TRACTOR Trailer", "category": "Vehicle instability", "risk": "Medium", "barriers": "4. PPE; 8. Training", "mit": "Forklifts and telehandlers become less stable as loads are lifted higher. Be extra careful on uneven or sloped terrain and wear seatbelts", "active": true}, {"task": "Loading/off Loading TRACTOR Trailer", "category": "Rigging failure", "risk": "High", "barriers": "1. Eliminate hazard; 6. Minimize error", "mit": "Ensure that material pallets are stacked straight, not too high, and material is secured to pallet", "active": true}, {"task": "Loading/off Loading TRACTOR Trailer", "category": "Shifting loads", "risk": "High", "barriers": "1. Eliminate hazard; 6. Minimize error", "mit": "Do not double-stack pallets without a supervisor approval", "active": true}, {"task": "Loading/off Loading TRACTOR Trailer", "category": "Traffic collisions", "risk": "Medium", "barriers": "3. Physical Barriers; 5. Warning Device; 9. Supervisor/observer", "mit": "Cordon off loading/unloading areas with cones and/or tape, use a spotter", "active": true}, {"task": "Loading/off Loading TRACTOR Trailer", "category": "Traffic collisions", "risk": "High", "barriers": "4. PPE; 9. Supervisor/observer", "mit": "Everyone working around the loading area must wear high visibility clothing", "active": true}, {"task": "Loading/off Loading TRACTOR Trailer", "category": "Falling objects", "risk": "High", "barriers": "8. Training", "mit": "We are not experts in tractor trailer load management or lashing. The truck operator must decide on load placement and secure their own load", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Equipment failure", "risk": "High", "barriers": "6. Minimize error; 8. Training", "mit": "AEPS truck driver sould personally inspect trailer for safety and correct operation before loading", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Falling objects", "risk": "High", "barriers": "1. Eliminate the hazard/threat; 6. Minimize chances of error", "mit": "Employees should distance themselves from the loads being moved, understanding that paletized materials can shift and fall when being loaded.", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Vehicle instability", "risk": "Medium", "barriers": "4.PPE; 8. Training", "mit": "Forklifts and telehandlers can become less stable the higher loads are lifted.  Be extra careful opperating on uneven or sloped terran and wear seatbelts!", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Rigging failure", "risk": "High", "barriers": "1. Eliminate the hazard/threat; 6. Minimize chances of error", "mit": "Ensure that materials pallets are stacked straight, and not too high to be stable, and material is secure to palet adequately", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Shifting loads", "risk": "High", "barriers": "1. Eliminate the hazard/threat; 6. Minimize chances of error", "mit": "Do not doublestack pallets, without a suppervisor's approval.", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Traffic collisions", "risk": "Medium", "barriers": "3. Physical Barriers; 5. Warning Device; 9.Supervisor/observer", "mit": "Cordone off loading/unloading areas with cones and/or tape", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Traffic collisions", "risk": "High", "barriers": "4.PPE; 9.Supervisor/observer", "mit": "Everyone working around the loading area must wear high visability clothing", "active": true}, {"task": "Loading/off Loading LANDSCAPE Trailer", "category": "Shifting loads", "risk": "High", "barriers": "6. Minimize chances of error; 8. Training", "mit": "AEPS truck driver has final responsibility for ensuring that the load is lashed down, balanced - inspect carefully before pulling away!", "active": true}, {"task": "Electrically isolating solar panels", "category": "Electrical contact", "risk": "High", "barriers": "2. Minimize Energy to Safe Level; 4.PPE; 8. Training", "mit": "Qualified person(s) should open COMBINER BOX disconnects, then open string fuses, then LOTO combiner boxes where strings terminate.", "active": true}, {"task": "Electrically isolating solar panels", "category": "Electrical contact", "risk": "High", "barriers": "2. Minimize Energy to Safe Level; 4.PPE; 8. Training", "mit": "Qualified person(s) should open STRING INVERTER disconnects, then LOTO the inverter DC disconnect.", "active": true}, {"task": "Electrically isolating solar panels", "category": "Electrical contact", "risk": "High", "barriers": "5. Warning Device; 8. Training", "mit": "Qualified person(s) should check string with a clamp-on multimeter before opening", "active": true}, {"task": "Electrically isolating solar panels", "category": "Electrical contact", "risk": "High", "barriers": "5. Warning Device; 8. Training", "mit": "Do not disconnect module leads until confirming that there is no current on the string via a clamp-on multimeter", "active": true}, {"task": "Mechanically removing/attaching solar panels", "category": "Electrical contact", "risk": "High", "barriers": "1. Eliminate the hazard/threat", "mit": "Follow guidelines for electrically isolating solar panels before removing or re-installing solar panels", "active": true}, {"task": "Mechanically removing/attaching solar panels", "category": "Cuts / bleeding", "risk": "Medium", "barriers": "4.PPE; 8. Training", "mit": "Cracked module surfaces can be very sharp, make sure to wear adequate gloves, and clothing to keep the surface away from your skin", "active": true}, {"task": "Mechanically removing/attaching solar panels", "category": "Falling objects", "risk": "High", "barriers": "6. Minimize chances of error; 8. Training", "mit": "User torque tool to ensure that panel fasteners are installed to manufacturer specified torque.", "active": true}, {"task": "Mechanically removing/attaching solar panels", "category": "Muscle Fatique", "risk": "Medium", "barriers": "8. Training", "mit": "Follow NIOSH guidelines and limit single person lifting to under 51lbs", "active": true}, {"task": "Mechanically removing/attaching solar panels", "category": "Falling objects", "risk": "Medium", "barriers": "6. Minimize chances of error; 8. Training", "mit": "Do not carry modules around in higher wind", "active": true}, {"task": "Mechanically removing/attaching solar panels", "category": "Falling objects", "risk": "High", "barriers": "1. Eliminate the hazard/threat; 8. Training", "mit": "Secure materials and tools as you work.  Never leave unsecured materials unnatended.  Wind can pickup sudddenly.", "active": true}, {"task": "Working in an inverter", "category": "Electrical contact", "risk": "High", "barriers": "6. Minimize chances of error; 9.Supervisor/observer", "mit": "ONLY QUALIFIED PERSONS SHOULD BE WORKING INSIDE OF AN INVERTER!", "active": true}, {"task": "Working in an inverter", "category": "Electrical contact", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE", "mit": "Follow LOTO process to disconnect inverter from AC power source, and then confirm AC power is disconnected at inverter.", "active": true}, {"task": "Working in an inverter", "category": "Electrical contact", "risk": "High", "barriers": "2. Minimize Energy to Safe Level", "mit": "Be aware that capacitors in an inverter can store energy for 5 minutes or more before they dissapate!", "active": true}, {"task": "Working in an inverter", "category": "Electrical contact", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE", "mit": "Open COMBINER BOX disconnects and LOTO. dc busbar and all PV output circuits will be energized until all combiner disconnects are open.", "active": true}, {"task": "Working in an inverter", "category": "Electrical contact", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE", "mit": "Inverter DC and AC disconnects should be opened and LOTO before opening inverter", "active": true}, {"task": "Working in an inverter", "category": "Electrical contact", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE", "mit": "Be aware that lineside connections on the INTERNAL inverter dc and ac disconnects will remain energized unless all ac and dc sources are removed", "active": true}, {"task": "Working in a DC Combiner", "category": "Electrical contact", "risk": "High", "barriers": "6. Minimize chances of error; 9.Supervisor/observer", "mit": "ONLY QUALIFIED PERSONS SHOULD BE WORKING INSIDE OF A dc COMBINER", "active": true}, {"task": "Working in a DC Combiner", "category": "Arching/electrical contact", "risk": "High", "barriers": "2. Minimize Energy to Safe Level; 5. Warning Device", "mit": "Only open touch safe fuses after confirming that no current is running through the string with a clamp on amp meter", "active": true}, {"task": "Working in a DC Combiner", "category": "Electrical contact", "risk": "High", "barriers": "2. Minimize Energy to Safe Level; 8. Training", "mit": "Combiner box disconnect should be open and LOTO, but THIS WILL NOT STOP POWER FROM ENTERING THE COMBINER FROM THE SOURCE STRINGS!", "active": true}, {"task": "Working in a DC Combiner", "category": "Backfeed", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE", "mit": "Issolated from other combiner boxes by opening the DC source circuit fuse in the inverter.", "active": true}, {"task": "Working in a DC Combiner", "category": "Electrical contact", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE", "mit": "Be aware that lineside connections on the INTERNAL combiner dc disconnect will remain energized unless panel sources are removed", "active": true}, {"task": "Working in a DC Combiner", "category": "Electrical contact", "risk": "High", "barriers": "3. Physical Barriers; 4.PPE", "mit": "Be aware and test ground and grounded conductors for current", "active": true}, {"task": "IR viewing panels", "category": "Slippery areas", "risk": "Medium", "barriers": "8. Training", "mit": "Stay aware of your surroundings, avoid looking through the IR cammera while walking", "active": true}];
const PERSONNEL=[{"name": "Michael Parker", "role": "Project Manager", "phone": "732-792-0700 x107", "email": "mparker@aeps-electric.com", "active": true}, {"name": "Marvin Oyuela", "role": "Supervisor", "phone": "732-609-0997", "email": "", "active": true}, {"name": "Elieser Levon", "role": "Crew Leader", "phone": "347-855-9611", "email": "", "active": true}, {"name": "Carlos Medrano", "role": "Crew Leader", "phone": "346-946-1709", "email": "", "active": true}, {"name": "Daniel Torres", "role": "Crew Leader", "phone": "732-504-9248", "email": "", "active": true}, {"name": "Gregg Stephens", "role": "Director", "phone": "215-779-2789", "email": "", "active": true}, {"name": "Alexander Hoyos", "role": "Crew Member", "phone": "732-489-0968", "email": "", "active": true}, {"name": "Amhed", "role": "Crew Member", "phone": "", "email": "", "active": true}, {"name": "Diego Maeda", "role": "Crew Member", "phone": "609-690-1449", "email": "", "active": true}, {"name": "Jorge Campos", "role": "Crew Member", "phone": "732-642-1376", "email": "", "active": true}, {"name": "Josue Ayala", "role": "Crew Member", "phone": "732-998-2607", "email": "", "active": true}, {"name": "Luis Marroquin", "role": "Crew Member", "phone": "732-867-4736", "email": "", "active": true}];
const SETTINGS={"Company Name": "AEPS-Electric", "Form Title": "HSSE Job Hazard Acknowledgment Form", "Submit Email Address": "safety@aeps-electric.com", "Company Tagline": "", "Office Phone": "732-792-0700"};

let rowCount=0, crewCount=0;

function activeTasks(){return TASKS.filter(t=>t.active);}
function hazardsFor(task){return HAZARDS.filter(h=>h.task===task&&h.active);}
function personnelByRole(role){return PERSONNEL.filter(p=>p.role===role&&p.active);}

// ── PERSONNEL DROPDOWNS ───────────────────────────────────────────────────────
function populatePersonnelDropdowns(){
  // JP Prepared By — all active personnel
  const prepSel = document.getElementById('prepared-by');
  if (prepSel) {
    const cur = prepSel.value;
    prepSel.innerHTML = '<option value="">— select —</option>' +
      PERSONNEL.filter(p=>p.active).map(p=>`<option value="${p.name}">${p.name} (${p.role})</option>`).join('');
    if (cur) prepSel.value = cur;
  }

  // Approved By — filtered by role
  const roleIdMap={'Supervisor':'sup','Crew Leader':'mgr','Director':'dir'};
  ['Supervisor','Crew Leader','Director'].forEach(role=>{
    const key=roleIdMap[role];
    const sel=document.getElementById('approved-'+key);
    if(!sel) return;
    const current=sel.value;
    sel.innerHTML='<option value="">— select —</option>';
    personnelByRole(role).forEach(p=>{
      const opt=document.createElement('option');
      opt.value=p.name; opt.dataset.phone=p.phone; opt.dataset.email=p.email;
      opt.textContent=p.name;
      sel.appendChild(opt);
    });
    if(current) sel.value=current;
    onPersonnelChange(sel.id,'phone-'+key);
  });
}

function onPersonnelChange(selId,phoneId){
  const sel=document.getElementById(selId);
  const phoneDiv=document.getElementById(phoneId);
  if(!sel||!phoneId) return;
  const opt=sel.options[sel.selectedIndex];
  const phone=opt&&opt.dataset.phone?opt.dataset.phone:'';
  if(phoneDiv) phoneDiv.textContent=phone?'📞 '+phone:'';
  // Also update the emergency contact display column
  const role=selId.includes('sup')?'sup':selId.includes('mgr')?'mgr':'dir';
  const ecEl=document.getElementById('ec-'+role+'-display');
  if(ecEl) ecEl.textContent=phone||'—';
}

// ── CREW SIGNATURE ROWS ───────────────────────────────────────────────────────
function crewMemberOptions(){
  const members=PERSONNEL.filter(p=>(p.role==='Crew Member'||p.role==='Crew Leader')&&p.active);
  if(!members.length) return '<option value="">— load data file —</option>';
  return '<option value="">— select —</option>'+members.map(p=>`<option value="${escQ(p.name)}">${p.name}</option>`).join('');
}

function buildCrewRows(n){
  const container=document.getElementById('crew-sigs-container');
  container.innerHTML='';
  for(let i=0;i<n;i++) addCrewRow();
}

function addCrewRow(){
  crewCount++;
  const id=crewCount;
  const today=new Date().toISOString().slice(0,10);
  const container=document.getElementById('crew-sigs-container');
  const div=document.createElement('div');
  div.className='crew-sig-row';
  div.id='crew-row-'+id;
  div.innerHTML=`
    <div class="crew-name-col">
      <select id="crew-name-${id}" class="personnel-sel">
        ${crewMemberOptions()}
      </select>
    </div>
    <div class="crew-sig-col">
      <button class="crew-clear-btn no-print" onclick="clearCrewSig(${id})">✕</button>
      <canvas class="crew-canvas" id="crew-canvas-${id}"></canvas>
    </div>`;
  container.appendChild(div);
  setTimeout(()=>initCrewSig(id),50);
}

function refreshCrewDropdowns(){
  document.querySelectorAll('[id^="crew-name-"]').forEach(sel=>{
    const cur=sel.value;
    sel.innerHTML=crewMemberOptions();
    if(cur) sel.value=cur;
  });
}

function initCrewSig(id){
  const canvas=document.getElementById('crew-canvas-'+id);
  if(!canvas) return;
  const ctx=canvas.getContext('2d');
  let drawing=false,lx=0,ly=0;
  function resize(){
    const r=canvas.getBoundingClientRect(),dpr=window.devicePixelRatio||1;
    const w=r.width||200;
    canvas.width=w*dpr; canvas.height=42*dpr; ctx.scale(dpr,dpr);
  }
  function pos(e){const r=canvas.getBoundingClientRect(),src=e.touches?e.touches[0]:e;return[src.clientX-r.left,src.clientY-r.top];}
  function start(e){e.preventDefault();drawing=true;[lx,ly]=pos(e);}
  function move(e){e.preventDefault();if(!drawing)return;const[x,y]=pos(e);ctx.beginPath();ctx.moveTo(lx,ly);ctx.lineTo(x,y);ctx.strokeStyle='#000';ctx.lineWidth=1.4;ctx.lineCap='round';ctx.stroke();[lx,ly]=[x,y];}
  function stop(){drawing=false;}
  canvas.addEventListener('mousedown',start);canvas.addEventListener('mousemove',move);canvas.addEventListener('mouseup',stop);canvas.addEventListener('mouseleave',stop);
  canvas.addEventListener('touchstart',start,{passive:false});canvas.addEventListener('touchmove',move,{passive:false});canvas.addEventListener('touchend',stop);
  resize(); window.addEventListener('resize',resize);
}
function clearCrewSig(id){const c=document.getElementById('crew-canvas-'+id);if(c)c.getContext('2d').clearRect(0,0,c.width,c.height);}

// ── TASK / HAZARD CHIP+CARD SYSTEM ──────────────────────────────────────────
let selectedTasks = [];
let checkedHazards = {};

function addTask(val) {
  if (!val || selectedTasks.includes(val)) { document.getElementById('task-select-main').value=''; return; }
  selectedTasks.push(val);
  document.getElementById('task-select-main').value='';
  renderChips();
  renderHazards();
}

function removeTask(task) {
  selectedTasks = selectedTasks.filter(t => t !== task);
  Object.keys(checkedHazards).forEach(k => { if (k.startsWith(task+'||')) delete checkedHazards[k]; });
  renderChips();
  renderHazards();
}

function renderChips() {
  const el = document.getElementById('task-chips');
  if (!selectedTasks.length) { el.innerHTML='<span class="chips-empty">No tasks selected yet</span>'; return; }
  el.innerHTML = selectedTasks.map(t =>
    `<span class="task-chip">${t}<button onclick="removeTask('${escQ(t)}')">&#x2715;</button></span>`
  ).join('');
}

function renderHazards() {
  const listEl = document.getElementById('hazard-list');
  const barrierSec = document.getElementById('barrier-section');
  if (!selectedTasks.length) { listEl.innerHTML=''; barrierSec.style.display='none'; return; }
  barrierSec.style.display='block';
  let html = '';
  selectedTasks.forEach(task => {
    const rows = hazardsFor(task);
    if (!rows.length) return;
    html += `<div class="task-group-label"><span class="task-group-label-text">${task}</span><span class="task-group-label-line"></span></div>`;
    rows.forEach((r, i) => {
      const key = `${task}||${i}`;
      const chk = checkedHazards[key] ? 'checked' : '';
      const cls = checkedHazards[key] ? 'hazard-card checked' : 'hazard-card';
      const bc = r.risk==='High'?'badge-high':r.risk==='Medium'?'badge-medium':'badge-low';
      html += `<div class="${cls}" onclick="toggleCard(this,'${escQ(task)}',${i})">
        <input type="checkbox" ${chk} onclick="event.stopPropagation();toggleHz('${escQ(task)}',${i},this)">
        <div class="hazard-card-body">
          <div class="hazard-card-top">
            <span class="hazard-card-name">${r.category||r.task}</span>
            <span class="badge ${bc}">${r.risk} risk</span>
          </div>
          <div class="hazard-card-mit">${r.mit}</div>
          <div class="hazard-card-barriers">Controls: ${r.barriers}</div>
        </div>
      </div>`;
    });
  });
  listEl.innerHTML = html;
}

function toggleCard(row, task, idx) {
  const cb = row.querySelector('input[type=checkbox]');
  cb.checked = !cb.checked;
  toggleHz(task, idx, cb);
}

function toggleHz(task, idx, cb) {
  const key = `${task}||${idx}`;
  checkedHazards[key] = cb.checked;
  const row = cb.closest ? cb.closest('.hazard-card') : null;
  if (row) row.className = cb.checked ? 'hazard-card checked' : 'hazard-card';
}

function escQ(s){ return s.replace(/\\/g,'\\\\').replace(/'/g,"\\'"); }

function refreshAllTaskSelects() {
  const sel = document.getElementById('task-select-main');
  if (!sel) return;
  const cur = sel.value;
  sel.innerHTML = '<option value="">— choose a task —</option>' +
    activeTasks().map(t=>`<option value="${t.name.replace(/"/g,'&quot;')}">${t.name}</option>`).join('');
  sel.disabled = false;
  if (cur) { sel.value = cur; }
  // Re-render hazard cards with updated data
  renderHazards();
}

// ── BOTTOM SIGNATURES ─────────────────────────────────────────────────────────
function initSig(id,h){
  const canvas=document.getElementById(id);
  if(!canvas) return;
  const ctx=canvas.getContext('2d');
  let drawing=false,lx=0,ly=0;
  function resize(){const r=canvas.getBoundingClientRect(),dpr=window.devicePixelRatio||1;canvas.width=r.width*dpr;canvas.height=(h||56)*dpr;ctx.scale(dpr,dpr);}
  function pos(e){const r=canvas.getBoundingClientRect(),src=e.touches?e.touches[0]:e;return[src.clientX-r.left,src.clientY-r.top];}
  function start(e){e.preventDefault();drawing=true;[lx,ly]=pos(e);}
  function move(e){e.preventDefault();if(!drawing)return;const[x,y]=pos(e);ctx.beginPath();ctx.moveTo(lx,ly);ctx.lineTo(x,y);ctx.strokeStyle='#000';ctx.lineWidth=1.5;ctx.lineCap='round';ctx.stroke();[lx,ly]=[x,y];}
  function stop(){drawing=false;}
  canvas.addEventListener('mousedown',start);canvas.addEventListener('mousemove',move);canvas.addEventListener('mouseup',stop);canvas.addEventListener('mouseleave',stop);
  canvas.addEventListener('touchstart',start,{passive:false});canvas.addEventListener('touchmove',move,{passive:false});canvas.addEventListener('touchend',stop);
  resize();window.addEventListener('resize',resize);
}
function clearSig(id){const c=document.getElementById(id);if(c)c.getContext('2d').clearRect(0,0,c.width,c.height);}

// ── MICROSOFT GRAPH / ONEDRIVE ────────────────────────────────────────────────
// Replace CLIENT_ID below with your Azure app registration client ID
const MSAL_CLIENT_ID = 'f330cd8a-3319-4222-944e-2e3ba1a69d3a';
const MSAL_AUTHORITY  = 'https://login.microsoftonline.com/common';
const GRAPH_SCOPES    = ['Files.ReadWrite', 'User.Read'];

let msalInstance = null;
let graphToken   = null;

function initMSAL(){
  if(msalInstance) return;
  // Load MSAL from CDN dynamically
  const s = document.createElement('script');
  s.src = 'https://alcdn.msauth.net/browser/2.38.3/js/msal-browser.min.js';
  s.onload = () => {
    msalInstance = new msal.PublicClientApplication({
      auth:{ clientId: MSAL_CLIENT_ID, authority: MSAL_AUTHORITY, redirectUri: window.location.href.split('?')[0] },
      cache:{ cacheLocation:'sessionStorage' }
    });
    msalInstance.initialize().then(()=>{
      // Check if already signed in
      const accounts = msalInstance.getAllAccounts();
      if(accounts.length > 0){
        acquireToken(accounts[0]).then(token=>{
          graphToken = token;
          setODStatus('✓ Signed in as '+accounts[0].username, '#15803d');
          document.getElementById('btn-signin').style.display = 'none';
        });
      } else {
        document.getElementById('btn-signin').style.display = '';
        setODStatus('Sign in to enable OneDrive save', '#6b7280');
      }
    });
  };
  document.head.appendChild(s);
}

function setODStatus(msg, color){
  const el = document.getElementById('od-status');
  const mel = document.getElementById('modal-od-status');
  if(el){ el.textContent = msg; el.style.color = color||'#6b7280'; }
  if(mel){ mel.textContent = msg; mel.style.color = color||'#6b7280'; }
}

async function acquireToken(account){
  const req = { scopes: GRAPH_SCOPES, account };
  try {
    const res = await msalInstance.acquireTokenSilent(req);
    return res.accessToken;
  } catch(e) {
    const res = await msalInstance.acquireTokenPopup(req);
    return res.accessToken;
  }
}

async function signIn(){
  if(!msalInstance){ initMSAL(); setTimeout(signIn, 1500); return; }
  try {
    const res = await msalInstance.loginPopup({ scopes: GRAPH_SCOPES });
    graphToken = await acquireToken(res.account);
    setODStatus('✓ Signed in as '+res.account.username, '#15803d');
    document.getElementById('btn-signin').style.display = 'none';
    document.getElementById('modal-signin-row').style.display = 'none';
  } catch(e){ setODStatus('Sign-in failed: '+e.message, '#dc2626'); }
}

async function saveToOneDrive(htmlContent, filename, folderPath){
  if(!graphToken){
    setModalSaveStatus('Not signed in to OneDrive — skipping save.','#856404');
    return false;
  }
  try {
    // Ensure folder path exists by creating upload path
    const safePath = folderPath.replace(/^\/+|\/+$/g,'');
    const uploadUrl = `https://graph.microsoft.com/v1.0/me/drive/root:/${safePath}/${filename}:/content`;
    const blob = new Blob([htmlContent], {type:'text/html'});
    const res = await fetch(uploadUrl, {
      method:'PUT',
      headers:{ 'Authorization':'Bearer '+graphToken, 'Content-Type':'text/html' },
      body: blob
    });
    if(res.ok){
      setModalSaveStatus('✓ Saved to OneDrive: '+folderPath+'/'+filename, '#15803d');
      return true;
    } else {
      const err = await res.json();
      setModalSaveStatus('OneDrive save failed: '+(err.error?.message||res.status), '#dc2626');
      return false;
    }
  } catch(e){
    setModalSaveStatus('OneDrive error: '+e.message, '#dc2626');
    return false;
  }
}

function setModalSaveStatus(msg, color){
  const el = document.getElementById('modal-save-status');
  if(el){ el.textContent=msg; el.style.color=color||'#374151'; }
}

function buildFilename(){
  const project = (document.getElementById('work-location').value||'HSSE-Form').trim().replace(/[^a-zA-Z0-9\-_ ]/g,'').trim()||'HSSE-Form';
  const date    = (document.getElementById('job-date').value||new Date().toISOString().slice(0,10)).replace(/-/g,'');
  return `${project}_${date}.html`;
}

// ── SUBMIT ─────────────────────────────────────────────────────────────────────
function openModal(){
  // Check MSAL state
  if(msalInstance){
    const accounts = msalInstance.getAllAccounts();
    document.getElementById('modal-signin-row').style.display = accounts.length ? 'none' : '';
  } else {
    document.getElementById('modal-signin-row').style.display = '';
  }
  document.getElementById('modal-save-status').textContent = '';
  document.getElementById('submit-modal').classList.add('open');
}
function closeModal(){ document.getElementById('submit-modal').classList.remove('open'); }

async function doSubmit(){
  const btn = document.getElementById('btn-save-submit');
  btn.disabled = true; btn.textContent = 'Saving…';
  setModalSaveStatus('','');

  const project  = document.getElementById('work-location').value||'—';
  const date     = document.getElementById('job-date').value||'—';
  const prepBy   = document.getElementById('prepared-by').value||'—';
  const sup      = document.getElementById('approved-sup').value||'—';
  const folder   = (document.getElementById('od-folder').value||'AEPS HSSE Forms/Completed').trim();
  const filename = buildFilename();

  // Build email body
  let body = `HSSE Form E: Daily Job HSSE Plan\n${'='.repeat(48)}\n\n`;
  body += `JP Prepared By: ${prepBy}\nProject:        ${project}\nDate:           ${date}\nSupervisor:     ${sup}\n\n`;
  body += `TASKS & ACKNOWLEDGED HAZARDS\n${'-'.repeat(40)}\n`;
  selectedTasks.forEach(task=>{
    body += `\nTask: ${task}\n`;
    const hz = hazardsFor(task).filter((_,i)=>checkedHazards[`${task}||${i}`]);
    if(hz.length) hz.forEach(h=>body+=`  • [${h.risk}] ${h.category} — ${h.mit}\n`);
    else body += `  (no hazards checked)\n`;
  });
  body += `\n${'='.repeat(48)}\nEmployee: ${document.getElementById('sig-emp-name').value||'—'}\nSupervisor: ${document.getElementById('sig-sup-name').value||'—'}\nSaved as: ${filename}`;

  // Save to OneDrive — capture current page HTML
  const snapshot = '<!DOCTYPE html>\n' + document.documentElement.outerHTML;
  const saved = await saveToOneDrive(snapshot, filename, folder);

  // Send email
  const to = (SETTINGS['Submit Email Address']||'safety@aeps-electric.com').trim();
  const emailTo = document.getElementById('sender-email').value.trim() || to;
  const subject = encodeURIComponent(`HSSE Form E — ${project} — ${date}`);
  window.location.href = `mailto:${to}?subject=${subject}&body=${encodeURIComponent(body)}`;

  btn.disabled = false; btn.textContent = 'Save to OneDrive & email ↗';
  if(saved) setTimeout(()=>closeModal(), 2000);
}

// ── SYNC PREPARER NAME TO BOTTOM SIG ────────────────────────────────────────
function syncPreparer(){
  const sel = document.getElementById('prepared-by');
  const nameField = document.getElementById('sig-emp-name');
  if (!sel || !nameField) return;
  // Strip the role in parentheses e.g. "John Smith (Supervisor)" → "John Smith"
  const val = sel.value || '';
  nameField.value = val.replace(/\s*\([^)]*\)\s*$/, '').trim();
  // Also sync email if we can find it in PERSONNEL
  const person = PERSONNEL.find(p => p.name === nameField.value);
  const emailField = document.getElementById('sig-emp-email');
  if (person && emailField) emailField.value = person.email || '';
}

// ── INIT ──────────────────────────────────────────────────────────────────────
// Update page number display
function updatePageNumber(){
  const el = document.getElementById('page-number');
  if (!el) return;
  // Count how many form-paper divs exist (always 1 for now, but future-proof)
  const pages = document.querySelectorAll('.form-paper').length;
  el.textContent = 'Page 1 of ' + pages;
}
window.addEventListener('beforeprint', ()=>{
  updatePageNumber();
  // Mark task group labels that have at least one checked hazard under them
  document.querySelectorAll('.task-group-label').forEach(label=>{
    let el = label.nextElementSibling;
    let hasChecked = false;
    while(el && !el.classList.contains('task-group-label')){
      if(el.classList.contains('hazard-card') && el.classList.contains('checked')) hasChecked = true;
      el = el.nextElementSibling;
    }
    label.classList.toggle('has-checked', hasChecked);
  });
});
window.addEventListener('afterprint', ()=>{
  document.querySelectorAll('.task-group-label').forEach(l => l.classList.remove('has-checked'));
});

window.addEventListener('load',()=>{
  updatePageNumber();
  const today=new Date().toISOString().slice(0,10);
  document.getElementById('job-date').value=today;
  // Populate dropdowns from embedded data
  populatePersonnelDropdowns();
  refreshCrewDropdowns();
  refreshAllTaskSelects();
  syncPreparer();
  // Build 6 crew rows
  buildCrewRows(6);
  // Bottom sigs
  setTimeout(()=>{
    initSig('sig-employee',56);
    initSig('sig-supervisor',56);
  },100);
  // Init OneDrive (MSAL)
  if(MSAL_CLIENT_ID !== 'YOUR_AZURE_CLIENT_ID_HERE') initMSAL();
  else {
    setODStatus('⚠ Add your Azure Client ID to enable OneDrive save','#856404');
    document.getElementById('btn-signin').style.display='';
  }
});
</script>
</body>
</html>
