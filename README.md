# Template de TCC em Ciência da Computação - Senac Santo Amaro

Template de Trabalho de Conclusão de Curso (TCC) para o Centro Universitário Senac - Santo Amaro, desenvolvido em LaTeX utilizando a classe `abntex2`. O repositório cobre **TCC1** (proposta) e **TCC2** (trabalho final), cada um com o documento escrito e a apresentação de banca.

## 📋 Sobre o Template

Este template foi desenvolvido para auxiliar os alunos do curso de **Bacharelado em Ciência da Computação** do Senac Santo Amaro na elaboração de seus Trabalhos de Conclusão de Curso, seguindo as normas da ABNT e os padrões acadêmicos da instituição.

## 📁 Estrutura do Repositório

O repositório é organizado em duas pastas independentes:

```
tcc1/                        # TCC1 — proposta do trabalho
├── tcc.tex                  # Documento principal (LaTeX/abntex2)
├── bibliografia.bib         # Referências (BibTeX)
├── apresentacao_tcc1.tex    # Slides da banca (Beamer) — 20 min
├── tcc.pdf                  # PDF gerado
└── assets/                  # Imagens (logo, figuras, diagramas)

tcc2/                        # TCC2 — trabalho final
├── tcc2.tex                 # Documento principal (LaTeX/abntex2)
├── bibliografia_tcc2.bib    # Referências (BibTeX)
├── apresentacao_tcc2.tex    # Slides da banca (Beamer) — 30 min
├── tcc2.pdf                 # PDF gerado
└── assets/                  # Imagens (logo, figuras, diagramas)
```

> Cada pasta é autossuficiente: compile dentro de `tcc1/` ou `tcc2/`.

## 🎯 Elementos Incluídos

### Elementos Pré-textuais

| Elemento | TCC1 | TCC2 |
|---|:---:|:---:|
| Capa | ✅ | ✅ |
| Folha de rosto | ✅ | ✅ |
| Resumo (português) | ✅ | ✅ |
| Abstract (inglês) | — | ✅ (obrigatório) |
| Lista de ilustrações (figuras) | ✅ | ✅ |
| Lista de tabelas | ✅ | ✅ |
| Lista de abreviaturas e siglas | ✅ | ✅ |
| Sumário | ✅ | ✅ |

### Elementos Textuais

**TCC1 — proposta** (a apresentação de banca segue exatamente esta ordem):

1. **Introdução** — Contexto, Justificativa, Objetivos (principal e secundários)
2. **Referencial Bibliográfico** — Metodologia da pesquisa bibliográfica, Referencial, Trabalhos relacionados
3. **Desenvolvimento** — Solução proposta e Cronograma (diagrama de Gantt)

**TCC2 — trabalho final** (estrutura no estilo Wazlawick):

1. **Introdução** — Contextualização, Formulação do problema, Objetivos e hipótese, Justificativa
2. **Revisão Bibliográfica / Trabalhos Relacionados** — Metodologia da pesquisa bibliográfica, Fundamentos teóricos, Trabalhos correlatos
3. **Desenvolvimento** — Metodologia da pesquisa, Detalhes da implementação, Experimentos (opcional), Resultados e análises
4. **Conclusão** — Retomada do problema, Contribuições, Limitações e trabalhos futuros

### Elementos Pós-textuais

- ✅ Referências bibliográficas (geradas via BibTeX, padrão ABNT NBR 6023)
- 💬 Apêndices e Anexos (modelos comentados, prontos para descomentar)

## 🚀 Como Usar

### Organização de imagens

Cada pasta já contém um diretório `assets/` para guardar a logo e as imagens do trabalho. Recomenda-se criar subpastas (ex.: `assets/figures/`) e referenciar com caminhos relativos, por exemplo `assets/figures/arquitetura.png`.

### Pré-requisitos

Você precisará de uma distribuição LaTeX instalada:

