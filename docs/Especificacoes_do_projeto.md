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

# 📚 Requisitos Funcionais Detalhados — Idealize Capital

## 1. Onboarding e Cadastro Inicial

### RF-001 — Formulário de Contato e Onboarding

- Usuário preenche nome, e-mail, empresa, telefone.
- Após submissão, o sistema envia um e-mail para o comercial.
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

- Upload deve validar estrutura dos arquivos e indicar campos obrigatórios/faltantes.
- Após importação, usuário segue para a próxima etapa do onboarding.

---

## 2. Autenticação e Gestão de Usuários

### RF-002 — Tela de Login

- Autenticação via e-mail/usuário e senha.
- Opção de recuperação de senha por e-mail.
- Mensagens claras de erro/sucesso.

### RF-003 — Gestão de Usuários

- Permitir cadastro de múltiplos usuários por empresa.
- Cada usuário com perfil (**Sócio/Diretor**, **Financeiro**, **Analista Externo**, **Investidor**).
- Controle de permissões:
    - **Sócio/Diretor**: acesso total
    - **Financeiro**: inserir/editar/excluir lançamentos, visualizar dashboards
    - **Analista externo**: visualizar/exportar relatórios, sem acesso a dashboards
    - **Investidor**: visualizar dashboards resumidos
- Permitir upgrade (compra) de licenças de usuário adicional.
- Logar responsável por cada ação (quem criou, editou, removeu, exportou, etc).

### RF-004 — Perfil e Configurações Pessoais

- Permitir edição de nome, e-mail, senha e configurações de notificação.
- Exibição do perfil ativo no sistema.

---

## 3. Importação e Gestão de Dados Financeiros

### RF-005 — Importação de Planilhas

- Upload de planilhas de contas a receber/pagar, com validação de estrutura e campos obrigatórios.
- Aceitar atualização de dados via novo upload (sobrescreve ou adiciona dados, conforme opção do usuário).
- Possibilidade de integração futura com API de ERP.

### RF-006 — Gestão Manual de Lançamentos

- Permitir inclusão, edição e exclusão manual de lançamentos:
    - **Contas a receber**: todos os campos da planilha
    - **Contas a pagar**: todos os campos da planilha
- Registro do responsável por cada ação.

### RF-007 — Status dos Lançamentos

- Controle de status:
    - **Contas a receber**: pendente, recebido, atrasado
    - **Contas a pagar**: pendente, pago, atrasado
- Alteração manual ou automática (ex: lançamento com data passada e sem baixa vira “atrasado”).

---

## 4. Dashboard Financeiro e Indicadores

### RF-008 — Dashboard Principal

- Exibir cards de indicadores-chave:
    - Fluxo de caixa histórico vs projetado
    - Clientes inadimplentes
    - Saldo atual e futuro
    - Recebimentos e pagamentos futuros programados
    - Prazo médio de recebimento/pagamento
    - Churn rate
    - Risco de concentração de clientes
    - Despesas operacionais categorizadas
- Cada card deve ter ícone “ℹ️” mostrando:
    - Fórmula de cálculo
    - Definição do indicador
- Possibilitar filtro por:
    - Período (mês, trimestre, 6 meses, ano)
    - Cliente
    - Natureza de despesa
    - Status (inadimplente, em aberto, recebido, pago, atrasado)

### RF-009 — Detalhamento das Despesas

- Listagem e gráficos de despesas agrupadas por categoria:
    - Impostos (PIS, COFINS, ISS, ICMS, IPI, IRPJ, CSLL)
    - Ocupação (Energia, Água, etc.)
    - Pessoal
    - Administrativas
    - Financeiras
    - Comerciais

### RF-010 — Filtros Avançados

- Filtro multi-período, multi-cliente, multi-natureza, com possibilidade de salvar filtros favoritos para uso recorrente.

---

## 5. Relatórios e Exportações

### RF-011 — Geração e Exportação de Relatórios

- Exportar dados (planilhas, gráficos, tabelas) em Excel e PDF.
- Relatórios possíveis:
    - Fluxo de caixa
    - DRE simplificado
    - Contas a receber
    - Contas a pagar
- Relatórios devem conter:
    - Título e subtítulo
    - Período analisado
    - Filtros aplicados
    - Cabeçalho com nomes das colunas
    - Rodapé com data/hora da exportação e usuário responsável

### RF-012 — Histórico de Exportações

- Registrar toda exportação realizada (data/hora, usuário, tipo de relatório).

---

## 6. Alertas e Notificações

### RF-013 — Alertas Automáticos

- Alertas configuráveis para:
    - Contas vencidas
    - Saldo projetado insuficiente
    - Churn rate elevado
    - Concentração de receita fora do padrão
    - Contas a pagar não baixadas
- Opções de recebimento: interface (banner/notificação interna), e-mail.

### RF-014 — Configuração de Alertas

- Usuário pode ativar/desativar tipos de alertas.
- Definir thresholds personalizados por tipo de alerta (ex: saldo mínimo, % churn rate, % concentração de receita).

---

## 7. Auditoria, Suporte e Ajuda

### RF-015 — Histórico de Ações e Auditoria

- Registrar ações críticas:
    - Login/logout
    - Importação de dados
    - Exclusão e edição de lançamentos
    - Geração e exportação de relatórios
    - Gerenciamento de usuários

### RF-016 — Ajuda e Suporte

- FAQ consultável e formulário de contato/suporte.
- Registro de tickets com resposta pelo sistema e por e-mail.

---

## 8. Fluxo de Usuário

**Onboarding:**
- Cadastro → Upload dos arquivos iniciais → Validação → Criação dos usuários → Configuração inicial.

**Operação:**
- Visualização de dashboards → Gestão manual de lançamentos → Geração de relatórios → Configuração de alertas → Exportações.

**Gestão:**
- Adição/remover usuários, ajuste de permissões, visualização de logs de auditoria.

**Suporte:**
- Consulta de dúvidas, abertura de chamados, registro de feedback.

---

## 📝 Observações e Regras de Negócio Importantes

- Perfis de usuário devem ser respeitados em todos os fluxos, impedindo acesso a dashboards sensíveis por analistas externos.
- Logs devem registrar usuário, data/hora e tipo de operação para toda ação relevante.
- Importação de dados deve ser amigável, com mensagens de erro detalhadas para auxiliar o usuário a corrigir planilhas.
- Dashboard e relatórios devem usar os mesmos critérios de cálculo e filtros que as planilhas, garantindo consistência.
- Planos e licenças: Limitar funcionalidades ou número de usuários conforme plano contratado, com mensagens informando o limite e possibilidade de upgrade.

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
