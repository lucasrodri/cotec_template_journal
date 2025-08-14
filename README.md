# Modelo LaTeX ABNT para Revistas Acadêmicas e Científicas

Este repositório contém um **modelo LaTeX** desenvolvido para atender às normas da **ABNT** (NBR 6022, 6023, 10520, entre outras) aplicado ao contexto de revistas acadêmicas e científicas.  
A iniciativa é parte de um esforço do **Instituto Brasileiro de Informação em Ciência e Tecnologia (IBICT)** para **incentivar e facilitar o uso de LaTeX** em periódicos da área de Ciência da Informação e áreas afins.

O modelo oferece uma base pronta para editores e autores produzirem artigos compatíveis com as exigências formais da ABNT, mantendo qualidade tipográfica profissional e automatizando tarefas repetitivas.

---

## 🎯 Objetivos

- **Padronizar** a formatação de artigos acadêmicos conforme as normas da ABNT.
- **Facilitar** o trabalho de autores e editores na submissão e publicação de artigos.
- **Impulsionar** o uso do LaTeX em revistas brasileiras, especialmente nas áreas de Ciência da Informação, Biblioteconomia e áreas correlatas.
- **Oferecer** um template adaptável para diferentes revistas e instituições.

---

## 📋 Funcionalidades

- Estrutura completa para artigos científicos:
  - Título em português, inglês e espanhol.
  - Autores, afiliações, e ORCID.
  - Resumo, abstract e resumen com palavras-chave.
  - Seções e subseções formatadas segundo a ABNT.
  - Figuras, tabelas, equações e algoritmos com legendas e fontes.
- Ambientes de citação (`\citacao`) com formatação para citações longas.
- Suporte para citações e referências conforme ABNT via `abntex2cite`.
- Espaçamento, margens, tipografia e numeração conforme padrões exigidos.
- Modelos prontos para:
  - **Como citar**
  - **Declaração de direitos autorais**
  - **Conflito de interesses**
  - **Fontes de financiamento**
  - **Contribuição dos autores (CRediT taxonomy)**

---

## 📂 Estrutura do Projeto

```
├── modelo.tex # Arquivo principal do artigo
├── estilo.sty # Definições de estilo e formatação
├── referencias.bib # Arquivo BibTeX com referências
├── figuras/ # Pasta para figuras
├── template/ # Imagens e arquivos auxiliares do modelo
└── README.md # Este arquivo
```

## 🚀 Como Usar

1. **Clone este repositório**:

```bash
git clone https://github.com/seuusuario/modelo-abnt-ibict.git
cd modelo-abnt-ibict
```

2. **Compile o projeto usando uma das opções**:

- Overleaf: envie todos os arquivos para um projeto novo.
- Local: use pdflatex ou xelatex + biber:

```bash
xelatex modelo.tex
biber modelo
xelatex modelo.tex
xelatex modelo.tex
```

3. **Personalize os campos de título, autores, resumo, palavras-chave e conteúdo**:

O modelo possui comandos específicos para facilitar a edição e a personalização do artigo:

##### Configuração da Revista

```latex
\setLogoRevista{figuras/logo-revista.png} % Define a logo
\setCheckForUpdatesUrl{http://link.com}   % URL para atualizações
```

##### Dados do Artigo

```latex
\newcommand{\secaoNome}{Seção do Artigo}     % Nome da seção
\newcommand{\editorNome}{Nome completo}      % Nome do editor
\newcommand{\dataRecebido}{31/03/2025}       % Data de recebimento
\newcommand{\dataAprovado}{28/05/2025}       % Data de aprovação
\newcommand{\dataPublicado}{05/06/2025}      % Data de publicação
\newcommand{\pidArtigo}{10.0000/...}         % PID do artigo
\newcommand{\doiArtigo}{https://doi.org/...} % DOI do artigo
```

##### Licenças e Créditos

```latex
\tipoLicenca{CC-BY}     % Tipo de licença Creative Commons
\tipoLicenca{CC-BY-SA}  % (Disponíveis: CC-BY, CC-BY-SA, CC-BY-NC, CC-BY-ND, CC-BY-NC-SA, CC-BY-NC-ND)

\newcommand{\textoLicenca}{...}    % Texto explicativo da licença
\newcommand{\textoCopyright}{...}  % Declaração de direitos
\newcommand{\textoCRediT}{...}     % Créditos CRediT Taxonomy
\newcommand{\textoConflito}{...}   % Declaração de conflitos
\newcommand{\textoFinanciamento}{...} % Financiamento
```

