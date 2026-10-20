# Portal SPO · Resultados do Checklist

Portal com os resultados do **Piloto SPO (Sales Process Optimization)** por unidade. Ele compara a **autoavaliação** da unidade com a **auditoria presencial** da Demarco, pilar a pilar, e mostra os **checklists de campo** lançados pelos auditores no app do piloto.

O portal inteiro está num único arquivo, `index.html`, sem instalação e sem servidor.

## Como abrir

- **No computador:** baixe o repositório e dê dois cliques em `index.html`.
- **Pelo GitHub Pages:** em *Settings → Pages*, escolha a branch `main` e a pasta `/ (root)`. O portal fica disponível em `https://<usuário>.github.io/<repositório>/`.
  - Em conta gratuita, o GitHub Pages só funciona com repositório **público**. Antes de abrir o repositório, veja o aviso sobre dados abaixo.

## O que o portal mostra

**Filtro de unidade** no topo: escolha a unidade e o portal mostra só os dados dela.

### Resultados
- Medidor de aderência ao checklist: auditoria no anel externo, autoavaliação no interno.
- Indicadores de autoavaliação, auditoria e gap (diferença em pontos percentuais).
- Mapa dos 11 pilares com a nota da auditoria e da autoavaliação (0, 1 ou 3). A cor segue a nota da auditoria: verde = 3 (pontua em tudo), amarelo = 1 (pontua em parte), vermelho = 0 (não pontua).
- Um cartão por pilar: primeiro a pergunta (objetivo e itens verificados), depois as notas lado a lado, o critério aplicado e a evidência da visita.
- Filtros: todos, com divergência, abaixo da nota 3.

### Checklists de campo
Registros do app do piloto (auditoria de PDV, matinal, bate-papo GV e RN, GSL, GSR e blitz), com a conformidade média por tipo e cada registro com as respostas e observações.

## Como o resultado é calculado

Cada pilar recebe nota **0, 1 ou 3** e tem um peso (os 11 pesos somam 100). Os pontos do pilar são `peso × nota ÷ 3`, e o resultado é a soma dos pontos. É a mesma conta da planilha *Checklist Auditoria Presencial*.

## Dados incluídos

| Fonte | Conteúdo |
|---|---|
| `Checklist Auditoria Presencial - CDD Fortaleza.xlsx` | Perguntas, pesos, critérios, notas e evidências do CDD Fortaleza |
| `Check List Auditoria Presencial - Checklist - Dunas Aracati.xlsx` | Notas e evidências da Revenda Dunas |
| App Piloto SPO (planilhas `Checklist *.xlsx` e `Piloto SPO.xlsx`) | Checklists de campo até 09/10/2026 |
| `Base Referencia/Unidades.xlsx` | Lista de unidades do filtro |

Os dados estão gravados dentro do `index.html` (cópia de 20/10/2026). Lançamentos novos no app não aparecem sozinhos: é preciso gerar o arquivo de novo.

> **Aviso:** o arquivo contém resultados de unidades, nomes de avaliadores, IDs de funcionários e comentários de visita. Mantenha o repositório **privado**, a menos que esses dados possam ser públicos.

## Recursos ocultos

O portal já tem **login por e-mail e código**, **página de autoavaliação** e **cadastro de usuários**, mas eles estão desligados por enquanto. Para reativar, mude a linha abaixo no `index.html`:

```js
const RECURSOS = { login: false, autoavaliacao: false, usuarios: false };
```

Esses três recursos dependem do banco de dados do portal publicado no claude.ai. Fora dele (no GitHub Pages, por exemplo), eles não funcionam e devem continuar desligados.

---

Demarco · Auditoria · Piloto SPO
