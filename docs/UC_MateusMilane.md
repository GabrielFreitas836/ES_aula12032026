# Casos de Uso – FitPass Gym Management

## UC01 – Cadastrar Aluno

**Atores:**  
Recepcionista

**Pré-condições**

- Recepcionista autenticado no sistema.

**Pós-condições**

- Aluno cadastrado no sistema.

**Fluxo Principal**

1. Recepcionista acessa a opção “Cadastrar Aluno”.
2. Sistema solicita os dados do aluno.
3. Recepcionista informa os dados necessários.
4. Sistema valida as informações.
5. Sistema registra o aluno no banco de dados.
6. Sistema confirma o cadastro.

**Fluxos Alternativos**

**A1 – Dados inválidos**

1. Sistema informa erro nos dados informados.
2. Recepcionista corrige as informações.

**Requisitos Funcionais Relacionados**

- RF01 – Cadastro de alunos

**Requisitos Não Funcionais Relacionados**

- RNF01 – Tempo de resposta inferior a 2 segundos.

**Regras de Negócio**

- RN01 – Cada aluno deve possuir CPF único.

---

## UC02 – Atualizar Cadastro de Aluno

**Atores**

Recepcionista

**Pré-condições**

- Aluno já cadastrado.

**Pós-condições**

- Dados atualizados no sistema.

**Fluxo Principal**

1. Recepcionista busca aluno.
2. Sistema exibe dados cadastrados.
3. Recepcionista altera informações.
4. Sistema salva alterações.

**Fluxos Alternativos**

**A1 – Aluno não encontrado**

1. Sistema informa que o aluno não foi localizado.

---

## UC03 – Realizar Matrícula

**Atores**

Recepcionista

**Pré-condições**

- Aluno cadastrado.

**Pós-condições**

- Matrícula registrada.

**Fluxo Principal**

1. Recepcionista seleciona aluno.
2. Sistema exibe planos disponíveis.
3. Recepcionista escolhe plano.
4. Sistema registra matrícula.

---

## UC04 – Cancelar Matrícula

**Atores**

Recepcionista

**Pré-condições**

- Aluno matriculado.

**Pós-condições**

- Matrícula cancelada.

**Fluxo Principal**

1. Recepcionista seleciona matrícula.
2. Sistema solicita confirmação.
3. Recepcionista confirma.
4. Sistema cancela matrícula.

---

## UC05 – Registrar Pagamento

**Atores**

Recepcionista

**Pré-condições**

- Matrícula ativa.

**Pós-condições**

- Pagamento registrado.

**Fluxo Principal**

1. Recepcionista seleciona aluno.
2. Sistema apresenta valores pendentes.
3. Recepcionista registra pagamento.
4. Sistema confirma pagamento.

---

## UC06 – Consultar Situação Financeira

**Atores**

- Recepcionista
- Gerente

**Fluxo Principal**

1. Usuário busca aluno.
2. Sistema mostra pagamentos realizados e pendentes.

---

## UC07 – Liberar Acesso na Catraca

**Atores**

- Aluno
- Sistema de Catraca (API)

**Pré-condições**

- Aluno com matrícula ativa.

**Fluxo Principal**

1. Aluno aproxima cartão RFID.
2. Sistema envia requisição à API da catraca.
3. Sistema verifica situação da matrícula.
4. Sistema libera acesso.

---

## UC08 – Bloquear Acesso por Inadimplência

**Atores**

Sistema

**Fluxo Principal**

1. Sistema identifica pagamento atrasado.
2. Sistema bloqueia acesso na catraca.

---

## UC09 – Cadastrar Plano

**Atores**

Gerente

**Fluxo Principal**

1. Gerente acessa gestão de planos.
2. Gerente informa nome, preço e duração.
3. Sistema registra plano.

---

## UC10 – Alterar Plano

**Atores**

Gerente

**Fluxo Principal**

1. Gerente seleciona plano.
2. Sistema exibe informações.
3. Gerente altera dados.
4. Sistema salva alterações.

---

## UC11 – Cancelar Plano

**Atores**

Gerente

**Fluxo Principal**

1. Gerente seleciona plano.
2. Sistema solicita confirmação.
3. Plano é cancelado.

---

## UC12 – Agendar Aula

**Atores**

Aluno

**Fluxo Principal**

1. Aluno acessa agenda.
2. Sistema mostra aulas disponíveis.
3. Aluno seleciona aula.
4. Sistema registra agendamento.

---

## UC13 – Cancelar Agendamento

**Atores**

Aluno

**Fluxo Principal**

1. Aluno acessa agendamentos.
2. Seleciona aula.
3. Sistema cancela agendamento.

---

## UC14 – Cadastrar Aula

**Atores**

- Instrutor
- Gerente

**Fluxo Principal**

1. Instrutor cria aula.
2. Define horário e capacidade.
3. Sistema registra aula.

---

## UC15 – Registrar Presença em Aula

**Atores**

Instrutor

**Fluxo Principal**

1. Instrutor abre lista de presença.
2. Marca alunos presentes.
3. Sistema registra presença.

---

## UC16 – Cadastrar Avaliação Física

**Atores**

Instrutor

**Fluxo Principal**

1. Instrutor seleciona aluno.
2. Informa dados físicos.
3. Sistema salva avaliação.

---

## UC17 – Consultar Avaliação Física

**Atores**

- Aluno
- Instrutor

**Fluxo Principal**

1. Usuário seleciona aluno.
2. Sistema mostra histórico de avaliações.

---

## UC18 – Gerar Relatório de Alunos

**Atores**

Gerente

**Fluxo Principal**

1. Gerente acessa relatórios.
2. Sistema gera relatório de alunos cadastrados.

---

## UC19 – Gerar Relatório Financeiro

**Atores**

Gerente

**Fluxo Principal**

1. Gerente seleciona período.
2. Sistema gera relatório financeiro.

---

## UC20 – Gerenciar Instrutores

**Atores**

Gerente

**Fluxo Principal**

1. Gerente cadastra ou edita instrutores.
2. Sistema salva alterações.
