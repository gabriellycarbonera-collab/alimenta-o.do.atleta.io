# alimenta-o.do.atleta.io
%%html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>AtletaControl</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background: #f4f5f7;
    color: #222;
    transition: 0.3s;
}

body.escuro {
    background: #181a1f;
    color: #eee;
}

.topo {
    background: #222831;
    color: white;
    padding: 20px 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}

.marca {
    display: flex;
    align-items: center;
    gap: 15px;
}

.icone-marca {
    font-size: 40px;
}

.marca h1 {
    font-size: 28px;
}

.marca p {
    color: #cfd3d8;
    margin-top: 5px;
}

.container {
    max-width: 1200px;
    margin: 30px auto;
    padding: 0 20px;
}

.card {
    background: white;
    border-radius: 15px;
    padding: 25px;
    margin-bottom: 25px;
    box-shadow: 0 3px 12px rgba(0,0,0,0.08);
}

body.escuro .card {
    background: #252830;
    color: #eee;
}

.titulo {
    margin-bottom: 20px;
}

.titulo h2 {
    margin-bottom: 7px;
}

.titulo p {
    color: #777;
}

body.escuro .titulo p {
    color: #bbb;
}

.grid-perfil,
.form-grid,
.rotina-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 18px;
}

.campo {
    display: flex;
    flex-direction: column;
    gap: 7px;
}

.campo.grande,
.campo-grande {
    grid-column: span 2;
}

label {
    font-weight: bold;
}

input,
select,
textarea {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 8px;
    font-size: 14px;
    background: white;
    color: #222;
}

body.escuro input,
body.escuro select,
body.escuro textarea {
    background: #30333b;
    color: white;
    border-color: #555;
}

textarea {
    min-height: 90px;
    resize: vertical;
}

.btn {
    border: none;
    padding: 11px 16px;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
    transition: 0.2s;
}

.btn:hover {
    transform: translateY(-1px);
    opacity: 0.9;
}

.btn-primary {
    background: #2563eb;
    color: white;
}

.btn-secondary {
    background: #777;
    color: white;
}

.btn-success {
    background: #16a34a;
    color: white;
}

.btn-danger {
    background: #dc2626;
    color: white;
}

.btn-tema {
    background: #444;
    color: white;
}

.botoes {
    display: flex;
    gap: 10px;
    margin-top: 20px;
}

.dashboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 15px;
    margin-bottom: 25px;
}

.indicador {
    background: white;
    border-radius: 15px;
    padding: 20px;
    display: flex;
    align-items: center;
    gap: 15px;
    box-shadow: 0 3px 12px rgba(0,0,0,0.08);
}

body.escuro .indicador {
    background: #252830;
}

.indicador > span {
    font-size: 30px;
}

.indicador small {
    display: block;
    color: #777;
    margin-bottom: 5px;
}

body.escuro .indicador small {
    color: #bbb;
}

.indicador strong {
    font-size: 22px;
}

.hidratacao {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}

.agua-visual {
    display: flex;
    align-items: center;
    gap: 15px;
    font-size: 25px;
}

.agua-acoes {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
}

.btn-agua {
    background: #0ea5e9;
    color: white;
}

.cabecalho {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    align-items: center;
    margin-bottom: 20px;
}

.acoes {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
}

.filtros {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 15px;
    margin-bottom: 20px;
}

.tabela-container {
    overflow-x: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
}

th,
td {
    padding: 12px;
    border-bottom: 1px solid #ddd;
    text-align: left;
}

body.escuro th,
body.escuro td {
    border-color: #444;
}

th {
    background: #f1f3f5;
}

body.escuro th {
    background: #30333b;
}

.vazio {
    text-align: center;
    padding: 40px;
    color: #777;
}

.vazio span {
    font-size: 40px;
}

.vazio h3 {
    margin: 10px 0;
}

.modal {
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.6);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
}

.modal[hidden] {
    display: none !important;
}

.modal-conteudo {
    background: white;
    color: #222;
    padding: 30px;
    border-radius: 15px;
    width: min(90%, 450px);
    text-align: center;
}

.modal-icone {
    font-size: 40px;
    margin-bottom: 10px;
}

.modal-conteudo p {
    margin: 15px 0 25px;
}

.modal-botoes {
    display: flex;
    justify-content: center;
    gap: 10px;
}

.toast {
    position: fixed;
    bottom: 25px;
    right: 25px;
    background: #222831;
    color: white;
    padding: 15px 20px;
    border-radius: 10px;
    display: none;
    gap: 8px;
    z-index: 2000;
}

