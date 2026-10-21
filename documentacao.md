# Documentação — App Web QA Study Tracker

## 1. Visão geral

O QA Study Tracker é uma aplicação web de apoio ao estudo de temas referentes a Qualidade de Software vistos no curso Mentoria 2.0 do professor Julio de Lima.

A aplicação reúne quatro áreas: **Plano de estudo** (metas com alerta na data e hora), **Revisão** (flashcards), **Exercícios** (com gabarito) e **Conteúdo** (consulta), e deve funcionar em computador e em dispositivo móvel.

Os casos de teste fazem referência às regras de negócio abaixo.

| ID | Regra |
| --- | --- |
| RN1 | A data e hora da meta deve ser futura. |
| RN2 | As horas de estudo por semana devem ser números inteiros de 1 a 20. |
| RN3 | Meta recorrente exige frequência (diária ou semanal). Meta única não tem frequência. |
| RN4 | O exercício só pode ser concluído depois de uma resposta não vazia ser enviada. |
| RN5 | Adiar uma meta exige nova data e hora futuras, com no máximo 3 adiamentos por meta. |

## 2. Técnicas utilizadas e por que foram escolhidas

A escolha parte de uma distinção do Módulo 2: *checking* verifica regras de negócio e critérios de aceite, enquanto *testing* é experimentação mais livre e cognitiva. As regras do app (RN1 a RN5) são simples de verificar. O que mais pede investigação é o comportamento em torno delas: tempo, alertas, dados no navegador, componentes de interface e uso em telas diferentes. Por isso as técnicas abaixo são, em conjunto, exploratórias e orientadas por heurísticas.

### 2.1 Teste exploratório

Teste sem roteiro definido de casos, em que se explora e experimenta o sistema por intuição (Módulo 2). Foi escolhido porque o app tem comportamentos que as regras de negócio não descrevem, como o alerta que depende da data e da hora, a persistência no navegador e o layout em telas diferentes. Sem um passo a passo fixo, é possível encontrar falhas e problemas de experiência do usuário que um roteiro não preveria.

### 2.2 Heurísticas de teste

Heurísticas são maneiras mais pessoais de testar: um conjunto de práticas que dá um norte e ajuda a mapear cenários (Módulo 2). Foram usadas as heurísticas do material do Júlio de Lima (baseado no Test Obsessed, com ideias de Elisabeth Hendrickson, James Lyndsay e Dale Emery) e o HTSM de James Bach.

| Heurística | Por que foi escolhida para o app |
| --- | --- |
| Interrupções | O alerta depende do tempo e os dados ficam no navegador. Recarregar, fechar a aba e deixar a aba em segundo plano podem afetar metas e alertas. |
| Abordagem contrária | O app tem regras com limites (RN1 a RN5). Testar o que o sistema não deveria permitir mostra se as regras realmente são aplicadas. |
| Strings | Título, descrição e respostas dos exercícios são campos de texto livre. |
| Ataques de tipos de dados (datas) | A data e hora são centrais para a RN1 e para o alerta. Dias inexistentes e valores extremos podem quebrar a validação. |
| CRUD e Siga os Dados | Metas são criadas, lidas, adiadas e excluídas, e exercícios e revisão guardam progresso. É preciso garantir a integridade dos dados por onde passam. |
| Heurísticas de UI | O app é uma página única: botão Voltar, atualizar página, alterar a URL e a validação de HTML e CSS podem revelar problemas. |
| HTSM: Platform e Quality Criteria | O exercício exige que o app funcione em computador e em dispositivo móvel. Platform lembra de variar o ambiente, e Usability e Compatibility orientam o que observar. |

### 2.3 ALTR FACE

Heurística do Júlio de Lima para aplicações web modernas, que usam componentes feitos à mão e, por isso, apresentam falhas que não eram comuns com componentes nativos. A sigla é **A**ctivation, **L**ayers, **T**iming, **R**emovable, **F**loat, **A**chievable, **C**ollision e **E**xpansion. Foi escolhida porque o app tem esse tipo de componente: abas, alerta em janela sobreposta, janela de adiamento, mensagens de confirmação que aparecem e somem, e um campo de frequência que depende do tipo da meta. Neste documento foram usadas sete das oito letras (Collision não entrou).

### 2.4 Ferramentas do navegador (Módulo 6)

O Módulo 6 trata acessibilidade, responsividade e performance de frontend como fatores a ver ao testar aplicações web. As ferramentas do Inspecionar dão evidência objetiva: o **Axe DevTools** aponta issues de acessibilidade (padrão WCAG), o **modo responsivo** mostra a tela em diferentes dispositivos e o **Lighthouse** mede a performance (FCP, LCP, TBT, CLS e Speed Index).

## 3. Equipe

- Danielle Hennings
- Ana Anzolin
