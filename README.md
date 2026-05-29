# Template de TCC em Ciência da Computação - Senac Santo Amaro

Template de Trabalho de Conclusão de Curso (TCC) para o Centro Universitário Senac - Santo Amaro, desenvolvido em LaTeX utilizando a classe `abntex2`.

## 📋 Sobre o Template

Este template foi desenvolvido para auxiliar os alunos do curso de **Bacharelado em Ciência da Computação** do Senac Santo Amaro na elaboração de seus Trabalhos de Conclusão de Curso, seguindo as normas da ABNT e os padrões acadêmicos da instituição.

## 📁 Estrutura do Projeto

O template é composto pelos seguintes arquivos:

- **`tcc.tex`**: Arquivo principal do documento LaTeX contendo toda a estrutura do TCC
- **`bibliografia.bib`**: Arquivo de referências bibliográficas no formato BibTeX

## 🎯 Elementos Incluídos

O template contém as seguintes seções pré-configuradas:

### Elementos Pré-textuais
- ✅ Capa
- ✅ Folha de rosto
- ✅ Dedicatória (opcional)
- ✅ Agradecimentos
- ✅ Epígrafe (opcional)
- ✅ Resumo em português
- ✅ Abstract em inglês
- ✅ Lista de ilustrações
- ✅ Lista de tabelas
- ✅ Lista de abreviaturas e siglas
- ✅ Sumário

### Elementos Textuais
- ✅ Introdução (com contexto, justificativa e objetivos)
- 📝 Desenvolvimento (seções a serem preenchidas pelo aluno)
- 📝 Resultados
- 📝 Conclusão

### Elementos Pós-textuais
- ✅ Referências bibliográficas (utilizando BibTeX)

## 🚀 Como Usar

### Organização de ativos

Crie uma pasta `assets` ao lado de `tcc.tex` para guardar imagens, vídeos ou outras mídias que você irá referenciar. Dentro dela, mantenha subpastas como `images/`, `figures/` ou `media/` e use caminhos relativos (`assets/images/minha_figura.png`) nas figuras do LaTeX.

### Pré-requisitos

Você precisará de uma distribuição LaTeX instalada no seu computador:

