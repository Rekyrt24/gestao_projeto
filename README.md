# Gestao Projeto — FieldOps

Este repositório reúne a documentação de planejamento e gestão do **FieldOps**, uma plataforma acadêmica para planejar, executar, sincronizar, revisar e auditar inspeções técnicas realizadas em campo.

O projeto foi desenvolvido no contexto do curso de **Análise e Desenvolvimento de Sistemas do SENAI** e integra três aplicações:

- **Aplicativo mobile:** Expo, React Native, TypeScript e SQLite; utilizado por técnicos em campo, inclusive sem conexão.
- **Painel administrativo web:** Angular e TypeScript; utilizado por administradores e supervisores.
- **API REST:** Java, Spring Boot e PostgreSQL; centraliza autenticação, regras de negócio, persistência, sincronização e auditoria.

## Sobre o produto

O processo tradicional de inspeção pode depender de formulários impressos, planilhas e mensagens. O FieldOps busca concentrar esse fluxo em uma plataforma única, permitindo:

- cadastrar clientes, locais e equipamentos;
- criar modelos versionados de inspeção;
- agendar e atribuir inspeções;
- executar checklists em campo;
- registrar QR Codes, fotografias, localização e não conformidades;
- continuar a execução sem internet;
- sincronizar dados com a API;
- revisar, aprovar ou reprovar inspeções;
- consultar o histórico de mudanças e decisões.

## Conteúdo do repositório

| Arquivo | Conteúdo |
|---|---|
| [`Termo de Abertura de Projeto - FieldOps.docx`](./Termo%20de%20Abertura%20de%20Projeto%20-%20FieldOps.docx) | Documento Word com a autorização formal para iniciar o projeto, incluindo contexto, objetivo e informações iniciais. |
| [`Declaração do Escopo do Projeto - FieldOps.docx`](./Declara%C3%A7%C3%A3o%20do%20Escopo%20do%20Projeto%20-%20FieldOps.docx) | Documento Word que define o escopo do MVP, os resultados esperados e os limites do projeto. |
| [`Matriz_RACI.md`](./Matriz_RACI.md) | Matriz de responsabilidades que relaciona equipes e atividades às funções Responsible, Accountable, Consulted e Informed. |
| [`matriz-poder-interesse.md`](./matriz-poder-interesse.md) | Matriz das partes interessadas, seus níveis de poder e interesse, estratégias de envolvimento e plano de comunicação. |
| [`eap.md`](./eap.md) | Estrutura Analítica do Projeto do FieldOps, com 10 ramos, 34 pacotes de trabalho, dependências, rastreabilidade e inventário das 252 issues do backlog. |
| [`cronograma.md`](./cronograma.md) | Cronograma planejado em 16 semanas e 8 sprints, com entregáveis, marcos, caminho crítico, riscos e verificações de equilíbrio. |
| [`orcamento.md`](./orcamento.md) | Planejamento financeiro do projeto, estimativas de custos e premissas orçamentárias. |
| [`gerenciamento-aquisicoes.md`](./gerenciamento-aquisicoes.md) | Identificação de recursos, ferramentas e fornecedores necessários ao desenvolvimento, testes e demonstração da solução. |
| [`registro_de_riscos.md`](./registro_de_riscos.md) | Registro resumido dos riscos principais e suas informações de acompanhamento. |
| [`riscos.md`](./riscos.md) | Análise mais detalhada dos riscos, incluindo probabilidade, impacto, respostas e monitoramento. |
| [`qualidade.md`](./qualidade.md) | Planejamento da qualidade, padrões, critérios de aceitação, controles e verificações esperadas para o projeto. |

## Planejamento em alto nível

### Estrutura Analítica do Projeto

A EAP organiza o produto em dez áreas principais:

1. Fundação técnica.
2. Identidade e acesso.
3. Cadastros operacionais.
4. Modelos de inspeção.
5. Planejamento de inspeções.
6. Execução de campo.
7. Recursos nativos e evidências.
8. Operação offline e sincronização.
9. Revisão, decisão e qualidade.
10. Entrega e demonstração.

### Cronograma

O planejamento foi dividido em oito sprints de duas semanas:

| Sprint | Semanas | Foco principal |
|---|---|---|
| Sprint 1 | 1–2 | Fundação técnica das aplicações mobile, web e API |
| Sprint 2 | 3–4 | Autenticação e cadastros operacionais |
| Sprint 3 | 5–6 | Modelos de inspeção e agendamento |
| Sprint 4 | 7–8 | Execução do checklist em campo |
| Sprint 5 | 9–10 | QR Code, fotos, localização e não conformidades |
| Sprint 6 | 11–12 | Operação offline, outbox e sincronização |
| Sprint 7 | 13–14 | Revisão, auditoria e testes automatizados |
| Sprint 8 | 15–16 | Dados de demonstração, publicação e documentação final |

O plano contém marcos verificáveis e relaciona todas as entregas aos pacotes da EAP. Os detalhes, incluindo dependências e caminho crítico, estão em [`cronograma.md`](./cronograma.md).

## Arquitetura planejada

```text
Aplicativo Mobile (Expo + React Native)
                |
                | API REST / sincronização
                v
Painel Web (Angular) <-----> API REST (Spring Boot)
                                    |
                                    v
                              PostgreSQL
```

A API atua como camada central de autenticação, autorização, validação, persistência e auditoria. O aplicativo mobile mantém uma base local SQLite e uma fila de operações pendentes para permitir o uso sem conexão.

## Partes interessadas

Os principais participantes e grupos envolvidos são:

- equipe do projeto FieldOps;
- professores orientadores do SENAI;
- representantes da Toyota do Brasil;
- técnicos que executam inspeções;
- gestores e supervisores;
- administradores do sistema;
- equipe de infraestrutura;
- demais usuários e interessados indiretos.

Os papéis de responsabilidade estão documentados em [`Matriz_RACI.md`](./Matriz_RACI.md), enquanto influência, interesse e comunicação estão detalhados em [`matriz-poder-interesse.md`](./matriz-poder-interesse.md).

## Gestão do projeto

Os documentos deste repositório permitem acompanhar diferentes aspectos da gestão:

- **Escopo:** Termo de Abertura e Declaração do Escopo.
- **Responsabilidades:** Matriz RACI.
- **Stakeholders:** Matriz de Poder e Interesse.
- **Estrutura e entregas:** EAP.
- **Tempo:** Cronograma por sprints.
- **Custos:** Orçamento.
- **Aquisições:** Recursos e fornecedores necessários.
- **Riscos:** Identificação, análise e resposta.
- **Qualidade:** Critérios, padrões e verificações.

## Observações

- Os documentos `.docx` são materiais oficiais em formato Word.
- Os arquivos `.md` apresentam o planejamento em formato textual versionável no GitHub.
- Os custos são estimativas acadêmicas e não constituem cotações comerciais confirmadas.
- Algumas premissas e dependências da EAP foram inferidas a partir dos documentos e do backlog. Sempre que necessário, essa natureza está explicitada nos próprios documentos.

## Como navegar pelo repositório

1. Comece pelo **Termo de Abertura** e pela **Declaração do Escopo**.
2. Consulte a **Matriz RACI** e a **Matriz de Poder e Interesse** para entender responsabilidades e comunicação.
3. Leia a **EAP** para conhecer toda a decomposição do projeto.
4. Consulte o **Cronograma** para acompanhar sprints, marcos e dependências.
5. Confira **Orçamento**, **Aquisições**, **Riscos** e **Qualidade** para os planos de controle.
