Aqui está uma versão aprimorada e com um design mais moderno, elegante e interativo.

O que mudou?
Design Moderno: Adicionado sombras leves (box-shadow), cantos arredondados (border-radius) e um layout responsivo e centralizado.

Botão de Curtir Estilizado: Animação de clique e alteração visual quando ativo (fica vermelho/preenchido e ganha um destaque).

Tags de Categoria e Data: Adicionadas informações extras para dar cara de artigo profissional de blog.

Tratamento de Imagem: Adicionado object-fit: cover para garantir que a imagem não fique distorcida.

1. index.html
HTML
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blog de Tecnologia</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <h1>Curiosidades Tech</h1>
        <p>Explorando a história e o futuro da computação</p>
    </header>

    <main>
        <article class="card">
            <img src="imagem-blog.png" alt="Imagem ilustrativa sobre computação" class="card-img">
            
            <div class="card-conteudo">
                <span class="tag">História da Tech</span>
                <h2>O Surgimento da Computação Moderna</h2>
                <p class="artigo-meta">Por <strong>Nome do Autor</strong> • 15 de Setembro, 2026</p>
                
                <p class="artigo-texto">
                    A primeira parte da história da computação nos mostra como pequenas invenções revolucionaram o mundo.
                    <br><br>
                    Hoje, esses avanços permitem que tenhamos supercomputadores no bolso.
                </p>

                <p class="artigo-fonte">📍 Fonte: <em>The National Museum of Computing</em></p>
                
                <div class="card-acoes">
                    <button class="btn-curtir">
                        <span class="icone">❤️</span> 
                        <span class="contador">0</span>
                    </button>
                </div>
            </div>
        </article>
    </main>

    <script src="script.js"></script>
</body>
</html>
2. style.css
CSS
/* Configurações Globais */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background-color: #F0F4F8;
    color: #183C63;
    padding-bottom: 40px;
}

/* Cabeçalho */
header {
    background-color: #183C63;
    color: #FFFFFF;
    text-align: center;
    padding: 40px 20px;
    margin-bottom: 30px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}

header h1 {
    font-size: 2rem;
    margin-bottom: 8px;
}

header p {
    font-size: 0.95rem;
    opacity: 0.8;
}

/* Container Principal */
main {
    max-width: 800px;
    margin: 0 auto;
    padding: 0 16px;
}

/* Card do Artigo */
.card {
    background-color: #FFFFFF;
    border-radius: 12px;
    padding: 24px;
    display: flex;
    gap: 20px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.08);
}

.card-img {
    width: 100px;
    height: 100px;
    border-radius: 8px;
    object-fit: cover;
    flex-shrink: 0;
}

.card-conteudo {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

/* Tags e Metadados */
.tag {
    align-self: flex-start;
    background-color: #E2E8F0;
    color: #183C63;
    font-size: 0.75rem;
    font-weight: 600;
    padding: 4px 8px;
    border-radius: 4px;
    text-transform: uppercase;
}

h2 {
    font-size: 1.25rem;
    color: #0F2A4A;
}

.artigo-meta {
    font-size: 0.85rem;
    color: #64748B;
}

.artigo-texto {
    font-size: 0.95rem;
    line-height: 1.5;
    color: #334155;
    margin: 8px 0;
}

.artigo-fonte {
    font-size: 0.85rem;
    color: #64748B;
}

/* Botão de Curtir */
.card-acoes {
    margin-top: 12px;
}

.btn-curtir {
    background-color: #F1F5F9;
    border: 1px solid #CBD5E1;
    color: #334155;
    padding: 8px 16px;
    border-radius: 20px;
    cursor: pointer;
    font-size: 0.9rem;
    font-weight: bold;
    display: inline-flex;
    align-items: center;
    gap: 6px;
    transition: all 0.2s ease;
}

.btn-curtir:hover {
    background-color: #E2E8F0;
}

/* Estilo do Botão quando Ativo (Curtido) */
.btn-curtir.ativo {
    background-color: #FEE2E2;
    border-color: #FCA5A5;
    color: #DC2626;
}

/* Responsividade para telas menores */
@media (max-width: 600px) {
    .card {
        flex-direction: column;
        align-items: flex-start;
    }

    .card-img {
        width: 100%;
        height: 160px;
    }
}
3. script.js
JavaScript
const botoesCurtir = document.querySelectorAll(".btn-curtir");

botoesCurtir.forEach(function (botao) {
    let curtiu = false;

    botao.addEventListener("click", function () {
        let contador = botao.querySelector(".contador");
        let valorAtual = Number(contador.textContent);

        if (!curtiu) {
            contador.textContent = valorAtual + 1;
            curtiu = true;
            botao.classList.add("ativo"); // Adiciona classe CSS de ativo
        } else {
            contador.textContent = valorAtual - 1;
            curtiu = false;
            botao.classList.remove("ativo"); // Remove classe CSS de ativo
        }
    });
});