- **Windows**: [MiKTeX](https://miktex.org/) ou [TeX Live](https://www.tug.org/texlive/)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: TeX Live (geralmente disponível nos repositórios da distribuição)

#### Instalando no Codespaces/Linux e no Windows

No GitHub Codespaces (ou qualquer Linux atual), instale o TeX Live com:

```bash
sudo apt update
sudo apt install --yes texlive-latex-recommended texlive-fonts-recommended texlive-latex-extra
```

No Windows, instale o MiKTeX (https://miktex.org/download) e, após a instalação, abra o console do MiKTeX para garantir que `pdflatex` está no `PATH`.

> Se usar uma instalação mínima (ex.: TinyTeX), pode ser necessário instalar pacotes adicionais como `abntex2`, `pgfgantt` e `babel-english` (este último é exigido pelo Abstract do TCC2).

### Compilação

Compile dentro da pasta correspondente. Para o **TCC1**:

```bash
cd tcc1
pdflatex tcc.tex
bibtex tcc
pdflatex tcc.tex
pdflatex tcc.tex
```

Para o **TCC2**:

```bash
cd tcc2
pdflatex tcc2.tex
bibtex tcc2
pdflatex tcc2.tex
pdflatex tcc2.tex
```

**Por que compilar múltiplas vezes?**
- A primeira compilação gera o documento base;
- O `bibtex` processa as referências bibliográficas;
- As duas compilações finais atualizam referências cruzadas, sumário e as listas de figuras/tabelas.

## 🎤 Apresentações (Beamer)

Além dos documentos escritos, o repositório inclui templates de **slides** em LaTeX/Beamer para a defesa perante a banca:

- **`tcc1/apresentacao_tcc1.tex`** — apresentação da proposta (TCC1) — **20 minutos**
- **`tcc2/apresentacao_tcc2.tex`** — apresentação final (TCC2) — **30 minutos**

### Regras de tempo

| Etapa | Duração da apresentação | Slides de conteúdo (aprox.) |
|-------|-------------------------|------------------------------|
| **TCC1** | **20 minutos** | 14 a 18 |
| **TCC2** | **30 minutos** | 20 a 26 |

- Cronometre os ensaios — ultrapassar o tempo é penalizado.
- Ritmo de referência: ~1 a 1,5 minuto por slide.
- A apresentação do **TCC1 segue exatamente a estrutura do documento escrito**: Introdução → Referencial Bibliográfico → Desenvolvimento (solução + cronograma).
- O **TCC2** cobre o trabalho completo, com peso especial em **resultados e análise crítica**.
- As regras completas também estão documentadas dentro de cada `.tex` escrito (seção/capítulo *Apresentação oral (banca)*).

### Logo do SENAC

Os templates exibem a **logo grande no primeiro slide (capa)** e a **logo pequena no canto superior direito dos demais slides** — isso já vem configurado.

Para usar a logo oficial, coloque o arquivo em:

```
tcc1/assets/logo-senac.png      # para a apresentação do TCC1
tcc2/assets/logo-senac.png      # para a apresentação do TCC2
```

> Se o arquivo não existir, um marcador de texto (`SENAC`) é exibido no lugar, de modo que a apresentação compila normalmente mesmo sem a imagem.

### Compilando os slides

```bash
cd tcc1                          # ou cd tcc2
pdflatex apresentacao_tcc1.tex
pdflatex apresentacao_tcc1.tex   # 2x para fixar o roteiro e a numeração dos slides
```

O resultado é um PDF de slides em 16:9 (para 4:3, troque `aspectratio=169` por `aspectratio=43` no início do arquivo).

## ✏️ Personalizando o Template

### Informações básicas

Edite, no início de `tcc.tex` (TCC1) ou `tcc2.tex` (TCC2), o bloco **INFORMAÇÕES DO DOCUMENTO**:

```latex
\titulo{Título do Trabalho de Conclusão de Curso}
\autor{Nome Completo do Aluno}
\local{São Paulo}
\data{2025}
\orientador{Prof. Nome do Orientador}
% \coorientador{Prof. Nome do Coorientador} % Descomente se houver coorientador
```

### Resumo e Abstract

Substitua o conteúdo do ambiente `\begin{resumo}` (português) pelo resumo do seu trabalho. No **TCC2**, atualize também o `\begin{resumo}[Abstract]` (inglês), que é **obrigatório**, com a tradução do resumo e as *Keywords*.

### Lista de abreviaturas e siglas

A lista é uma **tabela** (em ordem alfabética). Acrescente ou remova linhas conforme o seu trabalho:

```latex
\begin{tabular}{@{}p{3.2cm}p{0.6\textwidth}@{}}
\toprule
\textbf{Abreviatura/Sigla} & \textbf{Significado} \\
\midrule
ABNT  & Associação Brasileira de Normas Técnicas \\
API   & \textit{Application Programming Interface} \\
TCC   & Trabalho de Conclusão de Curso \\
\bottomrule
\end{tabular}
```

### Conteúdo principal

Edite os capítulos e seções mantendo a estrutura:

```latex
\chapter{Título do Capítulo}
\section{Título da Seção}
\subsection{Título da Subseção}

Seu conteúdo aqui...
```

### Referências bibliográficas

Adicione suas referências no arquivo `.bib` da pasta (`bibliografia.bib` no TCC1, `bibliografia_tcc2.bib` no TCC2), seguindo o formato BibTeX. Exemplos de cada tipo de entrada já estão incluídos.

Para citar no texto:

```latex
\cite{chave}         % (SOBRENOME, ano) — citação indireta
\citeonline{chave}   % Sobrenome (ano) — autor como parte do texto
```

> **Citações (ABNT NBR 10520:2023):** priorize **citações indiretas** (paráfrases). Reserve a citação direta para casos em que a transcrição literal seja indispensável. Há orientações detalhadas, com exemplos, dentro do capítulo de Introdução de cada `.tex`.

## 📦 Pacotes Incluídos

Os documentos já carregam, entre outros:

- **Base ABNT**: `abntex2` (classe) e `abntex2cite` (citações)
- **Formatação**: `indentfirst`, `microtype`, `lmodern`
- **Gráficos e figuras**: `graphicx`, `float`
- **Tabelas**: `booktabs`, `multirow`, `longtable`
- **Matemática**: `amsmath`, `amssymb`
- **Cronograma**: `pgfgantt` (diagramas de Gantt)
- **Referências cruzadas**: `backref` (páginas onde cada obra é citada)

> **Código-fonte:** o pacote `listings` **não** vem carregado por padrão. Se o seu trabalho precisar exibir trechos de código, adicione `\usepackage{listings}` ao preâmbulo e defina os estilos desejados.

### Inserindo figuras

Pela ABNT, o **título** (`\caption`) fica **acima** da figura e a **fonte** (`\legend`) **abaixo** — ambos em 10 pt (já configurado). Por isso o `\caption` e o `\label` vêm **antes** do `\includegraphics`:

```latex
\begin{figure}[htb]
    \centering
    \caption{Legenda da figura}
    \label{fig:minha_figura}
    \includegraphics[width=0.8\textwidth]{assets/figures/imagem.png}
    \legend{Fonte: Elaborado pelo autor (2025)}
\end{figure}
```

Cite a figura no texto com `\ref{fig:minha_figura}`. Toda figura com `\caption` aparece automaticamente na *Lista de ilustrações*.

### Inserindo tabelas

Mesma regra: **título acima**, **fonte abaixo**.

```latex
\begin{table}[htb]
    \centering
    \caption{Título da tabela}
    \label{tab:minha_tabela}
    \begin{tabular}{lcc}
        \toprule
        \textbf{Coluna 1} & \textbf{Coluna 2} & \textbf{Coluna 3} \\
        \midrule
        Dado 1 & Dado 2 & Dado 3 \\
        \bottomrule
    \end{tabular}
    \legend{Fonte: Elaborado pelo autor (2025)}
\end{table}
```

## 📚 Recursos Adicionais

- [Manual do ABNTeX2](https://www.abntex.net.br/)
- [Documentação LaTeX (LaTeX Project)](https://www.latex-project.org/help/documentation/)
- [CTAN - Comprehensive TeX Archive Network](https://www.ctan.org/)
- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX)
- [Guia de referências BibTeX](https://www.bibtex.com/g/bibtex-format/)

## ⚠️ Dicas Importantes

1. **Faça backups regulares** do seu trabalho.
2. **Compile frequentemente** para detectar erros cedo.
3. **Use controle de versão** (Git) para gerenciar alterações.
4. **Consulte seu orientador** regularmente sobre formato e conteúdo.
5. **Revise as normas da ABNT** atualizadas antes da entrega final.
6. **Não deixe para a última hora** — TCC requer tempo e dedicação.

## 🔧 Versionamento com Git

1. Versione os fontes de cada pasta: `*.tex`, o `.bib` e a pasta `assets/`.
2. Revise o status com `git status`, confira diffs (`git diff`) e faça commits com mensagens claras, por exemplo: `git commit -am "Atualiza metodologia proposta"`.
3. Use branches para trabalhar em capítulos diferentes e abra Pull Requests se estiver colaborando.
4. Envie (`git push`) regularmente para o remoto para evitar perda de dados.

### Como funciona o `.gitignore`

O `.gitignore` evita o versionamento de arquivos temporários do LaTeX (`.aux`, `.log`, `.toc`, `.lof`, `.lot`, `.bbl`, `.blg`, `.brf`, `.idx` etc.) e de caches de editores (`.idea/`, `.vscode/`). Assim, ficam no repositório apenas os fontes (`*.tex`, `*.bib`), os ativos e os PDFs gerados.

## 🤝 Suporte

Para dúvidas sobre o template ou formatação:

- Consulte seu orientador de TCC;
- Entre em contato com a coordenação do curso;
- Consulte a documentação do ABNTeX2.

## 📄 Licença

Este template é fornecido para uso acadêmico dos alunos do Centro Universitário Senac - Santo Amaro.

---

**Centro Universitário Senac - Santo Amaro**  
**Curso: Bacharelado em Ciência da Computação**  
**Disciplinas de TCC 1 e TCC 2**
