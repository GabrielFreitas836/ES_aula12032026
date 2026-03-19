# Entrega – Documento de Casos de Uso e Diagramas

## Identificação do Aluno
- Aluno: Davi Padua Medeiros de Carvalho

## Arquivos Entregues

### Documento de Casos de Uso
Nome do arquivo entregue: UC_nomealuno1_nomealuno2.md

### Diagramas de Casos de Uso
Arquivos entregues (PNG): DUC_davi_carvalho.png.

# UC01 — Efetuar Login

**Ator Principal**
Usuário (Aluno, Recepcionista, Instrutor ou Gerente)

**Objetivo**
Permitir que o usuário acesse o sistema utilizando suas credenciais.

**Pré-condições**
O usuário precisa possuir um cadastro ativo no sistema.

**Pós-condições**
O usuário entra no sistema e sua sessão é iniciada.

**Fluxo Principal**

1. O usuário digita e-mail e senha.
2. O sistema verifica as credenciais informadas.
3. Se os dados forem válidos, o acesso é liberado.
4. O sistema direciona o usuário para a tela inicial.

**Fluxos Alternativos**

**A1 — Senha incorreta**
O sistema informa que a senha digitada está incorreta.

**A2 — Conta bloqueada**
O sistema impede o acesso e orienta o usuário a recuperar a conta.

---

# UC02 — Cadastrar Novo Aluno

**Ator Principal**
Recepcionista

**Objetivo**
Registrar um novo aluno no sistema.

**Pré-condições**
O recepcionista precisa estar autenticado.

**Pós-condições**
O aluno passa a fazer parte do cadastro da academia.

**Fluxo Principal**

1. O recepcionista acessa a tela de cadastro.
2. Preenche os dados do aluno.
3. O sistema verifica se as informações são válidas.
4. O cadastro é salvo no banco de dados.

**Fluxos Alternativos**

**A1 — CPF duplicado**
O sistema informa que já existe um aluno com esse CPF.

---

# UC03 — Atualizar Dados do Aluno

**Ator Principal**
Recepcionista

**Objetivo**
Modificar informações cadastrais de um aluno.

**Pré-condições**
O aluno deve estar registrado no sistema.

**Pós-condições**
As novas informações são salvas.

**Fluxo Principal**

1. O recepcionista procura o aluno no sistema.
2. Realiza as alterações necessárias.
3. O sistema valida os dados.
4. As alterações são registradas.

**Fluxos Alternativos**

**A1 — Aluno não encontrado**
O sistema informa que o aluno não foi localizado.

---

# UC04 — Registrar Matrícula

**Ator Principal**
Recepcionista

**Objetivo**
Associar um aluno a um plano da academia.

**Pré-condições**
O aluno precisa estar cadastrado.

**Pós-condições**
A matrícula do aluno é registrada.

**Fluxo Principal**

1. O recepcionista seleciona o aluno.
2. O sistema mostra os planos disponíveis.
3. O recepcionista escolhe um plano.
4. O sistema registra a matrícula.

**Fluxos Alternativos**

**A1 — Plano indisponível**
O sistema informa que o plano escolhido não está disponível.

---

# UC05 — Gerenciar Planos

**Ator Principal**
Gerente

**Objetivo**
Criar ou modificar planos oferecidos pela academia.

**Pré-condições**
O gerente precisa estar logado no sistema.

**Pós-condições**
As informações do plano são registradas ou atualizadas.

**Fluxo Principal**

1. O gerente acessa a área de planos.
2. Cria um novo plano ou edita um existente.
3. O sistema salva as alterações.

**Fluxos Alternativos**

**A1 — Dados incorretos**
O sistema solicita a correção das informações.

---

# UC06 — Registrar Pagamento

**Ator Principal**
Recepcionista

**Objetivo**
Registrar o pagamento da mensalidade de um aluno.

**Pré-condições**
O aluno deve possuir matrícula ativa.

**Pós-condições**
O pagamento é registrado no sistema.

**Fluxo Principal**

1. O recepcionista seleciona o aluno.
2. Informa o pagamento realizado.
3. O sistema confirma o registro da transação.

**Fluxos Alternativos**

**A1 — Falha no registro**
O sistema apresenta uma mensagem de erro.

---

# UC07 — Validar Acesso na Catraca

**Ator Principal**
Sistema de Catraca

**Objetivo**
Controlar a entrada dos alunos na academia.

**Pré-condições**
O aluno deve possuir matrícula ativa.

**Pós-condições**
A entrada é liberada ou bloqueada.

**Fluxo Principal**

1. O aluno aproxima o cartão RFID da catraca.
2. O sistema verifica a situação da matrícula.
3. Caso esteja ativa, a catraca é liberada.

**Fluxos Alternativos**

**A1 — Matrícula vencida**
O sistema bloqueia o acesso.

---

# UC08 — Consultar Situação da Matrícula

**Ator Principal**
Aluno

**Objetivo**
Permitir que o aluno visualize o status da sua matrícula.

**Pré-condições**
O aluno deve estar logado no sistema.

**Pós-condições**
As informações da matrícula são exibidas.

**Fluxo Principal**

1. O aluno acessa o menu de matrícula.
2. O sistema mostra o status atual.

---

# UC09 — Agendar Aula

**Ator Principal**
Aluno

**Objetivo**
Permitir que o aluno reserve vaga em uma aula.

**Pré-condições**
O aluno deve possuir matrícula ativa.

**Pós-condições**
A reserva da aula é confirmada.

**Fluxo Principal**

1. O aluno acessa a agenda de aulas.
2. Escolhe uma aula disponível.
3. O sistema registra o agendamento.

