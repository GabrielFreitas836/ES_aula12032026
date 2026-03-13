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
- RF01


## UC02 — Cancelar agendamento

### Ator Principal
Aluno

### Objetivo
Permitir que o usuário cancele o agendamento de aulas

### Pré-condições
- Usuário aluno deve já ter feito o agendamento de alguma aula

### Pós-condições
- Agendamento cancelado com sucesso

### Fluxo Principal
1. O usuário aluno cancela o agendamento
2. O sistema verifica se falta mais de 1 hora para o começo da aula
3. O sistema confirma o cancelamento

### Fluxos Alternativos
- **A1 — Menos de 1 hora para começar a aula:**
  
  O sistema não permite o cancelamento

### RN Relacionados
- RN03

## UC03 — Controle de Acesso

### Ator Principal
- Catraca
- Aluno

### Objetivo
Validar a entrada do aluno por RFID

### Pré-condições
- O usuário aluno deve possuir um cadastro ativo
- O usuário aluno não deve possuir as mensalidades vencidas há mais de 5 dias

### Pós-condições
- Entrada de usuário aluno validada com sucesso

### Fluxo Principal
1. O usuário aluno utiliza a catraca
2. O sistema da catraca verifica se as mensalidades não estão vencidas há mais de 5 dias
3. O sistema da catraca permite a entrada do usuário aluno

## Fluxos Alternativos
- **A1 — Bloqueio por Inadimplência:**
  
  O sistema não permite a entrada do usuário aluno

## RF Relacionados
- RF03
  
## RN Relacionados
- RN01

## UC04 - Gerar relatórios

### Ator Principal
- Gerente

### Objetivo
Permitir ao usuário gerente gerar relatórios pelo sistema

### Pré-condições
- O usuário cadastrado deve ser do tipo gerente
  
### Pós-condições
- Geração de relatórios realizada com sucesso

### Fluxo Principal
1. O sistema verifica se o usuário cadastrado é do tipo gerente
2. O usuário gerente utiliza a função de gerar relatório
3. O sistema gera o relatório

### Fluxos Alternativos
- **A1 — Outro tipo de usuário:**
  
  O sistema não permite a geração de relatórios

### RF Relacionados
- RF09
  
### RN Relacionados
- RN06

## UC05 — Verificar mensalidade

### Ator Principal
- Sistema
- Aluno

### Objetivo
Verificar se a mensalidade do usuário aluno está em dia

### Pré-condições
- O usuário aluno deve estar cadastrado no sistema
- O usuário aluno deve ter um plano ativo

### Pós-condições
- Verificação de mensalidade bem-sucedida

### Fluxo Principal
1. O sistema faz uma requisição pela API REST para retornar do JSON o status atual da última mensalidade do aluno
2. O sistema determina se a mensalidade está em dia ou não

### Fluxo Alternativo
- **A1 — Mensalidade atrasada em até 5 dias:**
  
  O sistema determina que a mensalidade não está em dia
  
- **A2 — Mensalidade atrasada há mais de 5 dias:**
  
  1. O sistema determina que a mensalidade não está em dia
  2. O sistema bloqueia a entrada do usuário aluno por inadimplência
  
- **A3 — Mensalidade dentro do prazo:**
  
  O sistema determina que a mensalidade está em dia

### RF Relacionados
- RF04

### RN Relacionados
- RN01

### RNF Relacionados
- RNF06

## UC06 — Listar presença

### Ator Principal
- Instrutor

### Objetivo
Permitir ao usuário instrutor listar a presença dos usuários alunos ativos e regulares

### Pré-condições
- As aulas devem ter sido registradas no sistema

### Pós-condições
- Usuário instrutor deve listar a presença dos alunos com sucesso

### Fluxo Principal
1. Aula é registrada no sistema
2. Aula é concluída com sucesso
3. Professor lista a presença dos alunos participantes

### Fluxo Alternativo
- **A1 — Nenhum aluno registrado:**
  
  1. Aula não é concluída com sucesso
  2. Instrutor naõ lista presença alguma

## RF Relacionados
- RF07

##UC07 — Configurar Planos da Academia

### Ator Principal
- Gerente

### Objetivo
- Criar ou editar as modalidades e pacotes oferecidos pela academia.

### Pré-condições
- O usuário deve possuir perfil de Gerente (RN06).

### Pós-condições
- Novo plano disponível para venda na recepção.

### Fluxo Principal
1. O gerente acessa o gerenciamento de planos (RF02).
2. O gerente define o nome (ex: "Plano Funcional"), valor, periodicidade e status.
3. O sistema salva as configurações.