- **Windows**: [MiKTeX](https://miktex.org/) ou [TeX Live](https://www.tug.org/texlive/)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: TeX Live (geralmente disponível nos repositórios da distribuição)

#### Instalando `pdflatex` no Codespaces/Linux e no Windows

No GitHub Codespaces (ou qualquer Linux atual), instale o TeX Live com:

```bash
sudo apt update
sudo apt install --yes texlive-latex-recommended texlive-fonts-recommended texlive-latex-extra
```

No Windows, instale o MiKTeX (https://miktex.org/download) e, após a instalação, abra o console do MiKTeX para garantir que `pdflatex` está no `PATH`. Isso garante que `pdflatex` esteja disponível tanto no terminal local quanto no Codespaces.

### Compilação

#### No Terminal

Para compilar o documento, execute os seguintes comandos na ordem:

```bash
pdflatex tcc.tex
bibtex tcc
pdflatex tcc.tex
pdflatex tcc.tex
```

**Por que compilar múltiplas vezes?**
- A primeira compilação gera o documento base
- O `bibtex` processa as referências bibliográficas
- As próximas duas compilações atualizam as referências cruzadas e o sumário

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
cd tcc1                       # ou cd tcc2
pdflatex apresentacao_tcc1.tex
pdflatex apresentacao_tcc1.tex   # 2x para fixar o roteiro e a numeração dos slides
```

O resultado é um PDF de slides em 16:9 (para 4:3, troque `aspectratio=169` por `aspectratio=43` no início do arquivo).

## ✏️ Personalizando o Template

### Informações Básicas

Edite as seguintes linhas no arquivo `tcc.tex` (aproximadamente linhas 75-89):

```latex
\titulo{Título do Seu TCC}
\autor{Seu Nome Completo}
\local{São Paulo - Brasil}
\data{2025}
\orientador{Nome do Seu Orientador}
% \coorientador{Nome do Coorientador} % Descomente se houver coorientador
```

### Resumo e Abstract

Substitua o conteúdo das seções `\begin{resumo}` e `\begin{resumo}[Abstract]` pelos resumos do seu trabalho (entre as linhas 257-299).

### Lista de Siglas

Adicione ou remova siglas na seção `\begin{siglas}` (linhas 318-324):

```latex
\begin{siglas}
  \item[API] Application Programming Interface
  \item[TCC] Trabalho de Conclusão de Curso
\end{siglas}
```

### Conteúdo Principal

Edite os capítulos e seções após a linha 333, mantendo a estrutura:

```latex
\chapter{Título do Capítulo}
\section{Título da Seção}
\subsection{Título da Subseção}

Seu conteúdo aqui...
```

### Referências Bibliográficas

Adicione suas referências no arquivo `bibliografia.bib` seguindo o formato BibTeX. Exemplos já estão incluídos no arquivo.

Para citar uma referência no texto, use:
```latex
\cite{chave_da_referencia}
```

## 📦 Pacotes e Recursos Incluídos

O template já inclui diversos pacotes úteis:

- **Formatação**: `geometry`, `indentfirst`, `microtype`
- **Gráficos e figuras**: `graphicx`, `tikz`, `float`
- **Código-fonte**: `listings` (com estilos pré-configurados para C, R, Python e JSON)
- **Matemática**: `amsmath`
- **Tabelas**: `csvsimple`
- **Citações ABNT**: `abntex2cite`

### Inserindo Código-fonte

O template possui estilos pré-definidos para código:

```latex
\begin{lstlisting}[style=python, caption={Exemplo em Python}]
def hello_world():
    print("Hello, World!")
\end{lstlisting}
```

Estilos disponíveis: `psceudo`, `r_code`, `json`, `python`

### Inserindo Figuras

```latex
\begin{figure}[htb]
    \centering
    \includegraphics[width=0.8\textwidth]{caminho/para/imagem.png}
    \caption{Legenda da figura}
    \label{fig:minha_figura}
\end{figure}
```

### Inserindo Tabelas

```latex
\begin{table}[htb]
    \centering
    \caption{Título da tabela}
    \label{tab:minha_tabela}
    \begin{tabular}{|c|c|c|}
        \hline
        \textbf{Coluna 1} & \textbf{Coluna 2} & \textbf{Coluna 3} \\
        \hline
        Dado 1 & Dado 2 & Dado 3 \\
        \hline
    \end{tabular}
\end{table}
```

## 📚 Recursos Adicionais

### Documentação

- [Manual do ABNTeX2](https://www.abntex.net.br/)
- [Documentação LaTeX (LaTeX Project)](https://www.latex-project.org/help/documentation/)
- [CTAN - Comprehensive TeX Archive Network](https://www.ctan.org/)

### Tutoriais Recomendados

- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX)
- [Guia de referências BibTeX](https://www.bibtex.com/g/bibtex-format/)

## ⚠️ Dicas Importantes

1. **Faça backups regulares** do seu trabalho
2. **Compile frequentemente** para detectar erros cedo
3. **Use controle de versão** (Git) para gerenciar alterações
4. **Consulte seu orientador** regularmente sobre o formato e conteúdo
5. **Revise as normas da ABNT** atualizadas antes da entrega final
6. **Não deixe para a última hora** - TCC requer tempo e dedicação

## 🔧 Versionamento com Git

1. Inicialize um repositório (local ou no GitHub) e versionize `tcc.tex`, `bibliografia.bib` e a pasta `assets/`.
2. Sempre revise o status com `git status`, confira diffs (`git diff`) e faça commits com mensagens claras, por exemplo: `git commit -am "Atualiza metodologia proposta"`.
3. Use branches para trabalhar em capítulos diferentes (`tcc1-metodologia`, `tcc1-referencial` etc.) e abra Pull Requests se estiver colaborando com colegas ou orientador.
4. Envie (`git push`) regularmente para o remoto para evitar perda de dados.
5. Gere o PDF antes de entregas com `pdflatex` + `bibtex` e guarde o binário somente quando necessário; prefira manter no repositório apenas os fontes e ativos.

### Como funciona o `.gitignore`

O arquivo `.gitignore` deste repositório evita que saiam arquivos temporários do LaTeX (como `.aux`, `.log`, `.synctex.gz`, `.toc` etc.) e caches de editores (`.idea/`, `.vscode/`). Desse modo, apenas `*.tex`, `*.bib`, `*.pdf` e os ativos importantes são enviados para o repositório. Consulte o `.gitignore` para entender exatamente o que fica de fora antes de fazer commits.

## 🤝 Suporte

Para dúvidas sobre o template ou formatação:

- Consulte seu orientador de TCC
- Entre em contato com a coordenação do curso
- Consulte a documentação do ABNTeX2

## 📄 Licença

Este template é fornecido para uso acadêmico dos alunos do Centro Universitário Senac - Santo Amaro.

---

**Desenvolvido para a disciplina de TCC 1**  
**Centro Universitário Senac - Santo Amaro**  
**Curso: Bacharelado em Ciência da Computação**
