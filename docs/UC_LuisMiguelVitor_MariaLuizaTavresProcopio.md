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
- RF04

### RNF Relacionados
- RNF02
- RNF04

### RN Relacionadas
- RN06


## UC02 — Cadastrar Aluno 

### Ator Principal
Recepcionista

### Objetivo
Registrar novo aluno no sistema.

### Pré-condições
- Recepcionista autenticado.

### Pós-condições
- Aluno cadastrado e ativo.

### Fluxo Principal
1. Recepcionista acessa a tela de cadastro.
2. Informa dados pessoais e contato.
3. Seleciona plano.
4. Sistema valida dados.
5. Sistema salva cadastro.

### Fluxos Alternativos
- **A1 — Dados obrigatórios não informados:**  
  Sistema solicita preenchimento.

- **A2 — CPF já cadastrado:**  
  Sistema impede duplicidade.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF02
- RNF04

### RN Relacionadas
- RN06


## UC03 — Gerenciar Planos

### Ator Principal
Gerente

### Objetivo
Criar, editar, ativar ou desativar planos.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Plano atualizado.

### Fluxo Principal
1. Gerente acessa módulo de planos.
2. Seleciona ação desejada.
3. Informa dados do plano.
4. Sistema valida informações.
5. Sistema salva alterações.

### Fluxos Alternativos
- **A1 — Dados incompletos:**  
  Sistema impede salvamento.

- **A2 — Plano em uso por alunos:**  
  Sistema impede exclusão e sugere desativação.

### RF Relacionados
- RF02

### RNF Relacionados
- RNF05

### RN Relacionadas
- RN06

## UC04 — Registrar Pagamento

### Ator Principal
Recepcionista

### Objetivo
Registrar pagamento de mensalidade.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Situação financeira atualizada.

### Fluxo Principal
1. Recepcionista seleciona aluno.
2. Informa forma de pagamento.
3. Confirma valor integral.
4. Sistema registra pagamento.
5. Sistema atualiza regularidade.

### Fluxos Alternativos
- **A1 — Valor incorreto:**  
  Sistema impede confirmação.

- **A2 — Falha na transação:**  
  Sistema cancela operação e solicita nova tentativa.

### RF Relacionados
- RF03

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN04
- RN07



## UC05 — Verificar Regularidade do Aluno

### Ator Principal
Sistema

### Objetivo
Determinar se o aluno está apto.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Status atualizado.

### Fluxo Principal
1. Sistema consulta pagamentos.
2. Verifica vencimentos.
3. Define situação como regular ou irregular.

### Fluxos Alternativos
- **A1 —Mensalidade vencida:**  
  Aluno marcado como inadimplente.

- **A2 —Dados financeiros indisponíveis:**  
 Sistema registra erro e mantém status anterior.

### RF Relacionados
- RF04

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01


## UC06 — Validar Acesso na Catraca

### Ator Principal
Sistema de Catraca

### Objetivo
Permitir ou bloquear entrada.

### Pré-condições
- Aluno identificado por RFID.

### Pós-condições
- Entrada registrada ou negada.

### Fluxo Principal
1. Catraca envia identificação ao sistema.
2. Sistema verifica regularidade.
3. Sistema autoriza acesso.
4. Catraca libera entrada.

### Fluxos Alternativos
- **A1 —Aluno inadimplente:**  
  Acesso negado.

- **A2 —Falha de comunicação com API:**  
 Catraca permanece bloqueada.

### RF Relacionados
- RF05

### RNF Relacionados
- RNF03
- RNF06

### RN Relacionadas
- RN01



## UC07 — Visualizar Aulas Disponíveis

### Ator Principal
Aluno

### Objetivo
Consultar horários de aulas.

### Pré-condições
- Aluno autenticado.

### Pós-condições
- Lista exibida.

### Fluxo Principal
1. Aluno acessa área de aulas.
2. Sistema apresenta horários disponíveis.


### Fluxos Alternativos
- **A1 — Nenhuma aula disponível:**  
  Sistema informa indisponibilidade.

- **A2 — Falha na consulta:**  
  Sistema exibe mensagem de erro.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- Nenhuma

## UC08 — Agendar Aula

### Ator Principal
Aluno

### Objetivo
Reservar vaga em aula.

### Pré-condições
- Aluno regular.

### Pós-condições
- Reserva confirmada.

### Fluxo Principal
1. Aluno seleciona aula.
2. Sistema verifica vagas.
3. Sistema registra reserva.


### Fluxos Alternativos
- **A1 — Aula lotada:**  
  Reserva bloqueada.

- **A2 — Aluno irregular:**  
  Sistema impede agendamento

### RF Relacionados
- RF06

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN02

## UC09 — Cancelar Agendamento

### Ator Principal
Aluno

### Objetivo
Cancelar reserva.

### Pré-condições
- Agendamento existente.

### Pós-condições
- Vaga liberada.

### Fluxo Principal
1. Aluno acessa agendamentos.
2. Seleciona aula.
3. Confirma cancelamento.
4. Sistema remove reserva.


### Fluxos Alternativos
- **A1 — Prazo expirado:**  
  Cancelamento bloqueado.

- **A2 — Agendamento inexistente:**  
  Sistema informa erro.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN03



## UC10 — Registrar Presença em Aula

### Ator Principal
Instrutor

### Objetivo
Confirmar presença dos alunos.

### Pré-condições
- Aula em andamento.

### Pós-condições
- Lista atualizada.

### Fluxo Principal
1. Instrutor acessa lista da aula.
2. Marca presença dos alunos.
3. Sistema salva registros.


### Fluxos Alternativos
- **A1 — Aluno não inscrito:**  
  Sistema impede marcação.