**Fluxos Alternativos**

**A1 — Aula cheia**
O sistema informa que não há vagas.

---

# UC10 — Cancelar Aula Agendada

**Ator Principal**
Aluno

**Objetivo**
Cancelar uma reserva de aula.

**Pré-condições**
O aluno deve ter um agendamento ativo.

**Pós-condições**
O agendamento é removido.

**Fluxo Principal**

1. O aluno acessa sua lista de aulas.
2. Seleciona a aula desejada.
3. Solicita o cancelamento.
4. O sistema confirma a remoção.

**Fluxos Alternativos**

**A1 — Prazo expirado**
O sistema informa que não é mais possível cancelar.

---

# UC11 — Registrar Presença em Aula

**Ator Principal**
Instrutor

**Objetivo**
Registrar a presença dos alunos em uma aula.

**Pré-condições**
A aula deve estar acontecendo.

**Pós-condições**
A presença dos alunos fica registrada.

**Fluxo Principal**

1. O instrutor acessa a lista de alunos inscritos.
2. Marca os alunos presentes.
3. O sistema salva as informações.

---

# UC12 — Cadastrar Instrutor

**Ator Principal**
Gerente

**Objetivo**
Registrar um novo instrutor no sistema.

**Pré-condições**
O gerente deve estar autenticado.

**Pós-condições**
O instrutor é cadastrado no sistema.

**Fluxo Principal**

1. O gerente acessa o cadastro de instrutores.
2. Insere os dados necessários.
3. O sistema salva o cadastro.

---

# UC13 — Criar Aula

**Ator Principal**
Instrutor

**Objetivo**
Cadastrar uma nova aula no sistema.

**Pré-condições**
O instrutor deve estar logado.

**Pós-condições**
A aula é adicionada ao sistema.

**Fluxo Principal**

1. O instrutor informa data, horário e limite de alunos.
2. O sistema registra a aula.

---

# UC14 — Atualizar Aula

**Ator Principal**
Instrutor

**Objetivo**
Modificar informações de uma aula existente.

**Pré-condições**
A aula deve estar cadastrada.

**Pós-condições**
As alterações são salvas.

**Fluxo Principal**

1. O instrutor seleciona a aula.
2. Atualiza as informações.
3. O sistema registra as mudanças.

---

# UC15 — Registrar Avaliação Física

**Ator Principal**
Instrutor

**Objetivo**
Registrar dados de avaliação física de um aluno.

**Pré-condições**
O aluno deve estar cadastrado.

**Pós-condições**
A avaliação é armazenada no sistema.

**Fluxo Principal**

1. O instrutor acessa o perfil do aluno.
2. Insere os dados da avaliação.
3. O sistema salva as informações.

---

# UC16 — Consultar Avaliação Física

**Ator Principal**
Aluno

**Objetivo**
Visualizar as avaliações físicas realizadas.

**Pré-condições**
O aluno deve estar autenticado.

**Pós-condições**
O histórico de avaliações é exibido.

**Fluxo Principal**

1. O aluno acessa a área de avaliações.
2. O sistema mostra as avaliações registradas.

---

# UC17 — Gerar Relatório de Frequência

**Ator Principal**
Gerente

**Objetivo**
Visualizar relatórios de frequência dos alunos.

**Pré-condições**
O gerente deve estar autenticado.

**Pós-condições**
O relatório é exibido.

**Fluxo Principal**

1. O gerente seleciona o período desejado.
2. O sistema gera o relatório.
3. Os dados são apresentados na tela.

---

# UC18 — Gerar Relatório Financeiro

**Ator Principal**
Gerente

**Objetivo**
Visualizar informações financeiras da academia.

**Pré-condições**
O gerente deve estar logado.

**Pós-condições**
O relatório financeiro é apresentado.

**Fluxo Principal**

1. O gerente define o período.
2. O sistema reúne os dados de pagamentos.
3. O relatório é exibido.

---

# UC19 — Administrar Usuários do Sistema

**Ator Principal**
Gerente

**Objetivo**
Gerenciar contas de usuários do sistema.

**Pré-condições**
O gerente deve estar autenticado.

**Pós-condições**
As contas são criadas ou atualizadas.

**Fluxo Principal**

1. O gerente acessa a área de usuários.
2. Cria ou modifica contas.
3. O sistema salva as alterações.

---

# UC20 — Encerrar Sessão

**Ator Principal**
Usuário

**Objetivo**
Finalizar o acesso ao sistema.

**Pré-condições**
O usuário deve estar logado.

**Pós-condições**
A sessão é encerrada.

**Fluxo Principal**

1. O usuário seleciona a opção de sair.
2. O sistema encerra a sessão.
3. O sistema retorna à tela de login.

---

## Issues Relacionadas
> **Atenção:** As Issues devem ser **apenas referenciadas** — não utilize termos como *closes*, *fixes*, *resolve*.

- Relacionado à Issue **#1 – Documento de Casos de Uso**
- Relacionado à Issue **#2 – Diagrama de Casos de Uso**

## Checklist Antes do Envio

Marque cada linha após confirmar:

- [X] O documento contém **20 casos de uso completos**, seguindo o template do arquivo `/docs/casosdeuso.md`
- [X] O nome do arquivo segue o padrão exigido
- [X] Os diagramas representam **todos os casos de uso listados** no documento
- [X] Todos os diagramas estão em **formato PNG**
- [X] As Issues foram referenciadas corretamente
- [X] O PR contém **apenas** os arquivos exigidos

## Observações (Opcional)
Use este espaço caso queira explicar alguma decisão, dúvida ou comentário adicional.