footer {
    text-align: center;
    padding: 30px;
    color: #777;
}

@media (max-width: 800px) {

    .dashboard {
        grid-template-columns: repeat(2, 1fr);
    }

    .grid-perfil,
    .form-grid,
    .rotina-grid,
    .filtros {
        grid-template-columns: 1fr;
    }

    .campo.grande,
    .campo-grande {
        grid-column: span 1;
    }

    .cabecalho,
    .hidratacao {
        flex-direction: column;
        align-items: stretch;
    }
}

@media (max-width: 500px) {

    .dashboard {
        grid-template-columns: 1fr;
    }

    .topo {
        flex-direction: column;
        align-items: flex-start;
    }
}
</style>

</head>

<body>

<header class="topo">

    <div class="marca">

        <div class="icone-marca">🏆</div>

        <div>
            <h1>AtletaControl</h1>
            <p>Controle de alimentação e rotina esportiva</p>
        </div>

    </div>

    <button id="btnTema" class="btn btn-tema">
        🌙 Tema escuro
    </button>

</header>


<main class="container">


<!-- PERFIL -->

<section class="card">

    <div class="titulo">

        <h2>👤 Perfil do atleta</h2>

        <p>
            Informações para organização dos registros.
        </p>

    </div>

    <div class="grid-perfil">

        <div class="campo">

            <label>Nome</label>

            <input
                type="text"
                id="atletaNome"
                placeholder="Nome do atleta">

        </div>


        <div class="campo">

            <label>Modalidade</label>

            <input
                type="text"
                id="modalidade"
                placeholder="Ex.: futebol">

        </div>


        <div class="campo">

            <label>Equipe/Clube</label>

            <input
                type="text"
                id="equipe"
                placeholder="Nome da equipe">

        </div>


        <div class="campo">

            <label>Data</label>

            <input
                type="date"
                id="dataRegistro">

        </div>

    </div>

</section>


<!-- RESUMO -->

<section class="dashboard">

    <div class="indicador">

        <span>🍽️</span>

        <div>

            <small>Refeições registradas</small>

            <strong id="totalRefeicoes">0</strong>

        </div>

    </div>


    <div class="indicador">

        <span>💧</span>

        <div>

            <small>Água registrada</small>

            <strong id="aguaTotal">0 ml</strong>

        </div>

    </div>


    <div class="indicador">

        <span>😴</span>

        <div>

            <small>Sono</small>

            <strong id="sonoTotal">--</strong>

        </div>

    </div>


    <div class="indicador">

        <span>⚡</span>

        <div>

            <small>Energia percebida</small>

            <strong id="energiaTotal">--</strong>

        </div>

    </div>

</section>


<!-- REGISTRO DE REFEIÇÃO -->

<section class="card">

    <div class="titulo">

        <h2>🍽️ Registrar refeição</h2>

        <p>
            Registre o que foi consumido e como você se sentiu.
        </p>

    </div>


    <form id="formRefeicao">

        <input type="hidden" id="refeicaoId">

        <div class="form-grid">


            <div class="campo">

                <label>Tipo de refeição *</label>

                <select id="tipoRefeicao" required>

                    <option value="">Selecione</option>

                    <option>Café da manhã</option>
                    <option>Lanche da manhã</option>
                    <option>Almoço</option>
                    <option>Lanche da tarde</option>
                    <option>Jantar</option>
                    <option>Lanche noturno</option>
                    <option>Refeição pré-treino</option>
                    <option>Refeição pós-treino</option>

                </select>

            </div>


            <div class="campo">

                <label>Horário *</label>

                <input
                    type="time"
                    id="horario"
                    required>

            </div>


            <div class="campo grande">

                <label>Alimentos consumidos *</label>

                <input
                    type="text"
                    id="alimentos"
                    placeholder="Ex.: arroz, feijão, legumes..."
                    required>

            </div>


            <div class="campo">

                <label>Porção/quantidade</label>

                <input
                    type="text"
                    id="porcao"
                    placeholder="Ex.: 1 prato">

            </div>


            <div class="campo">

                <label>Antes ou depois do treino?</label>

                <select id="relacaoTreino">

                    <option value="Não informado">
                        Não informado
                    </option>

                    <option value="Antes do treino">
                        Antes do treino
                    </option>

                    <option value="Depois do treino">
                        Depois do treino
                    </option>

                    <option value="Sem relação">
                        Sem relação
                    </option>

                </select>

            </div>


            <div class="campo grande">

                <label>Observações</label>

                <textarea
                    id="observacoes"
                    placeholder="Como se sentiu após a refeição?"></textarea>

            </div>

        </div>


        <div class="botoes">

            <button
                type="submit"
                class="btn btn-primary"
                id="btnSalvar">

                ➕ Registrar refeição

            </button>


            <button
                type="button"
                class="btn btn-secondary"
                id="btnCancelar"
                hidden>

                Cancelar

            </button>

        </div>

    </form>

