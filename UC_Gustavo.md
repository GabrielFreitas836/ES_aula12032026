# Documento de Casos de Uso
Sistema: FitPass Gym Management

Aluno 1: Gustavo da Silva Victor  

Disciplina: Engenharia de Software

---

# UC01 – Realizar Matrícula de Aluno

**Atores:**  
Recepcionista

**Pré-condições:**  
Aluno fornece seus dados pessoais.

**Pós-condições:**  
Aluno é cadastrado no sistema.

**Fluxo Principal:**
1. Recepcionista acessa o sistema.
2. Seleciona "Nova Matrícula".
3. Insere dados do aluno.
4. Sistema valida os dados.
5. Sistema salva cadastro.

**Fluxos Alternativos:**
A1 – Dados inválidos  
1. Sistema solicita correção.

**Requisitos Funcionais:** RF01  
**Requisitos Não Funcionais:** RNF01  
**Regras de Negócio:** RN01

---

# UC02 – Atualizar Cadastro do Aluno

**Atores:**  
Recepcionista

**Pré-condições:**  
Aluno já cadastrado.

**Pós-condições:**  
Dados atualizados no sistema.

**Fluxo Principal:**
1. Recepcionista busca aluno.
2. Sistema exibe dados.
3. Recepcionista altera informações.
4. Sistema salva alterações.

**Fluxos Alternativos:**  
A1 – Aluno não encontrado.

**RF:** RF02  
**RNF:** RNF01  
**RN:** RN02

---

# UC03 – Cancelar Matrícula

**Atores:**  
Recepcionista

**Pré-condições:**  
Aluno ativo no sistema.

**Pós-condições:**  
Aluno fica inativo.

**Fluxo Principal:**
1. Recepcionista localiza aluno.
2. Seleciona cancelar matrícula.
3. Sistema confirma cancelamento.

**Fluxos Alternativos:**  
A1 – Matrícula já cancelada.

**RF:** RF03  
**RNF:** RNF01  
**RN:** RN03

---

# UC04 – Consultar Planos Disponíveis

**Atores:**  
Aluno, Recepcionista

**Pré-condições:**  
Planos cadastrados no sistema.

**Pós-condições:**  
Lista de planos exibida.

**Fluxo Principal:**
1. Usuário acessa opção planos.
2. Sistema mostra planos disponíveis.

**Fluxos Alternativos:**  
A1 – Nenhum plano disponível.

**RF:** RF04  
**RNF:** RNF02  
**RN:** RN04

---

# UC05 – Contratar Plano

**Atores:**  
Aluno, Recepcionista

**Pré-condições:**  
Aluno cadastrado.

**Pós-condições:**  
Plano vinculado ao aluno.

**Fluxo Principal:**
1. Aluno escolhe plano.
2. Recepcionista confirma contratação.
3. Sistema registra plano.

**Fluxos Alternativos:**  
A1 – Plano indisponível.

**RF:** RF05  
**RNF:** RNF01  
**RN:** RN05

---

# UC06 – Registrar Pagamento

**Atores:**  
Recepcionista

**Pré-condições:**  
Aluno possui plano ativo.

**Pós-condições:**  
Pagamento registrado.

**Fluxo Principal:**
1. Recepcionista acessa pagamentos.
2. Seleciona aluno.
3. Registra pagamento.
4. Sistema confirma.

**Fluxos Alternativos:**  
A1 – Falha no pagamento.

**RF:** RF06  
**RNF:** RNF03  
**RN:** RN06

---

# UC07 – Validar Acesso na Catraca

**Atores:**  
Aluno, Sistema de Catraca

**Pré-condições:**  
Aluno com plano ativo.

**Pós-condições:**  
Acesso liberado.

**Fluxo Principal:**
1. Aluno aproxima cartão RFID.
2. Sistema verifica situação.
3. Catraca libera entrada.

**Fluxos Alternativos:**  
A1 – Plano vencido.

**RF:** RF07  
**RNF:** RNF04  
**RN:** RN07

---

# UC08 – Bloquear Acesso por Inadimplência

**Atores:**  
Sistema

**Pré-condições:**  
Pagamento atrasado.

**Pós-condições:**  
Aluno bloqueado.

**Fluxo Principal:**
1. Sistema verifica pagamentos.
2. Detecta atraso.
3. Bloqueia acesso.

**Fluxos Alternativos:**  
A1 – Pagamento regularizado.

**RF:** RF08  
**RNF:** RNF03  
**RN:** RN08

---

# UC09 – Agendar Aula

**Atores:**  
Aluno

**Pré-condições:**  
Aula disponível.

**Pós-condições:**  
Agendamento registrado.

**Fluxo Principal:**
1. Aluno acessa agenda.
2. Escolhe aula.
3. Sistema registra agendamento.