##### Informações dos Autores

```latex
\afiliacao{1}{Instituto X, Departamento Y, Universidade Z}
\afiliacao{2}{Laboratório ABC, Universidade DEF}

\autor{João da}{Silva}{1}{https://orcid.org/...}
\autor{Lucas}{Costa}{2}{https://orcid.org/...}
\autor{José}{Souza}{1}{https://orcid.org/...}

\emailCorrespondencia{email@mail.com} % E-mail do autor de contato
```

##### Título, Resumo e Palavras-chave

- Português
```latex
\newcommand{\monog}{Título do Artigo em Português}
\newcommand{\resumoPT}{Texto do resumo em português...}
\newcommand{\keywordsPT}{termo1; termo2; termo3; termo4; termo5.}
```

- Inglês
```latex
\newcommand{\monogIngles}{Título do artigo em Inglês}
\newcommand{\resumoEN}{Texto do resumo em inglês...}
\newcommand{\keywordsEN}{term1; term2; term3; term4; term5.}
```

- Espanhol
```latex
\newcommand{\monogEspanhol}{Título do artigo em Espanhol}
\newcommand{\resumoES}{Texto do resumo em espanhol...}
\newcommand{\keywordsES}{término1; término2; término3; término4; término5.}
```

##### Como Citar o Artigo

```latex
\newcommand{\comoCitar}{
    \textit{Nome da Revista}, Cidade, v. 23, p. x--xx, 2025.
    DOI: https://doi.org/10.0000/0000-0000-0000.
}
```

##### Bibliografia (BibTeX)

Adicione suas referências no arquivo bibliografia.bib. No final do .tex, inclua:

```latex
\bibliography{bibliografia} % sem extensão
% (opcional) força o estilo; se não declarar, o abntex2cite escolhe automaticamente pelo modo selecionado
%\bibliographystyle{abntex2-alf} % autor-ano
%\bibliographystyle{abntex2-num} % numérico
```

##### Bibliografia (BibTeX) - Campos mais comuns (por tipo)

Regra geral ABNT (estilo autor-ano):

    - Autor(es) separados por and.
    - Título com apenas nomes próprios em maiúsculas (não use ALL CAPS).
    - Cidade (address), editora (publisher) e ano (year) em livros.
    - DOI/URL quando existir; para fontes online, inclua url e urldate (data de acesso, ISO YYYY-MM-DD), que o estilo converte para “Acesso em: …”.

- @article (artigo de periódico) 
-- Campos: author, title, journal, year, volume (opcional), number (opcional), pages (opcional), doi/url (opcionais).

- @inproceedings (artigo em anais/atas)
-- Campos: author, title, booktitle (nome do evento), year, address (cidade do evento), publisher/organization (se houver), pages (opcional).

- @incollection (capítulo de livro)
-- Campos: author, title (capítulo), booktitle (título do livro), editor(es), publisher, address, year, pages (capítulo).

- @book (livro)
-- Campos: author ou editor, title, publisher, address, year, edition (apenas número, ex.: 2), doi/url (opcionais).

- @phdthesis / @mastersthesis (tese/dissertação)
-- Campos: author, title, school (instituição), address (cidade), year, type (ex.: Tese (Doutorado em ...) / Dissertação (Mestrado em ...)).

- @techreport (relatório técnico)
-- Campos: author, title, institution, year, number (se houver), address, url/doi (opcionais).

- @misc / @online (página/site/software/dataset)
-- Campos: author/organization, title, year (se conhecido), url, urldate, note (ex.: versão, commit, etc.).

> **Dica:** no campo edition, informe apenas o número (edition = {2}), e o estilo formata como “2. ed.”.

**Exemplos prontos**

Artigo de periódico: 
```latex
@article{ponciano2018agreement,
  author  = {Ponciano, Leonardo and Brasileiro, Francisco},
  title   = {Agreement-based credibility assessment and task replication in human computation systems},
  journal = {Future Generation Computer Systems},
  year    = {2018},
  volume  = {87},
  pages   = {159--170},
  doi     = {10.1016/j.future.2018.04.058}
}
```

Artigo em anais/atas: 
```latex
@inproceedings{ponciano2017hfcs,
  author    = {Ponciano, Leonardo and Others},
  title     = {Designing for pragmatists and fundamentalists: Privacy concerns and attitudes on the IoT},
  booktitle = {Brazilian Symposium on Human Factors in Computing Systems},
  year      = {2017},
  address   = {Joinville},
  publisher = {ACM},
  pages     = {1--10}
}
```