</section>


<!-- HIDRATAÇÃO -->

<section class="card">

    <div class="titulo">

        <h2>💧 Controle de hidratação</h2>

        <p>
            Registre a ingestão de líquidos ao longo do dia.
        </p>

    </div>


    <div class="hidratacao">

        <div class="agua-contador">

            <div class="agua-visual">

                <span>💧</span>

                <strong id="aguaExibida">
                    0 ml
                </strong>

            </div>

        </div>


        <div class="agua-acoes">

            <button
                type="button"
                class="btn btn-agua"
                data-agua="200">

                + 200 ml

            </button>


            <button
                type="button"
                class="btn btn-agua"
                data-agua="300">

                + 300 ml

            </button>


            <button
                type="button"
                class="btn btn-agua"
                data-agua="500">

                + 500 ml

            </button>


            <button
                type="button"
                class="btn btn-secondary"
                id="btnZerarAgua">

                Zerar

            </button>

        </div>

    </div>

</section>


<!-- ROTINA -->

<section class="card">

    <div class="titulo">

        <h2>😴 Rotina diária</h2>

        <p>
            Registre informações subjetivas da rotina.
        </p>

    </div>


    <div class="rotina-grid">

        <div class="campo">

            <label>Horas de sono</label>

            <input
                type="number"
                id="sono"
                min="0"
                max="24"
                step="0.5"
                placeholder="Ex.: 8">

        </div>


        <div class="campo">

            <label>Energia percebida</label>

            <select id="energia">

                <option value="">Selecione</option>

                <option value="Muito baixa">
                    Muito baixa
                </option>

                <option value="Baixa">
                    Baixa
                </option>

                <option value="Moderada">
                    Moderada
                </option>

                <option value="Boa">
                    Boa
                </option>

                <option value="Muito boa">
                    Muito boa
                </option>

            </select>

        </div>


        <div class="campo campo-grande">

            <label>Observações sobre o dia</label>

            <textarea
                id="observacaoDia"
                placeholder="Ex.: disposição, recuperação, rotina..."></textarea>

        </div>

    </div>


    <button
        type="button"
        id="btnSalvarRotina"
        class="btn btn-primary">

        💾 Salvar rotina

    </button>

</section>


<!-- HISTÓRICO -->

<section class="card">

    <div class="cabecalho">

        <div>

            <h2>📋 Histórico alimentar</h2>

            <p>
                Consulte os registros realizados.
            </p>

        </div>


        <div class="acoes">

            <button
                id="btnExportar"
                class="btn btn-success">

                📥 Exportar CSV

            </button>


            <button
                id="btnImprimir"
                class="btn btn-secondary">

                🖨️ Imprimir

            </button>


            <button
                id="btnLimpar"
                class="btn btn-danger">

                🗑️ Limpar

            </button>

        </div>

    </div>


    <div class="filtros">

        <div class="campo">

            <label>Pesquisar</label>

            <input
                type="search"
                id="pesquisa"
                placeholder="🔎 Alimento ou refeição">

        </div>


        <div class="campo">

            <label>Tipo</label>

            <select id="filtroTipo">

                <option value="todos">Todos</option>

                <option>Café da manhã</option>
                <option>Lanche da manhã</option>
                <option>Almoço</option>
                <option>Lanche da tarde</option>
                <option>Jantar</option>
                <option>Lanche noturno</option>
                <option>Refeição pré-treino</option>
                <option>Refeição pós-treino</option>

            </select>

        </div>

    </div>


    <div class="tabela-container">

        <table>

            <thead>

                <tr>

                    <th>Data</th>
                    <th>Horário</th>
                    <th>Refeição</th>
                    <th>Alimentos</th>
                    <th>Porção</th>
                    <th>Treino</th>
                    <th>Ações</th>

                </tr>

            </thead>

            <tbody id="tabelaRefeicoes"></tbody>

        </table>


        <div
            id="semRegistros"
            class="vazio">

            <span>🍽️</span>

            <h3>Nenhuma refeição registrada</h3>

            <p>
                Utilize o formulário acima para começar.
            </p>

        </div>

    </div>

</section>

</main>


