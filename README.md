# Modelo de TCC — IFNMG Campus Salinas

Modelo LaTeX (classe [abnTeX2](https://ctan.org/pkg/abntex2)) para Trabalho de Conclusão de Curso do Bacharelado em Sistemas de Informação, seguindo ABNT NBR 14724:2011, NBR 6028:2021 e NBR 10520:2023.

## Estrutura

O modelo é um TCC de exemplo cuja Fundamentação Teórica descreve os tipos de trabalho do curso. Cada tipo traz caracterização, estrutura típica e um exemplo de figura, quadro, tabela ou equação.

| Caminho | Conteúdo |
|---|---|
| `main.tex` | Preâmbulo, dados do trabalho e elementos pré-textuais |
| `pre-textuais/` | Listas de siglas e símbolos |
| `Capitulos/cap1_introducao.tex` | Introdução: problema, objetivos, justificativa |
| `Capitulos/cap2_fundamentacao.tex` | Fundamentação teórica (inclui os arquivos de `fundamentacao/`) |
| `Capitulos/fundamentacao/` | Uma seção por tipo de trabalho: desenvolvimento de software, pesquisa experimental, survey, estudo de caso, revisão sistemática, outros |
| `Capitulos/cap3_metodologia.tex` | Metodologia comum a todos os tipos |
| `Capitulos/cap4_resultados.tex` | Resultados e discussão |
| `Capitulos/cap5_consideracoes.tex` | Considerações finais |
| `pos-textuais/apendices/` | Guia de uso do LaTeX, documento de requisitos, questionário e TCLE, roteiro de entrevista |
| `pos-textuais/anexos.tex` | Exemplo de anexo (parecer do CEP) |
| `Figuras/` | Imagens (use extensões em minúsculas) |
| `referencias.bib` | Referências (BibTeX) |

## Como usar no seu TCC

1. Leia, no Capítulo 2, a seção do seu tipo de trabalho e a estrutura típica correspondente.
2. Substitua o conteúdo dos capítulos pelo seu texto, mantendo ou ajustando as seções.
3. Se o seu tipo de trabalho pedir um capítulo extra (por exemplo, "Desenvolvimento do sistema" ou "O caso"), crie o arquivo em `Capitulos/` e inclua-o no `main.tex` antes dos resultados.
4. Apague as Seções 1.3 e 1.4 da Introdução (exclusivas do modelo), as seções de tipos que não se aplicam, o Apêndice A (guia) e os apêndices e anexos de exemplo que não usar.
5. Remova do `main.tex` as listas que ficarem vazias (códigos, quadros, símbolos).

## Compilação

Requer TeX Live ou MiKTeX com o abnTeX2. As citações dependem do BibTeX: se aparecerem como **(??)**, o `bibtex` não foi executado.

**VS Code (LaTeX Workshop):** o arquivo `.vscode/settings.json` já define a receita `pdflatex -> bibtex -> pdflatex*2` como padrão para este projeto.

**Terminal:**

```sh
latexmk main.tex
```

Para a versão impressa, com links em preto, troque `\impressaofalse` por `\impressaotrue` no `main.tex`.

**GitHub:** o workflow `.github/workflows/build.yml` compila o PDF a cada push na `main` e em pull requests. O PDF fica em *Actions > execução > Artifacts*; ao criar uma tag `v*`, ele é anexado à *release*.

Sem o latexmk:

```sh
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Antes de entregar

A lista de verificação completa está no Apêndice A (Quadro "Lista de verificação antes da entrega").

- Preencha título, autor, orientador e coorientador (se houver) em `main.tex`.
- Substitua a ficha catalográfica pela fornecida pela biblioteca.
- Substitua a folha de aprovação pela versão assinada após a defesa.
- Remova siglas, símbolos e referências de exemplo que não forem usadas.
- Substitua as imagens de exemplo por imagens próprias ou com fonte e autorização.

## Licença

[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.pt-br). Veja o arquivo `LICENSE`. A licença cobre o modelo; o texto do seu TCC é seu.
