
# Casos de Uso – Sistema FitPass Gym Management

---

## UC01 — Realizar Cadastro de Aluno

### Ator Principal
Recepcionista

### Objetivo
Permitir registrar um novo aluno no sistema.

### Pré-condições
- Recepcionista autenticado.

### Pós-condições
- Aluno cadastrado com sucesso.

### Fluxo Principal
1. Recepcionista acessa cadastro.
2. Informa dados do aluno.
3. Sistema valida informações.
4. Sistema registra aluno.

### Fluxos Alternativos
- **A1 — Dados incompletos:** sistema solicita correção.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF02
- RNF04

### RN Relacionadas
- RN06

---

## UC02 — Editar Dados do Aluno

### Ator Principal
Recepcionista

### Objetivo
Atualizar informações do aluno.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Dados atualizados.

### Fluxo Principal
1. Recepcionista busca aluno.
2. Sistema exibe dados.
3. Recepcionista altera informações.
4. Sistema salva alterações.

### Fluxos Alternativos
- **A1 — Aluno não encontrado:** sistema informa erro.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF02

### RN Relacionadas
- RN06

---

## UC03 — Criar Plano

### Ator Principal
Gerente

### Objetivo
Criar novo plano da academia.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Plano criado.

### Fluxo Principal
1. Gerente acessa área de planos.
2. Informa dados do plano.
3. Sistema salva plano.

### Fluxos Alternativos
- **A1 — Dados inválidos:** sistema solicita correção.

### RF Relacionados
- RF02

### RNF Relacionados
- RNF05

### RN Relacionadas
- RN06

---

## UC04 — Editar Plano

### Ator Principal
Gerente

### Objetivo
Alterar plano existente.

### Pré-condições
- Plano existente.

### Pós-condições
- Plano atualizado.

### Fluxo Principal
1. Gerente seleciona plano.
2. Altera informações.
3. Sistema salva alterações.

### RF Relacionados
- RF02

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06

---

## UC05 — Registrar Pagamento

### Ator Principal
Recepcionista

### Objetivo
Registrar pagamento de mensalidade.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Pagamento registrado.

### Fluxo Principal
1. Recepcionista seleciona aluno.
2. Escolhe método de pagamento.
3. Sistema registra pagamento.

### Fluxos Alternativos
- **A1 — Pagamento inválido:** sistema informa erro.

### RF Relacionados
- RF03

### RNF Relacionados
- RNF02

### RN Relacionadas
- RN04
- RN07

---

## UC06 — Verificar Regularidade do Aluno

### Ator Principal
Sistema

### Objetivo
Verificar se mensalidade está em dia.

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- Status atualizado.

### Fluxo Principal
1. Sistema consulta pagamentos.
2. Verifica vencimento.
3. Define situação do aluno.

### RF Relacionados
- RF04

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

---

## UC07 — Validar Acesso na Catraca

### Ator Principal
Sistema de Catraca

### Objetivo
Autorizar ou negar entrada do aluno.

### Pré-condições
- RFID cadastrado.

### Pós-condições
- Acesso liberado ou bloqueado.

### Fluxo Principal
1. RFID é lido.
2. Sistema verifica situação.
3. Sistema retorna autorização.

### Fluxos Alternativos
- **A1 — Aluno inadimplente:** acesso bloqueado.

### RF Relacionados
- RF05

### RNF Relacionados
- RNF06

### RN Relacionadas
- RN01

---

## UC08 — Visualizar Aulas

### Ator Principal
Aluno

### Objetivo
Consultar horários de aulas.

### Fluxo Principal
1. Aluno acessa agenda.
2. Sistema exibe aulas disponíveis.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN02

---

## UC09 — Agendar Aula

### Ator Principal
Aluno

### Objetivo
Reservar vaga em aula.

### Fluxo Principal
1. Aluno seleciona aula.
2. Sistema verifica vagas.
3. Sistema confirma reserva.

### Fluxos Alternativos
- **A1 — Aula lotada:** reserva negada.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN02

---

## UC10 — Cancelar Agendamento

### Ator Principal
Aluno

### Objetivo
Cancelar reserva de aula.

### Fluxo Principal
1. Aluno acessa reserva.
2. Seleciona cancelar.
3. Sistema remove reserva.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN03

---

## UC11 — Registrar Presença

### Ator Principal
Instrutor

### Objetivo
Registrar presença de alunos.

### Fluxo Principal
1. Instrutor acessa lista.
2. Marca presença.
3. Sistema salva presença.

### RF Relacionados
- RF07

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN06

---

## UC12 — Registrar Avaliação Física

### Ator Principal
Instrutor

### Objetivo
Registrar dados físicos do aluno.

### Fluxo Principal
1. Instrutor seleciona aluno.
2. Insere dados físicos.
3. Sistema salva avaliação.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF02

### RN Relacionadas
- RN05

---

## UC13 — Anexar Arquivo na Avaliação

### Ator Principal
Instrutor