Capítulo de livro: 
```latex
@incollection{bourdieu2011espaco,
  author    = {Bourdieu, Pierre},
  title     = {Espaço social e espaço simbólico},
  booktitle = {Razões práticas: sobre a teoria da ação},
  editor    = {Bourdieu, Pierre},
  publisher = {Papirus},
  address   = {Campinas},
  year      = {2011},
  pages     = {13--27}
}
```

Livro: 
```latex
@book{arroyo2013oficio,
  author    = {Arroyo, Miguel Gonz{\'a}lez},
  title     = {Of{\'\i}cio de mestre: Imagens e auto-imagens},
  edition   = {15},
  address   = {Petr{\'o}polis},
  publisher = {Vozes},
  year      = {2013}
}
```

Tese / Dissertação: 
```latex
@phdthesis{dickman1996tese,
  author  = {Dickman, Adriana Gomes},
  title   = {Transi{\c{c}}{\~o}es de Fases de N{\~a}o-equil{\'\i}brio em Sistemas de Part{\'\i}culas Interagentes},
  school  = {Universidade Federal de Minas Gerais},
  address = {Belo Horizonte},
  year    = {1996},
  type    = {Tese (Doutorado em F{\'\i}sica)}
}

@mastersthesis{pertence2021dissertacao,
  author  = {Pertence, Maria L{\'u}cia Barbosa},
  title   = {Ensino de f{\'\i}sica para estudantes cegos: Oficina sobre cria{\c{c}}{\~a}o e adapta{\c{c}}{\~a}o de materiais did{\'a}ticos},
  school  = {Pontif{\'\i}cia Universidade Cat{\'o}lica de Minas Gerais},
  address = {Belo Horizonte},
  year    = {2021},
  type    = {Disserta{\c{c}}{\~a}o (Mestrado em Ensino)}
}
```

Relatório técnico: 
```latex
@techreport{instituicao2025relatorio,
  author      = {Sobrenome, Nome and Outro, Autor},
  title       = {Título do relatório técnico},
  institution = {Institui{\c{c}}{\~a}o Respons{\'a}vel},
  number      = {Rel. T{\'e}c. 123/2025},
  address     = {Cidade},
  year        = {2025},
  url         = {https://exemplo.org/relatorio.pdf},
  urldate     = {2025-06-15}
}
```

Recurso online / página: 
```latex
@online{pucminas2019referencias,
  organization = {PUC Minas},
  title   = {Elabora{\c{c}}{\~a}o de refer{\^e}ncias: ABNT NBR 6023},
  year    = {2019},
  url     = {http://portal.pucminas.br/biblioteca/documentos/Guia-ABNT-referencias.pdf},
  urldate = {2025-04-15},
  note    = {Acesso em: 15 abr. 2025}
}
```

**Dicas finais:**

> Use sempre acentos normalmente nos campos BibTeX (o estilo trata a saída).

> Para múltiplos autores, separe com and: author = {Silva, Jo{\~a}o and Costa, Lucas and Souza, Jos{\'e}}.

> Prefira doi quando existir; caso contrário use url + urldate.

>Em capítulos e anais, não repita o nome do livro/evento em title; use booktitle.

## ✍️ Exemplos de Citação no Texto

- Parêntese: ... 

```latex
\cite{ponciano2018agreement}. → (Ponciano; Brasileiro, 2018)
```

- Narrativa: ... 

```latex
\citeonline{ponciano2018agreement} mostram que ... → Ponciano e Brasileiro (2018) mostram que...
```

- Citação longa:

```latex
\begin{citacao}
Texto recuado, fonte menor e espaçamento simples.
\end{citacao}
```

## 📝 Licença

Este modelo é distribuído sob a licença Creative Commons Attribution (CC BY), permitindo uso, distribuição e adaptação, desde que seja dado o devido crédito.

## 📣 Créditos

Desenvolvido no âmbito do Instituto Brasileiro de Informação em Ciência e Tecnologia (IBICT), com inspiração e adaptações baseadas em modelos ABNT existentes, para apoiar editores, revisores e autores na produção de artigos científicos de alta qualidade tipográfica.

## ✉️ Dúvidas ou sugestões:

> Para dúvidas ou sugestões, abra uma issue no repositório ou entre em contato.