<!-- MODAL -->

<div
    id="modal"
    class="modal"
    hidden>

    <div class="modal-conteudo">

        <div class="modal-icone">
            ⚠️
        </div>

        <h2>Confirmação</h2>

        <p id="modalTexto">
            Deseja realmente apagar todos os registros?
        </p>

        <div class="modal-botoes">

            <button
                type="button"
                id="modalCancelar"
                class="btn btn-secondary">

                Cancelar

            </button>

            <button
                type="button"
                id="modalConfirmar"
                class="btn btn-danger">

                Confirmar

            </button>

        </div>

    </div>

</div>


<!-- TOAST -->

<div
    id="toast"
    class="toast">

    <span id="toastIcon">✅</span>

    <span id="toastTexto">
        Operação realizada.
    </span>

</div>


<footer>

    <strong>AtletaControl</strong>

    <p>
        Sistema de organização alimentar e rotina esportiva.
    </p>

</footer>


<script>

let refeicoes = [];
let agua = 0;
let rotina = {};


// ==========================
// TEMA
// ==========================

const btnTema = document.getElementById("btnTema");

btnTema.addEventListener("click", function() {

    document.body.classList.toggle("escuro");

    if (document.body.classList.contains("escuro")) {

        btnTema.textContent = "☀️ Tema claro";

    } else {

        btnTema.textContent = "🌙 Tema escuro";

    }

});


// ==========================
// TOAST
// ==========================

function mostrarToast(mensagem) {

    const toast = document.getElementById("toast");
    const texto = document.getElementById("toastTexto");

    texto.textContent = mensagem;

    toast.style.display = "flex";

    setTimeout(function() {

        toast.style.display = "none";

    }, 2500);

}


// ==========================
// REFEIÇÕES
// ==========================

const formRefeicao =
    document.getElementById("formRefeicao");

formRefeicao.addEventListener("submit", function(event) {

    event.preventDefault();

    const refeicao = {

        id: Date.now(),

        data:
            document.getElementById("dataRegistro").value,

        horario:
            document.getElementById("horario").value,

        tipo:
            document.getElementById("tipoRefeicao").value,

        alimentos:
            document.getElementById("alimentos").value,

        porcao:
            document.getElementById("porcao").value,

        treino:
            document.getElementById("relacaoTreino").value,

        observacoes:
            document.getElementById("observacoes").value

    };

    refeicoes.push(refeicao);

    atualizarTabela();

    atualizarResumo();

    formRefeicao.reset();

    document.getElementById("dataRegistro").value =
        new Date().toISOString().split("T")[0];

    mostrarToast("Refeição registrada com sucesso! 🍽️");

});


// ==========================
// TABELA
// ==========================

function atualizarTabela() {

    const tabela =
        document.getElementById("tabelaRefeicoes");

    const vazio =
        document.getElementById("semRegistros");

    tabela.innerHTML = "";

    if (refeicoes.length === 0) {

        vazio.style.display = "block";

        return;

    }

    vazio.style.display = "none";


    refeicoes.forEach(function(refeicao) {

        const linha =
            document.createElement("tr");

        linha.innerHTML = `

            <td>${refeicao.data || "--"}</td>

            <td>${refeicao.horario}</td>

            <td>${refeicao.tipo}</td>

            <td>${refeicao.alimentos}</td>

            <td>${refeicao.porcao || "--"}</td>

            <td>${refeicao.treino}</td>

            <td>

                <button
                    type="button"
                    class="btn btn-danger"
                    onclick="excluirRefeicao(${refeicao.id})">

                    🗑️

                </button>

            </td>

        `;

        tabela.appendChild(linha);

    });

}


// ==========================
// EXCLUIR REFEIÇÃO
// ==========================

function excluirRefeicao(id) {

    refeicoes =
        refeicoes.filter(function(item) {

            return item.id !== id;

        });

    atualizarTabela();

    atualizarResumo();

    mostrarToast("Refeição removida.");

}


// ==========================
// RESUMO
// ==========================

function atualizarResumo() {

    document.getElementById("totalRefeicoes")
        .textContent = refeicoes.length;

    document.getElementById("aguaTotal")
        .textContent = agua + " ml";

    document.getElementById("sonoTotal")
        .textContent =
        rotina.sono
        ? rotina.sono + " h"
        : "--";

    document.getElementById("energiaTotal")
        .textContent =
        rotina.energia
        ? rotina.energia
        : "--";

}


// ==========================
// ÁGUA
// ==========================