### Objetivo
Adicionar arquivos complementares à avaliação física do aluno.

### Pré-condições
- O aluno deve possuir uma avaliação física registrada.
- Instrutor autenticado no sistema.

### Pós-condições
- Arquivo anexado à avaliação física do aluno.

### Fluxo Principal
1. O instrutor acessa o perfil do aluno.
2. O instrutor abre a avaliação física existente.
3. O instrutor seleciona a opção de anexar arquivo.
4. O sistema solicita o envio do arquivo.
5. O instrutor seleciona o arquivo.
6. O sistema salva o arquivo na avaliação.

### Fluxos Alternativos
- **A1 — Arquivo inválido:**  
  O sistema informa que o formato do arquivo não é permitido.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF02

### RN Relacionadas
- RN05

---

## UC14 — Consultar Avaliação Física

### Ator Principal
Aluno

### Objetivo
Permitir que o aluno visualize suas avaliações físicas registradas.

### Pré-condições
- Aluno autenticado.
- Avaliações físicas registradas no sistema.

### Pós-condições
- Avaliações exibidas ao aluno.

### Fluxo Principal
1. O aluno acessa o menu de avaliações físicas.
2. O sistema consulta as avaliações registradas.
3. O sistema exibe o histórico de avaliações.

### Fluxos Alternativos
- **A1 — Nenhuma avaliação registrada:**  
  O sistema informa que não existem avaliações disponíveis.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN05

---

## UC15 — Emitir Relatório de Inadimplência

### Ator Principal
Gerente

### Objetivo
Gerar relatório de alunos inadimplentes.

### Pré-condições
- Gerente autenticado no sistema.

### Pós-condições
- Relatório gerado e exibido.

### Fluxo Principal
1. O gerente acessa a área de relatórios.
2. Seleciona relatório de inadimplência.
3. O sistema consulta alunos com pagamentos vencidos.
4. O sistema gera o relatório.
5. O sistema apresenta os dados ao gerente.

### Fluxos Alternativos
- **A1 — Nenhum aluno inadimplente:**  
  O sistema informa que não há registros.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN01

---

## UC16 — Emitir Relatório de Alunos Ativos

### Ator Principal
Gerente

### Objetivo
Gerar relatório com alunos ativos na academia.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. O gerente acessa a área de relatórios.
2. Seleciona relatório de alunos ativos.
3. O sistema consulta os alunos ativos.
4. O sistema gera o relatório.
5. O sistema exibe os resultados.

### Fluxos Alternativos
- **A1 — Nenhum aluno ativo:**  
  O sistema informa que não existem registros.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN06

---

## UC17 — Emitir Relatório de Acessos

### Ator Principal
Gerente

### Objetivo
Consultar histórico de entradas na academia.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Histórico de acessos exibido.

### Fluxo Principal
1. O gerente acessa a área de relatórios.
2. Seleciona relatório de acessos.
3. O sistema consulta registros da catraca.
4. O sistema gera o relatório.
5. O sistema exibe o histórico.

### Fluxos Alternativos
- **A1 — Nenhum registro encontrado:**  
  O sistema informa ausência de dados.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF03
- RNF06

### RN Relacionadas
- RN06

---

## UC18 — Emitir Relatório de Ocupação de Aulas

### Ator Principal
Gerente

### Objetivo
Analisar o nível de ocupação das aulas.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório exibido.

### Fluxo Principal
1. O gerente acessa a área de relatórios.
2. Seleciona relatório de ocupação das aulas.
3. O sistema consulta agendamentos.
4. O sistema gera relatório.
5. O sistema apresenta resultados.

### Fluxos Alternativos
- **A1 — Nenhum agendamento registrado:**  
  O sistema informa ausência de dados.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF05

### RN Relacionadas
- RN02

---

## UC19 — Enviar Notificação de Mensalidade

### Ator Principal
Sistema

### Objetivo
Avisar alunos sobre vencimento da mensalidade.

### Pré-condições
- Aluno cadastrado no sistema.
- Data próxima ao vencimento.

### Pós-condições
- Notificação enviada ao aluno.

### Fluxo Principal
1. O sistema verifica mensalidades próximas do vencimento.
2. O sistema gera notificações.
3. O sistema envia mensagem ao aluno.

### Fluxos Alternativos
- **A1 — Falha no envio:**  
  O sistema registra erro e tenta novamente.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN07

---

## UC20 — Enviar Confirmação de Agendamento

### Ator Principal
Sistema

### Objetivo
Notificar o aluno sobre confirmação de agendamento.

### Pré-condições
- Agendamento de aula realizado.

### Pós-condições
- Confirmação enviada ao aluno.

### Fluxo Principal
1. O aluno realiza o agendamento.
2. O sistema registra a reserva.
3. O sistema gera notificação.
4. O sistema envia confirmação ao aluno.

### Fluxos Alternativos
- **A1 — Falha no envio da notificação:**  
  O sistema registra o erro.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF03

### RN Relacionadas
- RN02
