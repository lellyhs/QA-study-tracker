# QA Study Tracker

Aplicação web de apoio aos estudos de Quality Assurance e testes de software. Reúne plano de estudo, revisão em flashcards, exercícios com gabarito e uma aba de consulta do conteúdo do curso.

Projeto desenvolvido como exercício da mentoria de testes de software do Júlio de Lima (Modelagem, Documentação e Execução de Testes). O app é o **objeto de teste** do exercício: ele será testado manualmente, com documentação e reporte de defeitos.

## Como abrir

É uma página única, sem instalação e sem dependências.

1. Baixe o arquivo `index.html` (ou `qa-study-tracker.html`).
2. Abra no navegador (duplo clique ou arrastando para uma janela do navegador).
3. Funciona em computador e em celular.

## Funcionalidades

### Plano
- Cadastro de metas de estudo com título, assunto, horas por semana, tipo (única ou recorrente), frequência, data/hora e descrição.
- Lista de metas ordenada da mais próxima para a mais distante.
- Quando a data/hora chega, um alerta permite **marcar como vista** ou **adiar** para uma nova data.
- Metas recorrentes, quando concluídas, são reagendadas (+1 dia para diária, +7 dias para semanal).

### Revisão
- Flashcards com pergunta e resposta, filtráveis por assunto.
- "Lembrei" remove o cartão da sessão. "Errei" faz o cartão voltar poucos cartões depois.
- Contador acumulado de acertos e erros.

### Exercícios
- 16 exercícios com gabarito.
- O gabarito só aparece depois de enviar uma resposta, e só então é possível marcar o exercício como concluído.

### Conteúdo
- Consulta de todos os cartões agrupados por assunto, com busca por texto.

## Assuntos cobertos

| Grupo | Conteúdo |
|---|---|
| Módulo 1 | O testador, definições de teste, testes x qualidade, Gherkin, automação, IA Gen, riscos |
| Módulo 2 | Checking x testing, exploratório, charter, partição de equivalência, valor limite, tabela de decisão, cobertura, Jira/Zephyr |
| Módulo 3 | Cascata, Scrum e Kanban, papéis, atuação do QA nas cerimônias ágeis, DOR e DOD |
| Templates | Condições de teste, caso de teste, defeito e relatório de sessão |
| Módulo 4 | Heurística VADER, testes de API, Mocha, SuperTest, Chai, Git, mochawesome, dotenv |
| Módulo 5 | Performance, ISO 25010, RNFs, estatística (desvio padrão, mediana, linha dos 90), k6 |
| Heurísticas | Heurísticas do Júlio, ALTR FACE e Heuristic Test Strategy Model (James Bach) |
| SBTM | Artigo de Jonathan Bach sobre Session-Based Test Management |

Total: 123 flashcards e 16 exercícios.

## Regras de negócio

Regras definidas para permitir a aplicação das técnicas de modelagem de testes.

| ID | Regra |
|---|---|
| RN1 | A data/hora da meta deve ser futura (agora ou passado é rejeitado). |
| RN2 | As horas de estudo por semana devem ser números inteiros de 1 a 20. |
| RN3 | Meta recorrente exige frequência (diária ou semanal). Meta única não tem frequência. |
| RN4 | O exercício só pode ser concluído depois de uma resposta não vazia ser enviada. |
| RN5 | Adiar uma meta exige nova data/hora futura, com no máximo 3 adiamentos por meta. |

## Requisitos do exercício

- Site em HTML, formato Single Page, com CSS e JavaScript no mesmo arquivo.
- Armazenamento no próprio navegador (`localStorage`).
- Esquema de cores originalmente escuro com tons de laranja. O professor liberou um visual alternativo, e a versão atual usa um tema claro e suave, inspirado em caça-bugs (fundo de caderno, fichas de estudo e mascote de joaninha com lupa).
- Funciona em desktop e em dispositivos móveis.
- Sem testes automatizados (o teste é manual).

## Limitações conhecidas

- Os alertas só disparam **com a página aberta**. Não há backend nem notificações do sistema.
- Os dados ficam no navegador e são **separados por endereço**. Dados salvos ao abrir o arquivo localmente não aparecem na versão publicada (por exemplo, no GitHub Pages), e vice-versa.
- Limpar os dados do navegador apaga metas e progresso.
- Abrir o app em mais de uma aba pode gerar inconsistências.
- O conteúdo dos cartões vem exclusivamente dos resumos e materiais do curso.

## Documentação de testes

_A preencher durante a execução do exercício._

- Condições de teste: _link_
- Casos de teste: _link_
- Relatórios de sessão: _link_
- Defeitos encontrados: _link_

## Publicar no GitHub Pages (opcional)

1. Deixe o arquivo na raiz do repositório com o nome `index.html`.
2. No repositório, vá em **Settings > Pages**.
3. Em **Branch**, escolha `main` e a pasta raiz.
4. Salve e aguarde o link ser gerado.
