## UC01 — Realizar Login

### Ator Principal
Usuário

### Objetivo
Permitir que o usuário acesse o sistema.

### Pré-condições
- Usuário deve possuir cadastro ativo.

### Pós-condições
- Sessão iniciada com sucesso.

### Fluxo Principal
1. O usuário informa e-mail e senha.
2. O sistema valida as credenciais.
3. O sistema autentica o usuário e redireciona para a tela inicial.

### Fluxos Alternativos
- **A1 — Senha incorreta:**  
  O sistema exibe mensagem de erro.

- **A2 — Conta bloqueada:**  
  O sistema impede o login e instrui o usuário a recuperar o acesso.

### RF Relacionados
- RF01 — Autenticação de usuário

### RNF Relacionados
- RNF01 — Segurança na autenticação

### RN Relacionadas
- RN01 — Usuários devem possuir credenciais únicas.

---

## UC02 — Cadastrar Aluno

### Ator Principal
Recepcionista

### Objetivo
Cadastrar um novo aluno no sistema.

### Pré-condições
- Recepcionista autenticado no sistema.

### Pós-condições
- Aluno registrado no sistema.

### Fluxo Principal
1. Recepcionista seleciona "Cadastrar Aluno".
2. Sistema solicita os dados do aluno.
3. Recepcionista preenche as informações.
4. Sistema valida os dados.
5. Sistema registra o aluno.

### Fluxos Alternativos
- **A1 — Dados inválidos:**  
  O sistema solicita correção dos dados.

### RF Relacionados
- RF02 — Cadastro de alunos

### RNF Relacionados
- RNF02 — Validação de dados

### RN Relacionadas
- RN02 — Cada aluno deve possuir CPF único.

---

## UC03 — Atualizar Cadastro de Aluno

### Ator Principal
Recepcionista

### Objetivo
Atualizar informações cadastrais de um aluno.

### Pré-condições
- Aluno deve estar cadastrado no sistema.

### Pós-condições
- Dados do aluno atualizados.

### Fluxo Principal
1. Recepcionista busca o aluno.
2. Sistema exibe os dados atuais.
3. Recepcionista altera as informações.
4. Sistema salva as alterações.

### Fluxos Alternativos
- **A1 — Dados inválidos:**  
  Sistema solicita correção.

### RF Relacionados
- RF03 — Atualização de cadastro

### RNF Relacionados
- RNF02 — Validação de dados

### RN Relacionadas
- RN02 — CPF não pode ser duplicado.

---

## UC04 — Cancelar Matrícula

### Ator Principal
Recepcionista

### Objetivo
Encerrar a matrícula de um aluno.

### Pré-condições
- Aluno deve possuir matrícula ativa.

### Pós-condições
- Matrícula cancelada.

### Fluxo Principal
1. Recepcionista localiza o aluno.
2. Recepcionista seleciona "Cancelar Matrícula".
3. Sistema solicita confirmação.
4. Recepcionista confirma.
5. Sistema registra cancelamento.

### Fluxos Alternativos
- **A1 — Operação cancelada:**  
  Recepcionista cancela o processo.

### RF Relacionados
- RF04 — Cancelamento de matrícula

### RNF Relacionados
- RNF03 — Registro de log de operações

### RN Relacionadas
- RN03 — Alunos com matrícula cancelada não podem acessar a academia.

---

## UC05 — Consultar Planos Disponíveis

### Ator Principal
Aluno

### Objetivo
Visualizar os planos disponíveis da academia.

### Pré-condições
- Sistema deve possuir planos cadastrados.

### Pós-condições
- Lista de planos exibida.

### Fluxo Principal
1. Aluno acessa a área de planos.
2. Sistema exibe os planos disponíveis.

### Fluxos Alternativos
- **A1 — Nenhum plano disponível:**  
  Sistema informa indisponibilidade.

### RF Relacionados
- RF05 — Consulta de planos

### RNF Relacionados
- RNF01 — Tempo de resposta do sistema

### RN Relacionadas
- RN04 — Planos possuem duração mínima de 1 mês.

---

## UC06 — Contratar Plano

### Ator Principal
Aluno

### Objetivo
Permitir que um aluno contrate um plano da academia.

### Pré-condições
- Aluno cadastrado no sistema.

### Pós-condições
- Plano associado ao aluno.

### Fluxo Principal
1. Aluno seleciona um plano.
2. Sistema apresenta detalhes.
3. Aluno confirma contratação.
4. Sistema registra o plano.

### Fluxos Alternativos
- **A1 — Plano indisponível:**  
  Sistema informa erro.

### RF Relacionados
- RF06 — Contratação de plano

### RNF Relacionados
- RNF01

### RN Relacionadas
- RN04

---

## UC07 — Registrar Pagamento

### Ator Principal
Recepcionista

### Objetivo
Registrar pagamento de mensalidade.

### Pré-condições
- Aluno deve possuir plano ativo.

### Pós-condições
- Pagamento registrado.

### Fluxo Principal
1. Recepcionista seleciona o aluno.
2. Sistema exibe débitos pendentes.
3. Recepcionista registra pagamento.
4. Sistema confirma pagamento.

### Fluxos Alternativos
- **A1 — Falha no registro:**  
  Sistema informa erro.

