# 📋 Especificação do Projeto

---

## 👥 Personas

### 1️⃣ **João, Administrador e Proprietário de Empresa**

- **Idade:** 40 anos  
- **Ocupação:** Proprietário e Administrador de uma empresa prestadora de serviços  
- **Desafios:** Sobrecarga operacional e falta de ferramentas eficazes para gestão financeira, resultando em atraso de pagamentos, dívidas desnecessárias e perda de oportunidades estratégicas.
- **Objetivos:** Melhorar o controle financeiro da empresa, reduzir custos operacionais e aumentar a rentabilidade.
- **Motivação:** Ter visibilidade clara sobre indicadores financeiros essenciais e simplificar processos administrativos.

### 2️⃣ **Fernanda, Analista Financeira Externa**

- **Idade:** 32 anos  
- **Ocupação:** Analista financeira terceirizada (contabilidade externa)  
- **Desafios:** Recebe informações financeiras de clientes de forma desorganizada, em diferentes formatos e frequentemente atrasadas, dificultando relatórios contábeis e aumentando tempo gasto com tarefas operacionais.
- **Objetivos:** Receber e analisar dados financeiros dos clientes rapidamente e de maneira padronizada.
- **Motivação:** Melhorar a eficiência e qualidade dos serviços prestados, aumentando a satisfação do cliente.

### 3️⃣ **Carlos, Sócio Investidor**

- **Idade:** 45 anos  
- **Ocupação:** Investidor e sócio em empresas de pequeno porte  
- **Desafios:** Dificuldade em acompanhar indicadores financeiros e desempenho das empresas em que investe, dificultando decisões ágeis e assertivas.
- **Objetivos:** Ter acesso fácil e rápido a dashboards financeiros das empresas em que investe.
- **Motivação:** Garantir retorno consistente e minimizar riscos financeiros.

---

## 📖 Histórias de Usuários

| EU COMO... `PERSONA` | QUERO/PRECISO ... `FUNCIONALIDADE` | PARA ... `MOTIVO/VALOR` |
|----------------------|------------------------------------|-------------------------|
| João - Administrador | Visualizar previsões financeiras claras (receitas, inadimplência e caixa futuro) | Tomar decisões estratégicas assertivas |
| João - Administrador | Acessar dashboard intuitivo sobre a saúde financeira | Entender rapidamente o desempenho da empresa |
| João - Administrador | Gerar relatórios contábeis rapidamente | Simplificar e otimizar processos administrativos |
| João - Administrador | Acompanhar indicadores financeiros chave regularmente | Realizar ações corretivas eficazes |
| Fernanda - Analista Externa | Receber relatórios financeiros padronizados rapidamente | Melhorar eficiência e qualidade do atendimento |
| Carlos - Sócio Investidor | Visualizar dashboards com indicadores financeiros resumidos | Facilitar o acompanhamento financeiro e decisões |

---

## ✅ Requisitos Funcionais

| ID     | Descrição Detalhada                                                                                                                        | Prioridade |
|--------|---------------------------------------------------------------------------------------------------------------------------------------------|------------|
| RF-001 | **Formulário de Contato / Onboarding**  
Permitir que potenciais clientes preencham formulário (nome, e-mail, empresa, telefone) para abertura de conta e disparo de fluxo comercial. | Alta       |
| RF-002 | **Cadastro Simplificado de Empresas**  
Cadastrar e gerenciar dados da empresa (nome, CNPJ, endereço, faturamento mensal, responsáveis financeiros).                                    | Alta       |
| RF-003 | **Tela de Login e Autenticação**  
Autenticar usuários por e-mail/usuário e senha, com recuperação de senha via e-mail.                                                            | Alta       |
| RF-004 | **Dashboard Financeiro**  
Exibir indicadores-chave:  
  - Fluxo de caixa histórico vs. projetado  
  - Clientes inadimplentes  
  - Saldo atual e futuro  
  - Recebimentos e pagamentos futuros programados  
  - Prazo médio de recebimento/pagamento  
  - Churn rate e risco de concentração de clientes  
  - Detalhamento de despesas operacionais categorizadas  
Cada card deve ter ícone “ℹ️” com fórmula e definição.                  | Alta       |
| RF-005 | **Contas a Receber**  
Importar planilha Excel com histórico; inclusão manual de lançamentos futuros; gerenciamento de status (pendente/recebido/atrasado).         | Alta       |
| RF-006 | **Contas a Pagar**  
Importar planilha Excel com histórico; inclusão manual de lançamentos futuros; gerenciamento de status (pendente/pago/atrasado).             | Alta       |
| RF-007 | **Geração de Relatórios Contábeis**  
Gerar e exportar relatórios formatados (PDF, Excel) com base em período selecionado, prontos para envio à contabilidade.                         | Alta       |
| RF-008 | **Notificações e Alertas**  
Disparar alertas automáticos via interface (e opcionalmente e-mail) para: vencimentos de contas, pagamentos atrasados, inadimplências críticas e saldo baixo projetado. | Média      |
| RF-009 | **Gestão de Usuários e Permissões**  
Criar/editar usuários, controlar níveis de acesso e habilitar cobrança adicional por usuário extra (controle de licenças).                        | Média      |
| RF-010 | **Perfil & Configurações Pessoais**  
Permitir que cada usuário edite seus dados de perfil, altere senha e configure notificações.                                                    | Média      |
| RF-011 | **Ajuda & Suporte Integrado**  
Disponibilizar sessão de FAQ e formulário de contato interno para suporte, registro de tickets ou envio de dúvidas.                                | Baixa      |
| RF-012 | **Auditoria e Histórico de Ações**  
Manter log de operações críticas (login/logout, importação de dados, geração de relatórios, alterações de usuário) para auditoria futura.         | Baixa      |

---

✨ Estes requisitos complementam os itens básicos, adicionando inteligência, automação e colaboração avançada para diferenciar o **Idealize Capital** como uma solução de próxima geração em gestão financeira.  


---

## ⚙️ Requisitos Não Funcionais

| ID      | Descrição do Requisito | Prioridade |
|---------|-------------------------|------------|
| RNF-001 | Plataforma simples, intuitiva e fácil de usar. | Alta |
| RNF-002 | Design visual harmonioso, limpo e atrativo. | Alta |
| RNF-003 | Responsividade (dashboard adaptado para celular após MVP). | Média |
| RNF-004 | Integração inicial com planilhas Excel para importação de dados. | Alta |

---

## 🚫 Restrições

| ID | Restrição |
|----|-----------|
| 01 | Acesso inicial à plataforma via cadastro manual após contato prévio. |
| 02 | Plataforma destinada inicialmente apenas a empresas prestadoras de serviços. |
| 03 | Orçamento limitado para desenvolvimento. |

---

## 🎯 Grupos de Usuários

- **Administradores e Sócios:** Acesso total às informações financeiras da empresa, com cobrança por usuário adicional.
- **Analistas Financeiros Externos:** Acesso restrito aos relatórios financeiros gerados.
- **Sócios Investidores:** Visualização de dashboards financeiros resumidos.

---

## 🛣️ Jornada do Usuário Principal

1. Preenchimento inicial do formulário de contato.
2. Apresentação detalhada da plataforma aos sócios interessados.
3. Período de teste gratuito por 7 dias.
4. Assinatura pós período de testes.
5. Onboarding inicial com importação facilitada de dados financeiros via Excel.
6. Uso contínuo para gestão financeira diária e tomada de decisões estratégicas.

---

✨ **Fim da Especificação do Projeto** ✨
