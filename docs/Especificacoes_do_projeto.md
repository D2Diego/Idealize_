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

# 📚 Requisitos Funcionais Detalhados — Idealize Capital

---

## 1. Onboarding e Cadastro Inicial

### RF-001 — Formulário de Contato e Onboarding
- Usuário preenche **nome, e-mail, empresa, telefone**.
- Após submissão, o sistema envia um **e-mail para o comercial**.
- Usuário é orientado a importar os arquivos iniciais:
  - **Inputs Contas a Receber.xlsx**
  - **Inputs Contas a Pagar.xlsx**
- Cada arquivo deve conter os seguintes campos:

#### Contas a Receber
- Nome do cliente  
- CNPJ ou CPF  
- Recorrente (sim/não)  
- Data de emissão  
- Data de vencimento  
- Valor a receber (R$)

#### Contas a Pagar
- Natureza da despesa (Impostos, Ocupação, Pessoal, Administrativas, Financeiras, Comerciais)
- Recorrente (sim/não)
- Data de emissão
- Data de pagamento
- Valor a pagar (R$)

- **Upload deve validar estrutura** dos arquivos e indicar campos obrigatórios/faltantes.
- Após importação, usuário segue para a próxima etapa do onboarding.

---

## 2. Autenticação e Gestão de Usuários

### RF-002 — Tela de Login
- Autenticação via **e-mail/usuário e senha**.
- Opção de **recuperação de senha** por e-mail.
- Mensagens claras de **erro/sucesso**.

### RF-003 — Gestão de Usuários
- Cadastro de **múltiplos usuários por empresa**.
- Perfis de usuário:
  - **Sócio/Diretor**: acesso total
  - **Financeiro**: inserir/editar/excluir lançamentos, visualizar dashboards
  - **Analista Externo**: visualizar/exportar relatórios, sem acesso a dashboards
  - **Investidor**: visualizar dashboards resumidos
- Controle de permissões e **compra de licenças adicionais**.
- Logar responsável por cada ação (criação, edição, exclusão, exportação, etc).

### RF-004 — Perfil e Configurações Pessoais
- Editar **nome, e-mail, senha e notificações**.
- Exibir perfil ativo.

---

## 3. Importação e Gestão de Dados Financeiros

### RF-005 — Importação de Planilhas
- **Upload de planilhas** de contas a receber/pagar, com validação de estrutura e campos.
- Aceitar **atualização de dados** via novo upload (sobrescrever ou adicionar).
- **Integração futura com API de ERP**.

### RF-006 — Gestão Manual de Lançamentos
- Inclusão, edição e exclusão manual:
  - **Contas a receber**: todos os campos da planilha.
  - **Contas a pagar**: todos os campos da planilha.
- Registro do **usuário responsável**.

### RF-007 — Status dos Lançamentos
- Controle de status:
  - Contas a receber: **pendente, recebido, atrasado**.
  - Contas a pagar: **pendente, pago, atrasado**.
- Alteração **manual ou automática** (data passada sem baixa = “atrasado”).

---

## 4. Dashboard Financeiro e Indicadores

### RF-008 — Dashboard Principal
- Exibir **cards de indicadores**:
  - Fluxo de caixa histórico vs projetado
  - Clientes inadimplentes
  - Saldo atual e futuro
  - Recebimentos e pagamentos futuros programados
  - Prazo médio de recebimento/pagamento
  - Churn rate
  - Risco de concentração de clientes
  - Despesas operacionais categorizadas
- Cada card com ícone **“ℹ️”** para fórmula e definição do indicador.
- Filtros:
  - Período (mês, trimestre, 6 meses, ano)
  - Cliente
  - Natureza de despesa
  - Status (inadimplente, em aberto, recebido, pago, atrasado)

### RF-009 — Detalhamento das Despesas
- Listagem e gráficos de despesas agrupadas por:
  - Impostos (PIS, COFINS, ISS, ICMS, IPI, IRPJ, CSLL)
  - Ocupação (Energia, Água, etc.)
  - Pessoal
  - Administrativas
  - Financeiras
  - Comerciais

### RF-010 — Filtros Avançados
- **Multi-período, multi-cliente e multi-natureza**.
- **Salvar filtros favoritos** para uso recorrente.

---

## 5. Relatórios e Exportações

### RF-011 — Geração e Exportação de Relatórios
- Exportar em **Excel e PDF**:
  - Fluxo de caixa
  - DRE simplificado
  - Contas a receber
  - Contas a pagar
- Relatórios devem conter:
  - Título e subtítulo
  - Período analisado
  - Filtros aplicados
  - Cabeçalho com nomes das colunas
  - Rodapé com **data/hora e usuário**

### RF-012 — Histórico de Exportações
- Registro de exportações (data/hora, usuário, tipo de relatório).

---

## 6. Alertas e Notificações

### RF-013 — Alertas Automáticos
- Configuráveis para:
  - Contas vencidas
  - Saldo projetado insuficiente
  - Churn rate elevado
  - Concentração de receita fora do padrão
  - Contas a pagar não baixadas
- Opções: **notificação interna e e-mail**.

### RF-014 — Configuração de Alertas
- **Ativar/desativar** tipos de alerta.
- Definir **limiares personalizados** (saldo mínimo, % churn, % concentração).

---

## 7. Auditoria e Suporte

### RF-015 — Histórico de Ações e Auditoria
- Registrar:
  - Login/logout
  - Importação de dados
  - Exclusão e edição de lançamentos
  - Exportação de relatórios
  - Gerenciamento de usuários

### RF-016 — Ajuda e Suporte
- **FAQ e formulário de contato**.
- Registro de **tickets** com resposta via sistema e e-mail.

---

## 8. Fluxos de Usuário

**Onboarding:**  
Cadastro → Upload de arquivos → Validação → Criação de usuários → Configuração inicial.

**Operação:**  
Visualização de dashboards → Gestão de lançamentos → Geração de relatórios → Configuração de alertas → Exportações.

**Gestão:**  
Adição/remoção de usuários, permissões, logs de auditoria.

**Suporte:**  
Consulta de dúvidas, abertura de chamados, feedback.

---

## 9. Observações e Regras de Negócio

- Perfis de usuário respeitados em todos os fluxos.
- **Logs detalhados** (usuário, data/hora, tipo de operação).
- **Mensagens de erro amigáveis** para correção de planilhas.
- Dashboard e relatórios com **critérios de cálculo consistentes**.
- **Limite por plano e licenças**, com alertas e opção de upgrade.


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