### RF Relacionados
- RF07 — Registro de pagamentos

### RNF Relacionados
- RNF04 — Segurança nas transações

### RN Relacionadas
- RN05 — Todo pagamento deve ser registrado com data e valor.

---

## UC08 — Verificar Situação Financeira

### Ator Principal
Sistema

### Objetivo
Identificar alunos inadimplentes.

### Pré-condições
- Sistema possui registros financeiros.

### Pós-condições
- Alunos inadimplentes identificados.

### Fluxo Principal
1. Sistema verifica pagamentos vencidos.
2. Sistema marca alunos inadimplentes.

### RF Relacionados
- RF08 — Controle financeiro

### RNF Relacionados
- RNF01

### RN Relacionadas
- RN06 — Alunos inadimplentes têm acesso bloqueado.

---

## UC09 — Liberar Acesso na Catraca

### Ator Principal
Sistema de Catraca

### Objetivo
Permitir entrada do aluno na academia.

### Pré-condições
- Aluno deve possuir plano ativo.

### Pós-condições
- Entrada liberada.

### Fluxo Principal
1. Aluno aproxima cartão RFID.
2. Sistema verifica situação do aluno.
3. Sistema autoriza acesso.
4. Catraca libera entrada.

### Fluxos Alternativos
- **A1 — Aluno inadimplente:**  
  Acesso negado.

### RF Relacionados
- RF09 — Controle de acesso

### RNF Relacionados
- RNF05 — Integração com API externa

### RN Relacionadas
- RN06

---

## UC10 — Bloquear Acesso por Inadimplência

### Ator Principal
Sistema

### Objetivo
Impedir acesso de alunos inadimplentes.

### Pré-condições
- Aluno com pagamento vencido.

### Pós-condições
- Acesso bloqueado.

### Fluxo Principal
1. Sistema identifica inadimplência.
2. Sistema bloqueia acesso.

---

## UC11 — Agendar Aula

### Ator Principal
Aluno

### Objetivo
Permitir que o aluno agende participação em aulas.

### Pré-condições
- Aluno possui plano ativo.

### Pós-condições
- Aula reservada.

### Fluxo Principal
1. Aluno acessa agenda.
2. Sistema mostra aulas disponíveis.
3. Aluno seleciona aula.
4. Sistema registra agendamento.

---

## UC12 — Cancelar Agendamento de Aula

### Ator Principal
Aluno

### Objetivo
Cancelar participação em aula agendada.

### Pré-condições
- Aula previamente agendada.

### Pós-condições
- Agendamento removido.

### Fluxo Principal
1. Aluno acessa agenda.
2. Seleciona aula.
3. Sistema cancela agendamento.

---

## UC13 — Registrar Presença em Aula

### Ator Principal
Instrutor

### Objetivo
Registrar presença dos alunos nas aulas.

### Pré-condições
- Aula cadastrada no sistema.

### Pós-condições
- Presenças registradas.

### Fluxo Principal
1. Instrutor acessa lista da aula.
2. Instrutor marca presença.
3. Sistema registra presença.

---

## UC14 — Cadastrar Aula

### Ator Principal
Instrutor

### Objetivo
Criar nova aula no sistema.

### Pré-condições
- Instrutor autenticado.

### Pós-condições
- Aula cadastrada.

### Fluxo Principal
1. Instrutor cria nova aula.
2. Define horário e capacidade.
3. Sistema salva aula.

---

## UC15 — Alterar Aula

### Ator Principal
Instrutor

### Objetivo
Modificar informações de uma aula.

### Pré-condições
- Aula existente.

### Pós-condições
- Aula atualizada.

### Fluxo Principal
1. Instrutor seleciona aula.
2. Instrutor altera dados.
3. Sistema salva alterações.

---

## UC16 — Registrar Avaliação Física

### Ator Principal
Instrutor

### Objetivo
Registrar dados físicos do aluno.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Avaliação registrada.

### Fluxo Principal
1. Instrutor seleciona aluno.
2. Insere dados da avaliação.
3. Sistema salva avaliação.

---

## UC17 — Consultar Histórico de Avaliações

### Ator Principal
Aluno

### Objetivo
Visualizar avaliações físicas anteriores.

### Pré-condições
- Avaliações registradas.

### Pós-condições
- Histórico exibido.

### Fluxo Principal
1. Aluno acessa histórico.
2. Sistema mostra avaliações.

---

## UC18 — Emitir Relatório Financeiro

### Ator Principal
Gerente

### Objetivo
Gerar relatório financeiro da academia.

### Pré-condições
- Dados financeiros disponíveis.

### Pós-condições
- Relatório gerado.

### Fluxo Principal
1. Gerente seleciona período.
2. Sistema gera relatório.

---

## UC19 — Emitir Relatório de Frequência

### Ator Principal
Gerente

### Objetivo
Visualizar frequência dos alunos.

### Pré-condições
- Presenças registradas.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. Gerente seleciona período.
2. Sistema apresenta dados.

---

## UC20 — Gerenciar Instrutores

### Ator Principal
Gerente

### Objetivo
Cadastrar ou atualizar instrutores.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Instrutor cadastrado ou atualizado.

### Fluxo Principal
1. Gerente acessa área de instrutores.
2. Insere ou altera dados.
3. Sistema salva informações.