- **A2 — Falha ao salvar:**  
  Sistema solicita nova tentativa.

### RF Relacionados
- RF07

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN06


## UC11 — Registrar Avaliação Física

### Ator Principal
Instrutor

### Objetivo
Cadastrar dados físicos.

### Pré-condições
- Aluno regular.

### Pós-condições
- Avaliação registrada.

### Fluxo Principal
1. Instrutor seleciona aluno.
2. Informa medidas físicas.
3. Anexa arquivos.
4. Sistema salva avaliação.


### Fluxos Alternativos
- **A1 — Aluno irregular:**  
  Avaliação bloqueada.

- **A2 — Dados inválidos:**  
  Sistema solicita correção.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF02

### RN Relacionadas
- RN05


## UC12 — Consultar Avaliações Físicas

### Ator Principal
Instrutor

### Objetivo
Visualizar histórico.

### Pré-condições
- Avaliações registradas.

### Pós-condições
- Dados exibidos.

### Fluxo Principal
1. Instrutor seleciona aluno.
2. Sistema exibe histórico.


### Fluxos Alternativos
- **A1 — Nenhuma avaliação encontrada:**  
  Sistema informa ausência de dados.

- **A2 — Falha na consulta:**  
  Sistema exibe erro.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF04

### RN Relacionadas
- Nenhuma

## UC13 — Emitir Relatório de Inadimplência

### Ator Principal
Gerente

### Objetivo
Identificar alunos inadimplentes.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório gerado.

### Fluxo Principal
1. Gerente solicita relatório.
2. Sistema processa dados.
3. Sistema exibe resultado.

### Fluxos Alternativos
- **A1 — Nenhum aluno inadimplente:**  
  Sistema informa ausência.

- **A2 — Falha na geração:**  
  Sistema exibe erro.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

## UC14 — Emitir Relatório de Alunos Ativos

### Ator Principal
Gerente

### Objetivo
Listar alunos ativos.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. Gerente solicita relatório.
2. Sistema gera lista.


### Fluxos Alternativos
- **A1 — Nenhum aluno ativo:**  
  Sistema informa ausência.

- **A2 — Falha na consulta:**  
  Sistema exibe erro.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- Nenhuma

## UC15 — Emitir Relatório de Acessos

### Ator Principal
Gerente

### Objetivo
Consultar histórico de entradas.

### Pré-condições
- Registros existentes.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. Gerente solicita relatório.
2. Sistema compila dados.
3. Exibe histórico.

### Fluxos Alternativos
- **A1 — Nenhum acesso registrado:**  
  Sistema informa ausência.

- **A2 — Falha na consulta:**  
  Sistema exibe erro.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- Nenhuma

## UC16 — Emitir Relatório de Ocupação de Aulas

### Ator Principal
Gerente

### Objetivo
Avaliar demanda das aulas.

### Pré-condições
- Aulas registradas.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. Gerente solicita relatório.
2. Sistema analisa reservas.
3. Exibe ocupação.

### Fluxos Alternativos
- **A1 — Nenhuma aula cadastrada:**  
  Sistema informa ausência.

- **A2 — Falha na geração:**  
  Sistema exibe erro.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF05

### RN Relacionadas
- RN02

## UC17 — Enviar Notificação de Vencimento

### Ator Principal
Sistema

### Objetivo
Avisar sobre mensalidade.

### Pré-condições
- Mensalidade próxima do vencimento.

### Pós-condições
- Notificação enviada.

### Fluxo Principal
1. Sistema identifica vencimento.
2. Gera notificação.
3. Envia ao aluno.


### Fluxos Alternativos
- **A1 — Falha no envio:**  
  Sistema agenda nova tentativa.

- **A2 — Dados de contato inválidos:**  
  Sistema exibe erro.

### RF Relacionados
- RF010

### RNF Relacionados
- RNF01

### RN Relacionadas
- Nenhuma

## UC18 — Enviar Confirmação de Agendamento

### Ator Principal
Sistema

### Objetivo
Confirmar reserva.

### Pré-condições
- Agendamento realizado.

### Pós-condições
- Aluno notificado.

### Fluxo Principal
1. Sistema registra agendamento.
2. Envia confirmação.

### Fluxos Alternativos
- **A1 — Falha no envio:**  
  Sistema agenda reenvio.

- **A2 — Agendamento cancelado antes do envio:**  
  Notificação não enviada.

### RF Relacionados
- RF010

### RNF Relacionados
- RNF01

### RN Relacionadas
- Nenhuma


## UC19 — Enviar Notificação de Avaliação Disponível

### Ator Principal
Sistema

### Objetivo
Avisar liberação de avaliação.

### Pré-condições
- Nova avaliação permitida.

### Pós-condições
- Aluno informado.

### Fluxo Principal
1. Sistema verifica elegibilidade.
2. Envia notificação.

### Fluxos Alternativos
- **A1 — Falha no envio:**  
  Sistema agenda nova tentativa.

- **A2 — Aluno sem contato cadastrado:**  
  Sistema registra erro.

### RF Relacionados
- RF010

### RNF Relacionados
- RNF01

### RN Relacionadas
- Nenhuma

## UC20 — Atualizar Situação do Aluno

### Ator Principal
Sistema

### Objetivo
Manter status atualizado.

### Pré-condições
- Pagamento registrado.

### Pós-condições
- Situação regularizada.

### Fluxo Principal
1. Sistema recebe confirmação de pagamento.
2. Atualiza status do aluno.


### Fluxos Alternativos
- **A1 — Falha na atualização:**  
  Sistema mantém status anterior.

- **A2 — Pagamento inconsistente:**  
  Sistema solicita verificação manual.

### RF Relacionados
- RF04

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN07