### Fluxos Alternativos
- **A1 — Desativação de plano:**
  
  O gerente desativa um plano existente; novos alunos não podem mais contratá-lo, mas alunos antigos mantêm o contrato até o fim da vigência.

### RF Relacionados
- RF02

### RN Relacionaods
- RN06

UC07 — Realizar Matrícula de Aluno
Ator Principal
Recepcionista

Objetivo
Cadastrar um novo aluno no sistema vinculado a um plano específico.

Pré-condições
O usuário deve estar autenticado com perfil de Recepcionista ou Gerente (RN06).

O plano a ser contratado deve estar ativo no sistema.

Pós-condições
Aluno cadastrado e apto a frequentar a academia (dependendo do pagamento).

Fluxo Principal
O recepcionista acessa o módulo de cadastro.

O recepcionista insere os dados pessoais, contato e endereço (RF01).

O recepcionista seleciona o plano desejado (Mensal, Anual, etc.).

O sistema valida os campos obrigatórios e salva o registro.

Fluxos Alternativos
A1 — Dados incompletos:
O sistema impede o salvamento e destaca os campos obrigatórios vazios.

RF / RN Relacionados
RF01, RN06.

UC08 — Registrar Pagamento
Ator Principal
Recepcionista

Objetivo
Registrar a quitação de uma mensalidade para regularizar a situação do aluno.

Pré-condições
Aluno deve estar previamente cadastrado.

Pós-condições
Status de regularidade do aluno atualizado para "Em dia" imediatamente (RN07).

Fluxo Principal
O recepcionista seleciona o aluno e a fatura pendente.

O recepcionista informa a forma de pagamento (Dinheiro, Cartão ou PIX) (RF03).

O sistema valida o valor integral do pagamento (RN04).

O sistema registra o pagamento e atualiza automaticamente a situação do aluno para "Regular".

Fluxos Alternativos
A1 — Tentativa de pagamento parcial:
O sistema bloqueia a operação e informa que pagamentos parciais não são permitidos (RN04).

RF / RN Relacionados
RF03, RN04, RN07.

UC09 — Reservar Vaga em Aula (Agendamento)
Ator Principal
Aluno

Objetivo
Permitir que o aluno reserve uma vaga em uma aula específica.

Pré-condições
Aluno deve estar com a situação regular (mensalidade em dia).

Pós-condições
Vaga reservada e notificação de confirmação enviada (RF10).

Fluxo Principal
O aluno acessa a lista de aulas disponíveis (RF06).

O aluno seleciona o horário e a aula desejada.

O sistema verifica a disponibilidade de vagas (RN02).

O sistema confirma a reserva e envia uma notificação ao aluno (RF10).

Fluxos Alternativos
A1 — Turma lotada:
O sistema informa que o limite de vagas foi atingido e impede o agendamento (RN02).

RF / RN Relacionados
RF06, RF10, RN02.

UC10 — Registrar Avaliação Física
Ator Principal
Instrutor

Objetivo
Registrar os dados biométricos e de desempenho do aluno.

Pré-condições
O usuário deve estar autenticado com perfil de Instrutor (RN06).

O aluno deve estar ativo e com mensalidades em dia (RN05).

Pós-condições
Avaliação salva e notificação de liberação enviada ao aluno (RF10).

Fluxo Principal
O instrutor seleciona o aluno regular.

O instrutor insere peso, IMC e percentual de gordura (RF08).

O instrutor anexa arquivos complementares (se necessário).

O sistema salva a avaliação e notifica o aluno.

Fluxos Alternativos
A1 — Aluno irregular ou inativo:
O sistema bloqueia o registro da avaliação e informa o motivo (RN05).

RF / RN Relacionados
RF08, RF10, RN05, RN06.

UC11 — Configurar Planos da Academia
Ator Principal
Gerente

Objetivo
Criar ou editar as modalidades e pacotes oferecidos pela academia.

Pré-condições
O usuário deve possuir perfil de Gerente (RN06).

Pós-condições
Novo plano disponível para venda na recepção.

Fluxo Principal
O gerente acessa o gerenciamento de planos (RF02).

O gerente define o nome (ex: "Plano Funcional"), valor, periodicidade e status.

O sistema salva as configurações.

Fluxos Alternativos
A1 — Desativação de plano:
O gerente desativa um plano existente; novos alunos não podem mais contratá-lo, mas alunos antigos mantêm o contrato até o fim da vigência.

RF / RN Relacionados
RF02, RN06.
