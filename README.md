<html lang="pt-BR">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>Atividade — Peso Cubado </title>
  <style>
    body{font-family:Arial,Helvetica,sans-serif;background:#f4f6f9;color:#17202a;margin:0;padding:18px}
    header{display:flex;gap:12px;align-items:center;background:#003a70;color:#fff;padding:12px;border-radius:8px}
    header img{height:56px;border-radius:6px;background:#fff;padding:4px}
    .container{max-width:980px;margin:18px auto}
    .card{background:#fff;border-radius:8px;padding:14px;margin-bottom:12px;box-shadow:0 4px 14px rgba(2,6,23,0.06)}
    label{font-weight:700;display:block;margin-bottom:6px}
    input[type="text"]{width:100%;padding:8px;border-radius:6px;border:1px solid #d7dce1}
    .question{border:1px solid #e6eef8;background:#fbfdff;padding:12px;border-radius:8px;margin-bottom:12px}
    .sub{font-size:14px;color:#334155;margin-top:6px}
    .opts{margin-top:8px}
    .opts .group{margin-bottom:8px}
    .opts label{display:block;padding:8px;border-radius:6px;cursor:pointer;border:1px solid transparent}
    .opts input{margin-right:8px}
    button{background:#0066c9;color:#fff;padding:10px 14px;border-radius:8px;border:none;font-weight:700;cursor:pointer}
    button.secondary{background:#6b7280;margin-left:8px}
    .result{margin-top:12px;padding:12px;border-radius:8px;background:#eef6ff;border:1px solid #cfe4ff}
    .explain{margin-top:8px;padding:10px;border-radius:6px;background:#fffbea;border:1px solid #fff0b5}
    .small{font-size:13px;color:#475569}
    footer{font-size:13px;color:#475569;margin-top:8px}
    @media(max-width:700px){ header{flex-direction:column;align-items:flex-start} }
  </style>
</head>
<body>
  <header>
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQu4iGmUSMKmbCdNyJ_yf6oPuBfNf0sqiA_0A&s" alt="Logo SENAI">
    <div>
      <div style="font-weight:800;font-size:18px">Atividade: Peso Cubado </div>
      <div class="small">Professor: Luiz Eduardo Peixoto</div>
    </div>
  </header>

  <div class="container">
    <div class="card">
      <label>Nome do aluno</label>
      <input id="aluno" type="text" placeholder="Digite seu nome">
      <div class="small" style="margin-top:8px">
        Observações: todas as medidas nas questões estão em <strong>centímetros (cm)</strong>. Para calcular:
        <ul>
          <li>Converta para metros: <strong>m = cm / 100</strong></li>
          <li>Volume (m³) = comprimento × largura × altura (em metros)</li>
          <li>Peso cubado (kg) = volume (m³) × fator (kg por m³)</li>
        </ul>
        Fatores usados: <strong>Rodoviário = 300 kg/m³</strong>, <strong>Aéreo = 166,7 kg/m³</strong>, <strong>Marítimo = 1000 kg/m³</strong>.
      </div>
      <div style="margin-top:10px">
        <button onclick="corrigir()">Corrigir atividade</button>
        <button class="secondary" onclick="exportarPDF()">Exportar para PDF</button>
      </div>
    </div>

    <!-- QUESTÕES (cada pergunta mostra comprimento, largura e altura em cm) -->
    <div id="quizArea" class="card">

      <!-- Q1 -->
      <div class="question" data-q="1" data-modal="rodoviario" data-factor="300">
        <div><strong>1)</strong> Cenário — Envio de gabinetes (Rodoviário).</div>
        <div class="sub">Cada caixa tem: <strong>comprimento = 40 cm</strong>, <strong>largura = 25 cm</strong>, <strong>altura = 50 cm</strong>. Peso real: <strong>11 kg</strong>. Modal: <strong>Rodoviário</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q1_pv" value="A"> A) Peso cubado ≈ <strong>12 kg</strong></label>
            <label><input type="radio" name="q1_pv" value="B"> B) Peso cubado ≈ <strong>15 kg</strong></label>
            <label><input type="radio" name="q1_pv" value="C"> C) Peso cubado ≈ <strong>30 kg</strong></label>
            <label><input type="radio" name="q1_pv" value="D"> D) Peso cubado ≈ <strong>20 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q1_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q1_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q2 -->
      <div class="question" data-q="2" data-modal="maritimo" data-factor="1000">
        <div><strong>2)</strong> Cenário — Exportação de brinquedos (Marítimo).</div>
        <div class="sub">Cada caixa: <strong>comprimento = 60 cm</strong>, <strong>largura = 50 cm</strong>, <strong>altura = 55 cm</strong>. Peso real: <strong>14 kg</strong>. Modal: <strong>Marítimo</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q2_pv" value="A"> A) Peso cubado ≈ <strong>165 kg</strong></label>
            <label><input type="radio" name="q2_pv" value="B"> B) Peso cubado ≈ <strong>66 kg</strong></label>
            <label><input type="radio" name="q2_pv" value="C"> C) Peso cubado ≈ <strong>99 kg</strong></label>
            <label><input type="radio" name="q2_pv" value="D"> D) Peso cubado ≈ <strong>1 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q2_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q2_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q3 -->
      <div class="question" data-q="3" data-modal="aereo" data-factor="166.7">
        <div><strong>3)</strong> Cenário — Peças automotivas (Aéreo).</div>
        <div class="sub">Cada caixa: <strong>comprimento = 70 cm</strong>, <strong>largura = 45 cm</strong>, <strong>altura = 40 cm</strong>. Peso real: <strong>6 kg</strong>. Modal: <strong>Aéreo</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q3_pv" value="A"> A) Peso cubado ≈ <strong>10 kg</strong></label>
            <label><input type="radio" name="q3_pv" value="B"> B) Peso cubado ≈ <strong>21 kg</strong></label>
            <label><input type="radio" name="q3_pv" value="C"> C) Peso cubado ≈ <strong>18 kg</strong></label>
            <label><input type="radio" name="q3_pv" value="D"> D) Peso cubado ≈ <strong>5 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q3_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q3_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q4 -->
      <div class="question" data-q="4" data-modal="rodoviario" data-factor="300">
        <div><strong>4)</strong> Cenário — Distribuição de mini-fornos (Rodoviário).</div>
        <div class="sub">Cada caixa: <strong>comprimento = 55 cm</strong>, <strong>largura = 50 cm</strong>, <strong>altura = 48 cm</strong>. Peso real: <strong>15 kg</strong>. Modal: <strong>Rodoviário</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q4_pv" value="A"> A) Peso cubado ≈ <strong>39,6 kg</strong></label>
            <label><input type="radio" name="q4_pv" value="B"> B) Peso cubado ≈ <strong>20 kg</strong></label>
            <label><input type="radio" name="q4_pv" value="C"> C) Peso cubado ≈ <strong>30 kg</strong></label>
            <label><input type="radio" name="q4_pv" value="D"> D) Peso cubado ≈ <strong>15 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q4_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q4_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q5 -->
      <div class="question" data-q="5" data-modal="maritimo" data-factor="1000">
        <div><strong>5)</strong> Cenário — Envio de roupas (Marítimo).</div>
        <div class="sub">Cada caixa: <strong>comprimento = 90 cm</strong>, <strong>largura = 60 cm</strong>, <strong>altura = 40 cm</strong>. Peso real: <strong>12 kg</strong>. Modal: <strong>Marítimo</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q5_pv" value="A"> A) Peso cubado ≈ <strong>216 kg</strong></label>
            <label><input type="radio" name="q5_pv" value="B"> B) Peso cubado ≈ <strong>180 kg</strong></label>
            <label><input type="radio" name="q5_pv" value="C"> C) Peso cubado ≈ <strong>40 kg</strong></label>
            <label><input type="radio" name="q5_pv" value="D"> D) Peso cubado ≈ <strong>300 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q5_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q5_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q6 -->
      <div class="question" data-q="6" data-modal="aereo" data-factor="166.7">
        <div><strong>6)</strong> Cenário — Remessa de equipamentos médicos (Aéreo).</div>
        <div class="sub">Cada volume: <strong>comprimento = 35 cm</strong>, <strong>largura = 30 cm</strong>, <strong>altura = 50 cm</strong>. Peso real: <strong>5 kg</strong>. Modal: <strong>Aéreo</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q6_pv" value="A"> A) Peso cubado ≈ <strong>8,75 kg</strong></label>
            <label><input type="radio" name="q6_pv" value="B"> B) Peso cubado ≈ <strong>12 kg</strong></label>
            <label><input type="radio" name="q6_pv" value="C"> C) Peso cubado ≈ <strong>7 kg</strong></label>
            <label><input type="radio" name="q6_pv" value="D"> D) Peso cubado ≈ <strong>20 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q6_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q6_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q7 -->
      <div class="question" data-q="7" data-modal="rodoviario" data-factor="300">
        <div><strong>7)</strong> Cenário — Produtos de limpeza (Rodoviário).</div>
        <div class="sub">Cada caixa: <strong>comprimento = 45 cm</strong>, <strong>largura = 40 cm</strong>, <strong>altura = 60 cm</strong>. Peso real: <strong>10 kg</strong>. Modal: <strong>Rodoviário</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q7_pv" value="A"> A) Peso cubado ≈ <strong>32,4 kg</strong></label>
            <label><input type="radio" name="q7_pv" value="B"> B) Peso cubado ≈ <strong>50 kg</strong></label>
            <label><input type="radio" name="q7_pv" value="C"> C) Peso cubado ≈ <strong>20 kg</strong></label>
            <label><input type="radio" name="q7_pv" value="D"> D) Peso cubado ≈ <strong>40 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q7_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q7_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q8 -->
      <div class="question" data-q="8" data-modal="maritimo" data-factor="1000">
        <div><strong>8)</strong> Cenário — Kits de móveis (Marítimo).</div>
        <div class="sub">Cada embalagem: <strong>comprimento = 120 cm</strong>, <strong>largura = 40 cm</strong>, <strong>altura = 25 cm</strong>. Peso real: <strong>150 kg</strong>. Modal: <strong>Marítimo</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q8_pv" value="A"> A) Peso cubado ≈ <strong>120 kg</strong></label>
            <label><input type="radio" name="q8_pv" value="B"> B) Peso cubado ≈ <strong>100 kg</strong></label>
            <label><input type="radio" name="q8_pv" value="C"> C) Peso cubado ≈ <strong>200 kg</strong></label>
            <label><input type="radio" name="q8_pv" value="D"> D) Peso cubado ≈ <strong>300 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q8_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q8_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q9 -->
      <div class="question" data-q="9" data-modal="aereo" data-factor="166.7">
        <div><strong>9)</strong> Cenário — Painéis eletrônicos (Aéreo).</div>
        <div class="sub">Cada embalagem: <strong>comprimento = 80 cm</strong>, <strong>largura = 30 cm</strong>, <strong>altura = 25 cm</strong>. Peso real: <strong>7 kg</strong>. Modal: <strong>Aéreo</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q9_pv" value="A"> A) Peso cubado ≈ <strong>12 kg</strong></label>
            <label><input type="radio" name="q9_pv" value="B"> B) Peso cubado ≈ <strong>9,6 kg</strong></label>
            <label><input type="radio" name="q9_pv" value="C"> C) Peso cubado ≈ <strong>10 kg</strong></label>
            <label><input type="radio" name="q9_pv" value="D"> D) Peso cubado ≈ <strong>20 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q9_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q9_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

      <!-- Q10 -->
      <div class="question" data-q="10" data-modal="rodoviario" data-factor="300">
        <div><strong>10)</strong> Cenário — Caixa de papelaria (Rodoviário).</div>
        <div class="sub">Cada caixa: <strong>comprimento = 50 cm</strong>, <strong>largura = 45 cm</strong>, <strong>altura = 35 cm</strong>. Peso real: <strong>9 kg</strong>. Modal: <strong>Rodoviário</strong>.</div>

        <div class="opts">
          <div class="group">
            <label><input type="radio" name="q10_pv" value="A"> A) Peso cubado ≈ <strong>23,63 kg</strong></label>
            <label><input type="radio" name="q10_pv" value="B"> B) Peso cubado ≈ <strong>30 kg</strong></label>
            <label><input type="radio" name="q10_pv" value="C"> C) Peso cubado ≈ <strong>15 kg</strong></label>
            <label><input type="radio" name="q10_pv" value="D"> D) Peso cubado ≈ <strong>10 kg</strong></label>
          </div>

          <div class="group">
            <div class="small"><strong>Qual peso será considerado para faturamento?</strong></div>
            <label><input type="radio" name="q10_bill" value="real"> A) Peso real</label>
            <label><input type="radio" name="q10_bill" value="cubado"> B) Peso cubado</label>
          </div>
        </div>
      </div>

    </div>

    <div id="resultado" class="card" style="display:none"></div>

    <footer class="small">
      <div><strong>Como a correção funciona:</strong> para cada questão o sistema calcula (usando as dimensões em cm convertidas para m): <br>
      volume (m³) = (C / 100) × (L / 100) × (A / 100). Em seguida: peso cubado (kg) = volume × fator (kg/m³).</div>
    </footer>
  </div>

  <!-- html2pdf -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.9.3/html2pdf.bundle.min.js"></script>

  <script>
    // Mapeamento de fatores (kg por m³)
    const FACTORS = { 'rodoviario': 300, 'aereo': 166.7, 'maritimo': 1000 };

    // Gabarito calculado (para garantir consistência, vamos calcular aqui os valores "corretos"
    // usando os mesmos parâmetros das div.question: comprimento, largura, altura em cm, fator do modal.)
    function calcularPVporQuestao(div){
      // extrai os textos do enunciado para pegar as medidas e o peso real
      // mas já incluímos as medidas "visualmente" — para segurança vamos ler os atributos data-factor
      const factor = Number(div.getAttribute('data-factor'));
      // ler o texto da sub linha e extrair números (cm) e peso real (kg)
      const sub = div.querySelector('.sub').innerText;
      // extrair comprimento, largura, altura e peso real via regex (assume o formato colocado)
      const cmMatch = sub.match(/comprimento\s*=\s*([\d.,]+)\s*cm.*largura\s*=\s*([\d.,]+)\s*cm.*altura\s*=\s*([\d.,]+)\s*cm/s);
      const pesoMatch = sub.match(/Peso real:\s*([\d.,]+)\s*kg/);
      if(!cmMatch || !pesoMatch) return null;
      const C = Number(cmMatch[1].replace(',', '.'));
      const L = Number(cmMatch[2].replace(',', '.'));
      const A = Number(cmMatch[3].replace(',', '.'));
      const pesoReal = Number(pesoMatch[1].replace(',', '.'));
      // converter para m
      const Cm = C/100, Lm = L/100, Am = A/100;
      const volume_m3 = Cm * Lm * Am;
      const pv = volume_m3 * factor;
      return {pv, pesoReal, volume_m3, factor, C, L, A};
    }

    function corrigir(){
      const resultadoEl = document.getElementById('resultado');
      resultadoEl.style.display = 'block';
      resultadoEl.innerHTML = ''; 
      let totalPV = 0, totalBill = 0, totalQ = 0;
      const questions = document.querySelectorAll('.question');
      const detalhes = [];

      questions.forEach(div=>{
        const qnum = div.getAttribute('data-q');
        const calc = calcularPVporQuestao(div);
        if(!calc) return;
        // arredondar PV para 2 casas para comparação e apresentação
        const pvRounded = Math.round(calc.pv * 100) / 100;
        // opções CV: buscar qual opção foi marcada
        const selPV = div.querySelector(`input[name="q${qnum}_pv"]:checked`);
        const selBill = div.querySelector(`input[name="q${qnum}_bill"]:checked`);
        let okPV = false, okBill = false;
        // tratar caso não respondido
        let chosenPVText = null;
        if(selPV){
          chosenPVText = selPV.parentElement.innerText.trim();
          // extrair número da opção escolhida (procura por número com vírgula ou ponto)
          const numMatch = chosenPVText.match(/([0-9]+[.,]?[0-9]*)\s*kg/);
          if(numMatch){
            const chosenVal = Number(numMatch[1].replace(',', '.'));
            // considerar acerto se diferença < 0.5 kg para evitar problemas de arredondamento pequeno
            if(Math.abs(chosenVal - pvRounded) <= 0.5) okPV = true;
          }
        }

        if(selBill){
          const chosenBill = selBill.value; // 'real' ou 'cubado'
          // determinar faturado: maior entre peso real e pvRounded
          const faturado = (calc.pesoReal >= pvRounded) ? 'real' : 'cubado';
          if(chosenBill === faturado) okBill = true;
        }

        totalQ++;
        if(okPV) totalPV++;
        if(okBill) totalBill++;

        // montar explicação detalhada
        const explan = `
          <div style="margin-bottom:12px;padding:10px;border-radius:6px;background:#ffffff">
            <div style="font-weight:700">Questão ${qnum} — Correção</div>
            <div class="small" style="margin-top:6px">
              Medidas: comprimento = ${calc.C} cm, largura = ${calc.L} cm, altura = ${calc.A} cm.<br>
              Conversão: ${calc.C} cm = ${(calc.C/100).toFixed(3)} m; ${calc.L} cm = ${(calc.L/100).toFixed(3)} m; ${calc.A} cm = ${(calc.A/100).toFixed(3)} m.<br>
              Volume = ${(calc.C/100).toFixed(3)} × ${(calc.L/100).toFixed(3)} × ${(calc.A/100).toFixed(3)} = ${calc.volume_m3.toFixed(6)} m³.<br>
              Fator (kg/m³): ${calc.factor}. Peso cubado calculado = ${calc.volume_m3.toFixed(6)} × ${calc.factor} = <strong>${pvRounded.toFixed(2)} kg</strong>.<br>
              Peso real informado = <strong>${calc.pesoReal.toFixed(2)} kg</strong>.<br>
              <strong>Peso faturado (maior entre real e cubado):</strong> ${ (calc.pesoReal >= pvRounded) ? calc.pesoReal.toFixed(2) + ' kg (peso real)' : pvRounded.toFixed(2) + ' kg (peso cubado)' }.
            </div>
            <div style="margin-top:8px">
              <div><strong>Seu item — Peso cubado:</strong> ${ selPV ? selPV.parentElement.innerText.trim() : '<em>não respondeu</em>' } — ${ okPV ? '<span style="color:green;font-weight:700">Correto</span>' : '<span style="color:red;font-weight:700">Incorreto</span>' }</div>
              <div style="margin-top:6px"><strong>Seu item — Qual será faturado:</strong> ${ selBill ? selBill.parentElement.innerText.trim() : '<em>não respondeu</em>' } — ${ okBill ? '<span style="color:green;font-weight:700">Correto</span>' : '<span style="color:red;font-weight:700">Incorreto</span>' }</div>
            </div>
          </div>
        `;
        detalhes.push(explan);
      });

      // resumo
      const pvScore = Math.round((totalPV/totalQ)*100);
      const billScore = Math.round((totalBill/totalQ)*100);
      const html = `
        <div style="font-weight:800">Resultado final</div>
        <div style="margin-top:8px">Itens corrigidos (peso cubado): <strong>${totalPV}</strong> / ${totalQ} — (${pvScore}%)</div>
        <div style="margin-top:6px">Itens corrigidos (qual será faturado): <strong>${totalBill}</strong> / ${totalQ} — (${billScore}%)</div>
        <div style="margin-top:10px">${detalhes.join('')}</div>
      `;
      resultadoEl.innerHTML = html;
      // rolar até o resultado
      resultadoEl.scrollIntoView({behavior:'smooth'});
    }

    function exportarPDF(){
      const aluno = document.getElementById('aluno').value || 'Aluno';
      const opt = {
        margin:10,
        filename: `${aluno}_atividade_peso_cubado_v2.pdf`,
        image:{type:'jpeg', quality:0.98},
        html2canvas:{scale:2},
        jsPDF:{unit:'mm', format:'a4', orientation:'portrait'}
      };
      html2pdf().set(opt).from(document.body).save();
    }
  </script>
</body>
</html>