document.querySelectorAll(".btn-agua")
.forEach(function(botao) {

    botao.addEventListener("click", function() {

        const quantidade =
            Number(botao.dataset.agua);

        agua += quantidade;

        document.getElementById("aguaExibida")
            .textContent = agua + " ml";

        atualizarResumo();

    });

});


document.getElementById("btnZerarAgua")
.addEventListener("click", function() {

    agua = 0;

    document.getElementById("aguaExibida")
        .textContent = "0 ml";

    atualizarResumo();

    mostrarToast("Contador de água zerado.");

});


// ==========================
// ROTINA
// ==========================

document.getElementById("btnSalvarRotina")
.addEventListener("click", function() {

    rotina = {

        sono:
            document.getElementById("sono").value,

        energia:
            document.getElementById("energia").value,

        observacao:
            document.getElementById("observacaoDia").value

    };

    atualizarResumo();

    mostrarToast("Rotina salva com sucesso! 😴");

});


// ==========================
// PESQUISA
// ==========================

document.getElementById("pesquisa")
.addEventListener("input", aplicarFiltros);

document.getElementById("filtroTipo")
.addEventListener("change", aplicarFiltros);


function aplicarFiltros() {

    const pesquisa =
        document.getElementById("pesquisa")
        .value
        .toLowerCase();

    const tipo =
        document.getElementById("filtroTipo")
        .value;

    const linhas =
        document.querySelectorAll("#tabelaRefeicoes tr");


    linhas.forEach(function(linha) {

        const texto =
            linha.textContent.toLowerCase();

        const tipoLinha =
            linha.cells[2]
            ? linha.cells[2].textContent
            : "";

        const correspondePesquisa =
            texto.includes(pesquisa);

        const correspondeTipo =
            tipo === "todos" ||
            tipoLinha === tipo;

        linha.style.display =
            correspondePesquisa &&
            correspondeTipo
            ? ""
            : "none";

    });

}


// ==========================
// EXPORTAR CSV
// ==========================

document.getElementById("btnExportar")
.addEventListener("click", function() {

    if (refeicoes.length === 0) {

        mostrarToast(
            "Não há registros para exportar."
        );

        return;

    }


    let csv =
        "Data,Horário,Refeição,Alimentos,Porção,Treino,Observações\n";


    refeicoes.forEach(function(r) {

        csv += [

            r.data,
            r.horario,
            r.tipo,
            r.alimentos,
            r.porcao,
            r.treino,
            r.observacoes

        ].map(function(valor) {

            return `"${String(valor || "")
                .replace(/"/g, '""')}"`;

        }).join(",") + "\n";

    });


    const blob =
        new Blob([csv], {
            type: "text/csv;charset=utf-8;"
        });


    const url =
        URL.createObjectURL(blob);

    const link =
        document.createElement("a");

    link.href = url;

    link.download =
        "AtletaControl.csv";

    document.body.appendChild(link);

    link.click();

    document.body.removeChild(link);

    URL.revokeObjectURL(url);

    mostrarToast(
        "CSV exportado com sucesso! 📥"
    );

});


// ==========================
// IMPRIMIR
// ==========================

document.getElementById("btnImprimir")
.addEventListener("click", function() {

    window.print();

});


// ==========================
// LIMPAR - CONFIRMAÇÃO
// ==========================

const modal =
    document.getElementById("modal");

const modalConfirmar =
    document.getElementById("modalConfirmar");

const modalCancelar =
    document.getElementById("modalCancelar");


document.getElementById("btnLimpar")
.addEventListener("click", function() {

    if (refeicoes.length === 0) {

        mostrarToast(
            "Não há registros para limpar."
        );

        return;

    }

    modal.hidden = false;

});


// BOTÃO CONFIRMAR

modalConfirmar.addEventListener("click", function() {

    refeicoes = [];

    atualizarTabela();

    atualizarResumo();

    modal.hidden = true;

    mostrarToast(
        "Todos os registros foram apagados."
    );

});


// BOTÃO CANCELAR

modalCancelar.addEventListener("click", function() {

    modal.hidden = true;

});


// FECHAR CLICANDO FORA DA JANELA

modal.addEventListener("click", function(event) {

    if (event.target === modal) {

        modal.hidden = true;

    }

});


// ==========================
// DATA AUTOMÁTICA
// ==========================

const dataHoje =
    new Date()
    .toISOString()
    .split("T")[0];

document.getElementById("dataRegistro")
    .value = dataHoje;


// ==========================
// INICIALIZAÇÃO
// ==========================

atualizarTabela();

atualizarResumo();

</script>

</body>
</html>
