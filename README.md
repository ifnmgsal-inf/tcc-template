# Modelo de TCC — IFNMG Campus Salinas

Modelo LaTeX (classe [abnTeX2](https://ctan.org/pkg/abntex2)) para Trabalho de Conclusão de Curso do Bacharelado em Sistemas de Informação, seguindo ABNT NBR 14724:2011, NBR 6028:2021 e NBR 10520:2023.

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `main.tex` | Preâmbulo, dados do trabalho e elementos pré-textuais |
| `pre-textuais/` | Listas de siglas e símbolos |
| `Capitulos/` | Um arquivo por capítulo |
| `pos-textuais/` | Apêndices e anexos |
| `Figuras/` | Imagens (use extensões em minúsculas) |
| `referencias.bib` | Referências (BibTeX) |

## Compilação

Requer TeX Live ou MiKTeX com o abnTeX2.

```sh
latexmk main.tex
```

Sem o latexmk:

```sh
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Antes de entregar

- Preencha título, autor, orientador e coorientador (se houver) em `main.tex`.
- Substitua a ficha catalográfica pela fornecida pela biblioteca.
- Substitua a folha de aprovação pela versão assinada após a defesa.
- Remova siglas, símbolos e referências de exemplo que não forem usadas.
- Substitua as imagens de exemplo por imagens próprias ou com fonte e autorização.
