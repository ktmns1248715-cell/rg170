<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>KT M&S 기업무선 PTX 골프장 도입 견적서</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<style>
  * { box-sizing: border-box; }
  body {
    font-family: 'Malgun Gothic', 'Apple SD Gothic Neo', sans-serif;
    color: #333333;
    line-height: 1.6;
    margin: 0;
    padding: 24px 0 60px 0;
    background: #e9edf2;
  }

  /* A4 캔버스 (210mm x 297mm) */
  #quotation {
    width: 210mm;
    min-height: 297mm;
    margin: 0 auto;
    background: #ffffff;
    padding: 14mm 14mm;
    box-shadow: 0 4px 18px rgba(0,0,0,0.15);
  }

  .quotation-header {
    text-align: center;
    border-bottom: 3px double #0054a6;
    padding-bottom: 16px;
    margin-bottom: 22px;
  }
  .quotation-header h1 {
    color: #0054a6;
    font-size: 22pt;
    margin: 0 0 8px 0;
    letter-spacing: -1px;
  }
  .quotation-header p { margin: 0; color: #666666; font-size: 10.5pt; }

  .info-table { width: 100%; border-collapse: collapse; margin-bottom: 18px; }
  .info-table td { border: 1px solid #cccccc; padding: 7px 8px; font-size: 9.5pt; vertical-align: middle; }
  .info-table td.label { background-color: #f4f7fa; font-weight: bold; width: 15%; text-align: center; }
  .info-table td.manager-cell strong { display: block; margin-bottom: 3px; }

  .main-title {
    font-size: 12.5pt;
    color: #0054a6;
    font-weight: bold;
    margin-top: 20px;
    margin-bottom: 8px;
    border-left: 4px solid #0054a6;
    padding-left: 8px;
  }

  .data-table { width: 100%; border-collapse: collapse; margin-bottom: 14px; table-layout: fixed; }
  .data-table th, .data-table td { border: 1px solid #dddddd; padding: 8px 4px; text-align: center; font-size: 8.9pt; white-space: nowrap; overflow: visible; }
  .data-table th { background-color: #e6f0fa; color: #111111; font-weight: bold; white-space: normal; font-size: 9pt; }
  .text-right { text-align: right !important; }
  .highlight-text { color: #d9534f; font-weight: bold; }
  .total-row { background-color: #f0f7ff; font-weight: bold; }
  .total-row td { white-space: normal; }
  .data-table td.item-cell {
    white-space: normal;
    text-align: center;
    padding: 6px 8px;
    line-height: 1.35;
  }
  .item-edit {
    width: 100%;
    min-height: 2.4em;
    display: flex;
    align-items: center;
    justify-content: center;
    white-space: normal;
    overflow-wrap: break-word;
    word-break: keep-all;
    text-align: center;
    outline: none;
    background: transparent;
  }
  .item-edit:focus { background: #fffbe0; }

  .legal-notice {
    background-color: #fff9e6;
    border: 1px solid #ffe0b2;
    border-radius: 4px;
    padding: 12px;
    font-size: 9.3pt;
    margin-top: 16px;
    margin-bottom: 18px;
  }

  ul.effects { padding-left: 20px; font-size: 9.5pt; margin-bottom: 20px; }
  ul.effects li { margin-bottom: 4px; }

  .footer-sign {
    margin-top: 34px;
    text-align: center;
    font-size: 12pt;
    font-weight: bold;
    color: #222222;
  }

  /* 입력 필드 스타일 - 종이 위에서는 텍스트처럼 보이도록 */
  .edit {
    width: 100%;
    border: none;
    background: transparent;
    font-family: inherit;
    font-size: inherit;
    color: inherit;
    text-align: inherit;
    font-weight: inherit;
    padding: 0;
  }
  input.edit:focus, div.edit:focus {
    outline: none;
    background: #fffbe0;
  }
  input.qty-input { text-align: center; font-weight: bold; }
  input.money-input { text-align: right; }
  input.date-input {
    text-align: center;
    cursor: pointer;
    font-weight: bold;
    color: #0054a6;
  }
  .amount-cell { white-space: nowrap; padding-right: 8px !important; }
  .amount-cell input { display: inline-block; }
  .discount-inline {
    display: inline-flex;
    align-items: center;
    justify-content: flex-end;
    width: 100%;
    gap: 2px;
  }
  .discount-inline input { width: 55px; text-align: right; }

  /* ---------- 컨트롤 패널 (저장되지 않음) ---------- */
  .control-panel {
    width: 210mm;
    margin: 20px auto 0 auto;
    display: flex;
    justify-content: center;
    gap: 12px;
    flex-wrap: wrap;
  }
  .control-panel button {
    padding: 12px 22px;
    font-size: 11pt;
    font-weight: bold;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    color: #ffffff;
    transition: opacity 0.15s ease;
    font-family: inherit;
  }
  .control-panel button:hover { opacity: 0.85; }
  #btn-jpg { background-color: #0054a6; }
  #btn-pdf { background-color: #d9534f; }
  #btn-reset { background-color: #6c757d; }

  .hint {
    width: 210mm;
    margin: 10px auto 0 auto;
    text-align: center;
    font-size: 9.5pt;
    color: #777;
  }

  @media print {
    body { background: #fff; padding: 0; }
    .control-panel, .hint { display: none; }
    #quotation { box-shadow: none; margin: 0; }
  }
</style>
</head>
<body>

<div id="quotation">

    <div class="quotation-header">
        <h1>모토로라 RG170 도입견적</h1>
        <p>KT M&S 기업무선 PTX 스마트 통신망 전환 제안</p>
    </div>

    <table class="info-table">
        <tr>
            <td class="label">공급 명칭</td>
            <td>
                <div class="edit" id="supplyName" contenteditable="true" style="text-align: center; outline: none; line-height: 1.4;">골프장 경기 운영 혁신을 위한<br>VoLTE 무전기 도입</div>
            </td>
            <td class="label">견적 일자</td>
            <td><input class="edit date-input" type="date" id="quoteDate" value="2026-07-01"></td>
        </tr>
        <tr>
            <td class="label">제안 주관</td>
            <td class="manager-cell">
                <strong>KT M&S 동부법인지사</strong>
                <input class="edit" id="managerInfo" value="김영훈 과장 010-8290-9971">
            </td>
            <td class="label">제안 단말</td>
            <td><input class="edit" id="deviceName" value="모토로라 솔루션 RG170 (WAVE PTX)"></td>
        </tr>
    </table>

    <div class="legal-notice">
        <strong>⚠️ 법적 행정 처분 불이행 리스크 안내 (과기부 정책 고지)</strong><br>
        과학기술정보통신부 정책에 의거하여 현재 귀 사에서 운용 중인 400MHz 아날로그 생활무전기는 <br><strong>2026년 12월 31일부로 대한민국 전역에서 전면 종료(사용 불법화)</strong>됩니다. <br>본 견적은 필수적 무전망 디지털 전환에 따른 자본 지출(CAPEX)을 zero화하기 위한 KT M&S 단독 프로모션 단가입니다.
    </div>

    <div class="main-title">1. 초기 도입 비용 (CAPEX)</div>
    <table class="data-table">
        <colgroup>
            <col style="width:24%;"><col style="width:18%;"><col style="width:18%;"><col style="width:10%;"><col style="width:30%;">
        </colgroup>
        <thead>
            <tr>
                <th>품명 및 규격</th>
                <th>정상 가격</th>
                <th>프로모션 단가</th>
                <th>수량</th>
                <th>공급 가액</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="item-cell"><div class="item-edit" id="deviceSpec" contenteditable="true">모토로라 RG170 <br>(IP69 방수, <br>1.5W 고출력스피커)</div></td>
                <td class="text-right amount-cell">
                    <input class="edit money-input" type="text" inputmode="numeric" id="normalPrice" value="297,000">원
                </td>
                <td class="text-right amount-cell highlight-text">
                    <input class="edit money-input highlight-text" type="text" inputmode="numeric" id="promoPrice" value="0">원
                </td>
                <td>
                    <input class="edit qty-input" type="number" id="qty" min="1" value="60">
                </td>
                <td class="text-right amount-cell" style="font-weight: bold;"><span id="supplyAmount">0</span>원</td>
            </tr>
            <tr class="total-row">
                <td colspan="4">초기 투자비용 합계 (단말기 대금 할인 혜택)</td>
                <td class="text-right highlight-text">총 <span id="capexSaving">0</span>원 절감</td>
            </tr>
        </tbody>
    </table>

    <div class="main-title">2. 월 운영 비용 (OPEX - 3년 약정 기준)</div>
    <table class="data-table">
        <colgroup>
            <col style="width:24%;"><col style="width:16%;"><col style="width:16%;"><col style="width:22%;"><col style="width:22%;">
        </colgroup>
        <thead>
            <tr>
                <th>요금 항목 구성</th>
                <th>정상 월정액</th>
                <th>선택약정 할인액</th>
                <th>대당 월 청구액(VAT 포함)</th>
                <th>전체 기준 총 월정액</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="item-cell"><div class="item-edit" id="planName" contenteditable="true">기업전용 라이트(9,900원)+PTX 부가서비스(5,500원)</div></td>
                <td class="text-right amount-cell">
                    <input class="edit money-input" type="text" inputmode="numeric" id="normalMonthly" value="15,400">원
                </td>
                <td class="amount-cell">
                    <span class="discount-inline">-<input class="edit money-input" type="text" inputmode="numeric" id="discountMonthly" value="2,475">원</span>
                </td>
                <td class="text-right amount-cell highlight-text"><span id="perUnitMonthly">0</span>원</td>
                <td class="text-right amount-cell" style="font-weight: bold;"><span id="totalMonthly">0</span>원</td>
            </tr>
            <tr class="total-row">
                <td colspan="3">연간 총 운영 비용 (타사 PTT 서비스 대비 20% 절감 적용)</td>
                <td colspan="2" class="text-right" style="color: #0054a6;"><span id="annualTotal">0</span>원 / 년</td>
            </tr>
        </tbody>
    </table>

    <div class="main-title">3. 도입 시 독점적 기대 효과</div>
    <ul class="effects">
        <li><strong>음영지역 ZERO 통신망:</strong> KT LTE 전국망 백본망을 사용하여 산악 지형 및 그늘집, 지하에서도 통신 단절 없음.</li>
        <li><strong>골프장 특화 하드웨어:</strong> 카트 주행 소음을 상쇄하는 1.5W 스피커 탑재 및 세차 환경을 견디는 강력한 IP69 방수방진.</li>
        <li><strong>완벽한 보안 및 안전:</strong> AES-256 비화 암호화 기술로 내부 유출 방지 및 경기원 보호용 SOS 긴급 알람 작동.</li>
    </ul>

    <div class="footer-sign">
        KT M&S 동부법인지사 대표이사 (직인생략)
    </div>

</div>

<div class="control-panel">
    <button id="btn-jpg">📷 JPG로 저장</button>
    <button id="btn-pdf">📄 PDF로 저장</button>
    <button id="btn-reset">🔄 수량/조건 초기화</button>
</div>
<div class="hint">수량, 단가, 요금 항목을 직접 클릭해서 수정하면 아래 금액이 자동으로 재계산됩니다. 견적 일자는 클릭하면 달력에서 선택할 수 있습니다.</div>

<script>
  const fmt = (n) => Math.round(n).toLocaleString('ko-KR');
  const toRaw = (str) => (str || '').toString().replace(/[^0-9]/g, '');
  const toFormatted = (raw) => raw ? parseInt(raw, 10).toLocaleString('ko-KR') : '0';

  const els = {
    normalPrice: document.getElementById('normalPrice'),
    promoPrice: document.getElementById('promoPrice'),
    qty: document.getElementById('qty'),
    normalMonthly: document.getElementById('normalMonthly'),
    discountMonthly: document.getElementById('discountMonthly'),
    supplyAmount: document.getElementById('supplyAmount'),
    capexSaving: document.getElementById('capexSaving'),
    perUnitMonthly: document.getElementById('perUnitMonthly'),
    totalMonthly: document.getElementById('totalMonthly'),
    annualTotal: document.getElementById('annualTotal'),
  };

  const moneyInputs = document.querySelectorAll('.money-input');

  const defaults = {
    supplyName: '골프장 경기 운영 혁신을 위한<br>VoLTE 무전기 도입', // 초기화 시 두 줄 유지되도록 수정
    quoteDate: '2026-07-01',
    managerInfo: '김영훈 과장 010-8290-9971',
    deviceName: '모토로라 솔루션 RG170 (WAVE PTX)',
    deviceSpec: '모토로라 RG170 (IP69 방수, 1.5W 고출력 스피커)',
    normalPrice: '297,000',
    promoPrice: '0',
    qty: 60,
    planName: '기업전용 라이트(9,900원)+PTX 부가서비스(5,500원)',
    normalMonthly: '15,400',
    discountMonthly: '2,475',
  };

  function recalc() {
    const normalPrice = parseFloat(toRaw(els.normalPrice.value)) || 0;
    const promoPrice = parseFloat(toRaw(els.promoPrice.value)) || 0;
    const qty = parseFloat(els.qty.value) || 0;
    const normalMonthly = parseFloat(toRaw(els.normalMonthly.value)) || 0;
    const discountMonthly = parseFloat(toRaw(els.discountMonthly.value)) || 0;

    const supplyAmount = promoPrice * qty;
    const capexSaving = (normalPrice - promoPrice) * qty;
    const perUnitMonthly = Math.max(normalMonthly - discountMonthly, 0);
    const totalMonthly = perUnitMonthly * qty;
    const annualTotal = totalMonthly * 12;

    els.supplyAmount.textContent = fmt(supplyAmount);
    els.capexSaving.textContent = fmt(capexSaving);
    els.perUnitMonthly.textContent = fmt(perUnitMonthly);
    els.totalMonthly.textContent = fmt(totalMonthly);
    els.annualTotal.textContent = fmt(annualTotal);
  }

  moneyInputs.forEach(inp => {
    inp.addEventListener('input', recalc);
    inp.addEventListener('blur', () => {
      inp.value = toFormatted(toRaw(inp.value));
      recalc();
    });
  });
  els.qty.addEventListener('input', recalc);

  recalc();

  function formatKoreanDate(isoStr) {
    if (!isoStr) return '';
    const [y, m, d] = isoStr.split('-');
    return `${y}년 ${m}월 ${d}일`;
  }

  function resetAll() {
    document.getElementById('supplyName').innerHTML = defaults.supplyName; // div 구동을 위해 .value에서 .innerHTML로 변경
    document.getElementById('quoteDate').value = defaults.quoteDate;
    document.getElementById('managerInfo').value = defaults.managerInfo;
    document.getElementById('deviceName').value = defaults.deviceName;
    document.getElementById('deviceSpec').textContent = defaults.deviceSpec;
    els.normalPrice.value = defaults.normalPrice;
    els.promoPrice.value = defaults.promoPrice;
    els.qty.value = defaults.qty;
    document.getElementById('planName').textContent = defaults.planName;
    els.normalMonthly.value = defaults.normalMonthly;
    els.discountMonthly.value = defaults.discountMonthly;
    recalc();
  }
  document.getElementById('btn-reset').addEventListener('click', resetAll);

  function captureCanvas() {
    moneyInputs.forEach(inp => { inp.value = toFormatted(toRaw(inp.value)); });
    return html2canvas(document.getElementById('quotation'), {
      scale: 2,
      backgroundColor: '#ffffff',
      useCORS: true,
      onclone: (clonedDoc) => {
        clonedDoc.querySelectorAll('#quotation input').forEach(input => {
          const span = clonedDoc.createElement('span');
          if (input.type === 'date') {
            span.textContent = formatKoreanDate(input.value);
          } else {
            span.textContent = input.value;
          }
          const computed = window.getComputedStyle(input);
          span.style.cssText = computed.cssText;
          span.style.display = 'inline-block';
          span.style.width = input.classList.contains('money-input') && input.id === 'discountMonthly' ? 'auto' : '100%';
          input.parentNode.replaceChild(span, input);
        });
      }
    });
  }

  document.getElementById('btn-jpg').addEventListener('click', async () => {
    const canvas = await captureCanvas();
    const link = document.createElement('a');
    link.download = 'KT_MnS_PTX_견적서.jpg';
    link.href = canvas.toDataURL('image/jpeg', 0.95);
    link.click();
  });

  document.getElementById('btn-pdf').addEventListener('click', async () => {
    const canvas = await captureCanvas();
    const imgData = canvas.toDataURL('image/jpeg', 0.95);
    const { jsPDF } = window.jspdf;
    const pdf = new jsPDF('p', 'mm', 'a4');
    const pdfWidth = pdf.internal.pageSize.getWidth();
    const pdfHeight = (canvas.height * pdfWidth) / canvas.width;
    pdf.addImage(imgData, 'JPEG', 0, 0, pdfWidth, pdfHeight);
    pdf.save('KT_MnS_PTX_견적서.pdf');
  });
</script>

</body>
</html>