**Fluxos Alternativos:**  
A1 – Aula lotada.

**RF:** RF09  
**RNF:** RNF02  
**RN:** RN09

---

# UC10 – Cancelar Agendamento

**Atores:**  
Aluno

**Pré-condições:**  
Agendamento existente.

**Pós-condições:**  
Vaga liberada.

**Fluxo Principal:**
1. Aluno acessa agenda.
2. Cancela agendamento.
3. Sistema confirma cancelamento.

**Fluxos Alternativos:**  
A1 – Prazo expirado.

**RF:** RF10  
**RNF:** RNF02  
**RN:** RN10

---

# UC11 – Registrar Presença em Aula

**Atores:**  
Instrutor

**Pré-condições:**  
Aula iniciada.

**Pós-condições:**  
Presença registrada.

**Fluxo Principal:**
1. Instrutor acessa lista.
2. Marca presença dos alunos.

**Fluxos Alternativos:**  
A1 – Aluno não agendado.

**RF:** RF11  
**RNF:** RNF02  
**RN:** RN11

---

# UC12 – Registrar Avaliação Física

**Atores:**  
Instrutor

**Pré-condições:**  
Aluno presente.

**Pós-condições:**  
Avaliação registrada.

**Fluxo Principal:**
1. Instrutor abre ficha.
2. Registra dados físicos.
3. Sistema salva avaliação.

**Fluxos Alternativos:**  
A1 – Dados incompletos.

**RF:** RF12  
**RNF:** RNF01  
**RN:** RN12

---

# UC13 – Atualizar Avaliação Física

**Atores:**  
Instrutor

**Pré-condições:**  
Avaliação existente.

**Pós-condições:**  
Avaliação atualizada.

**Fluxo Principal:**
1. Instrutor seleciona avaliação.
2. Atualiza dados.
3. Sistema salva alterações.

**RF:** RF13  
**RNF:** RNF01  
**RN:** RN13

---

# UC14 – Consultar Histórico de Avaliações

**Atores:**  
Aluno, Instrutor

**Pré-condições:**  
Avaliações registradas.

**Pós-condições:**  
Histórico exibido.

**Fluxo Principal:**
1. Usuário acessa histórico.
2. Sistema mostra avaliações.

**RF:** RF14  
**RNF:** RNF02  
**RN:** RN14

---

# UC15 – Gerar Relatório de Alunos

**Atores:**  
Gerente

**Pré-condições:**  
Dados disponíveis.

**Pós-condições:**  
Relatório gerado.

**Fluxo Principal:**
1. Gerente solicita relatório.
2. Sistema gera documento.

**RF:** RF15  
**RNF:** RNF05  
**RN:** RN15

---

# UC16 – Gerar Relatório Financeiro

**Atores:**  
Gerente

**Pré-condições:**  
Pagamentos registrados.

**Pós-condições:**  
Relatório financeiro exibido.

**Fluxo Principal:**
1. Gerente seleciona relatório.
2. Sistema gera dados financeiros.

**RF:** RF16  
**RNF:** RNF05  
**RN:** RN16

---

# UC17 – Cadastrar Instrutor

**Atores:**  
Gerente

**Pré-condições:**  
Instrutor fornece dados.

**Pós-condições:**  
Instrutor cadastrado.

**Fluxo Principal:**
1. Gerente acessa cadastro.
2. Insere dados do instrutor.
3. Sistema salva cadastro.

**RF:** RF17  
**RNF:** RNF01  
**RN:** RN17

---

# UC18 – Gerenciar Horários de Aulas

**Atores:**  
Gerente

**Pré-condições:**  
Instrutores cadastrados.

**Pós-condições:**  
Horários atualizados.

**Fluxo Principal:**
1. Gerente define horários.
2. Sistema registra agenda.

**RF:** RF18  
**RNF:** RNF02  
**RN:** RN18

---

# UC19 – Consultar Frequência do Aluno

**Atores:**  
Aluno, Instrutor

**Pré-condições:**  
Presenças registradas.

**Pós-condições:**  
Frequência exibida.

**Fluxo Principal:**
1. Usuário acessa frequência.
2. Sistema exibe dados.

**RF:** RF19  
**RNF:** RNF02  
**RN:** RN19

---

# UC20 – Liberar Acesso Manual

**Atores:**  
Recepcionista

**Pré-condições:**  
Problema na catraca.

**Pós-condições:**  
Acesso liberado manualmente.

**Fluxo Principal:**
1. Recepcionista verifica aluno.
2. Libera acesso manual.

**Fluxos Alternativos:**  
A1 – Aluno bloqueado.

**RF:** RF20  
**RNF:** RNF04  
**RN:** RN20
