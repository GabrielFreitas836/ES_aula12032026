## UC01 — Realizar Login

### Ator Principal
Usuário (Aluno, Recepcionista, Instrutor, Gerente)

### Objetivo
Autenticar o usuário para acesso às funcionalidades do sistema de acordo com seu perfil.

### Pré-condições
- Usuário deve possuir cadastro ativo.

### Pós-condições
- Sessão iniciada com sucesso e permissões carregadas.

### Fluxo Principal
1. O usuário informa e-mail e senha.
2. O sistema valida as credenciais.
3. O sistema autentica o usuário e redireciona para a dashboard correspondente ao perfil.

### Fluxos Alternativos
- **A1 — Credenciais Incorretas:**  
  O sistema exibe mensagem de erro e solicita nova tentativa.

- **A2 — Conta bloqueada:**  
  O sistema impede o login e instrui o usuário a recuperar o acesso.

### RF Relacionados
- RF01, RF09

### RNF Relacionados
- RNF02, RNF03, RNF04

### RN Relacionadas
- RN06



## UC02 — Cadastrar Novo Aluno

### Ator Principal
Recepcionista

### Objetivo
Registrar um novo cliente na base de dados da academia.

### Pré-condições
Recepcionista autenticado no sistema.

### Pós-condições
Registro do aluno criado no banco de dados.

### Fluxo Principal
1. O recepcionista acessa o menu "Matrículas".
2. Preenche dados pessoais, contato, endereço e seleciona o plano.
3. O sistema valida os campos obrigatórios.
4. O sistema salva o cadastro e gera o ID único do aluno.

### Fluxos Alternativos
- **A1 — Dados Inválidos:**  
O sistema destaca os campos incorretos e solicita correção.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF02, RNF04

### RN Relacionadas
- RN06



## UC03 — Gerenciar Tipos de Planos

### Ator Principal
Gerente

### Objetivo
Criar ou editar as modalidades de planos oferecidas pela academia.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Plano atualizado ou criado na base de dados.

### Fluxo Principal
1. O gerente acessa "Configurações de Planos".
2. Define nome, valor, duração e descrição.
3. O sistema salva as alterações.

### Fluxos Alternativos
- **A1 — Desativar Plano:**
O gerente seleciona um plano existente e marca como "Inativo".

### RF Relacionados
- RF02

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06



## UC04 — Registrar Pagamento na Recepção

### Ator Principal
Recepcionista

### Objetivo
Processar o pagamento presencial de mensalidades.

### Pré-condições
- Aluno identificado no sistema.

### Pós-condições
- Status de pagamento atualizado e recibo gerado.

### Fluxo Principal
1. O recepcionista seleciona a parcela em aberto do aluno.
2. Escolhe o método (Dinheiro, Cartão ou PIX).
3. O sistema processa a transação e confirma o recebimento integral.
4. O sistema atualiza a regularidade do aluno instantaneamente.

### Fluxos Alternativos
- **A1 — Pagamento Parcial:**
O sistema bloqueia a operação informando que apenas valores integrais são aceitos.

### RF Relacionados
- RF03, RF04

### RNF Relacionados
- RNF02, RNF03

### RN Relacionadas
- RN04, RN07



## UC05 — Validar Acesso na Catraca (RFID)

### Ator Principal
Sistema de Catraca (API)

### Objetivo
Controlar a entrada física do aluno na unidade.

### Pré-condições
- Aluno aproxima o cartão/tag RFID no leitor.

### Pós-condições
- Acesso liberado ou bloqueado.

### Fluxo Principal
1. A API da catraca envia o ID do RFID para o sistema FitPass.
2. O sistema verifica a regularidade financeira do aluno.
3. O sistema retorna o comando de "Liberar" para a catraca.

### Fluxos Alternativos
- **A1 — Inadimplência (> 5 dias):**
O sistema retorna comando "Bloquear" e exibe mensagem na tela da catraca.
- **A2 — Plano Inativo:
O sistema nega o acesso.

### RF Relacionados
- RF04, RF05

### RNF Relacionados
- RNF03, RNF06

### RN Relacionadas
- RN01



## UC06 — Agendar Aula

### Ator Principal
Aluno

### Objetivo
Reservar uma vaga em uma aula coletiva específica.

### Pré-condições
- Aluno autenticado e com mensalidade em dia.

### Pós-condições
- Vaga reservada e confirmada.

### Fluxo Principal
1. O aluno visualiza a grade de horários.
2. Seleciona a aula desejada.
3. O sistema verifica a disponibilidade de vagas.
4. O sistema confirma o agendamento.

### Fluxos Alternativos
- **A1 — Aula Lotada:**
O sistema informa que não há mais vagas e bloqueia a reserva.

### RF Relacionados
- RF06, RF10

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN02



## UC07 — Cancelar Agendamento de Aula

### Ator Principal
Aluno

### Objetivo
Desistir de uma reserva previamente feita.

### Pré-condições
- Possuir um agendamento futuro.

### Pós-condições
- Vaga liberada para outros alunos.

### Fluxo Principal
1. O aluno acessa "Meus Agendamentos".
2. Solicita o cancelamento da aula selecionada.
3. O sistema valida o tempo de antecedência.
4. O sistema confirma a exclusão do agendamento.

### Fluxos Alternativos
- **A1 — Fora do Prazo:**
Se faltar menos de 1 hora, o sistema impede o cancelamento.

### RF Relacionados
- RF06

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN03



## UC08 — Registrar Lista de Presença

### Ator Principal
Instrutor

### Objetivo
Confirmar quais alunos agendados compareceram à aula.

### Pré-condições
- Aula iniciada ou finalizada.

### Pós-condições
- Presença computada no histórico do aluno.

### Fluxo Principal
1. O instrutor acessa a lista de alunos agendados para sua aula.
2. Marca o check-in dos presentes.
3. O sistema salva as presenças.

### Fluxos Alternativos
- **A1 — Fora do Prazo:**
Se faltar menos de 1 hora, o sistema impede o cancelamento.

### RF Relacionados
- RF07

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06



## UC09 — Registrar Avaliação Física

### Ator Principal
Instrutor

### Objetivo
Coletar e armazenar dados biométricos do aluno.

### Pré-condições
- Aluno deve estar ativo e regular financeiramente.

### Pós-condições
- Avaliação salva e notificação enviada ao aluno.

### Fluxo Principal
1. O instrutor seleciona o aluno.
2. Insere dados como peso, IMC e percentual de gordura.
3. O sistema salva o registro e notifica o aluno.

### Fluxos Alternativos
- **A1 — Aluno Inadimplente:**
O sistema impede a abertura do formulário de avaliação.

### RF Relacionados
- RF08, RF10

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN05, RN06



## UC10 — Emitir Relatório de Inadimplência

### Ator Principal
Gerente

### Objetivo
Identificar alunos com pagamentos atrasados para ações de cobrança.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório gerado em tela ou PDF.

### Fluxo Principal
1. O gerente seleciona "Relatórios > Inadimplência".
2. Define o período de filtro.
3. O sistema gera a lista de alunos com débitos.

### Fluxos Alternativos
- **A1 — Nenhum aluno inadimplente encontrado:**
O sistema exibe mensagem informando que não há inadimplências no período selecionado.

### RF Relacionados
- RF09

### RNF Relacionados
- RNF05

### RN Relacionadas
- RN06



## UC11 — Gerar Boleto/Cartão Online

### Ator Principal
Aluno

### Objetivo
Permitir o pagamento da mensalidade via aplicativo/web.

### Pré-condições
- Mensalidade próxima do vencimento ou vencida.

### Pós-condições
- Linha digitável ou QR Code PIX gerado.

### Fluxo Principal
1. O aluno acessa a área financeira.
2. Seleciona a fatura e clica em "Pagar".
3. O sistema gera o documento de cobrança.

### Fluxos Alternativos
- **A1 — Fatura já paga:**
O sistema informa que a fatura já está quitada e impede a geração de nova cobrança.

### RF Relacionados
- RF03

### RNF Relacionados
- RNF02, RNF04

### RN Relacionadas
- RN04



## UC12 — Notificar Vencimento de Mensalidade

### Ator Principal
Sistema (Automático)

### Objetivo
Alertar o aluno sobre o prazo de pagamento.

### Pré-condições
- Mensalidade a 3 dias do vencimento.

### Pós-condições
- Notificação enviada por Push/E-mail.

### Fluxo Principal
1. O sistema varre a base de dados diariamente.
2. Identifica contas a vencer.
3. Dispara notificação automática.

### Fluxos Alternativos
- **A1 — Falha no envio da notificação:**
O sistema agenda uma nova tentativa de envio da notificação.

### RF Relacionados
- RF10

### RNF Relacionados
- RNF01

### RN Relacionadas
- N/A



## UC13 — Consultar Histórico de Acessos

### Ator Principal
Gerente

### Objetivo
Monitorar o fluxo de pessoas na academia por período.

### Pré-condições
- Gerente autenticado no sistema.
- Registros de acesso armazenados no sistema.

### Pós-condições
- Histórico de acessos exibido na tela para consulta.

### Fluxo Principal
1. Gerente acessa "Relatórios de Acesso".
2. O sistema solicita o período de consulta.
3. O gerente informa o intervalo de datas.
4. O sistema consulta os registros da catraca.
5. O sistema exibe os logs de acesso com data e horário.

### Fluxos Alternativos
- **A1 — Nenhum registro encontrado:**  
O sistema exibe uma mensagem informando que não há registros disponíveis.

### RF Relacionados
- RF09

### RNF Relacionados
- N/A

### RN Relacionadas
- RN06



## UC14 — Editar Cadastro de Aluno

### Ator Principal
Recepcionista

### Objetivo
Atualizar informações de endereço ou contato do aluno.

### Pré-condições
- Recepcionista autenticado no sistema.

### Pós-condições
- Dados do aluno atualizados com sucesso no sistema.

### Fluxo Principal
1. Recepcionista busca o aluno.
2. Altera os campos necessários e salva.

### Fluxos Alternativos
- **A1 — Aluno não encontrado:**  
O sistema exibe mensagem informando que o aluno não foi encontrado. 

### RF Relacionados
- RF01

### RNF Relacionados
- N/A

### RN Relacionadas
- RN06



## UC15 — Emitir Relatório de Ocupação de Aulas

### Ator Principal
Gerente

### Objetivo
Analisar quais aulas possuem maior demanda.

### Pré-condições
- Gerente autenticado no sistema.
- Registros de aulas e presenças cadastrados no sistema. 

### Pós-condições
- Relatório de ocupação exibido com dados de vagas preenchidas e disponíveis.

### Fluxo Principal
1. Gerente acessa "Relatório de Ocupação".
2. O sistema mostra gráficos de vagas preenchidas vs disponíveis.

### Fluxos Alternativos
- **A1 — Relatório de ocupação exibido com dados de vagas preenchidas e disponíveis:**  
O sistema informa que não há informações disponíveis e permite nova consulta.

### RF Relacionados
- RF09

### RNF Relacionados
- N/A

### RN Relacionadas
- RN06



## UC16 — Vincular Tag RFID ao Aluno

### Ator Principal
Recepcionista

### Objetivo
Associar um cartão físico ao perfil do aluno para uso na catraca.

### Pré-condições
- Recepcionista autenticado no sistema.
- Aluno previamente cadastrado no sistema.

### Pós-condições
- Tag RFID vinculada ao cadastro do aluno.

### Fluxo Principal
1. Recepcionista abre o perfil do aluno.
2. Clica em "Vincular RFID" e aproxima a tag no leitor da recepção.
3. O sistema grava o código no cadastro.

### Fluxos Alternativos
- **A1 — Falha na leitura da tag RFID:**  
O sistema não consegue identificar o código da tag.

### RF Relacionados
- RF01, RF05

### RNF Relacionados
- N/A

### RN Relacionadas
- RN06



## UC17 — Visualizar Evolução Física

### Ator Principal
Aluno

### Objetivo
Consultar os resultados das suas avaliações físicas.

### Fluxo Principal
1. Aluno acessa "Minha Evolução".
2. O sistema exibe histórico de peso e medidas.

### RF Relacionados
- RF08

### RNF Relacionados
- RNF04

### RN Relacionadas
- N/A



## UC18 — Ativar/Desativar Plano de Aluno

### Ator Principal
Gerente

### Objetivo
Interromper o acesso de um aluno por motivos administrativos (ex: trancamento).

### Fluxo Principal
1. Gerente localiza o contrato do aluno.
2. Altera o status para "Suspenso" ou "Ativo".

### RF Relacionados
- RF02

### RNF Relacionados
- N/A

### RN Relacionadas
- RN06



## UC19 — Notificar Confirmação de Agendamento

### Ator Principal
Sistema (Automático)

### Objetivo
Confirmar ao aluno que sua vaga foi reservada com sucesso.

### Fluxo Principal
1. Após a conclusão do UC06, o sistema envia mensagem de confirmação imediata.

### RF Relacionados
- RF10

### RNF Relacionados
- N/A

### RN Relacionadas
- RN02



## UC20 — Listar Alunos Ativos

### Ator Principal
Gerente

### Objetivo
Obter a contagem total de clientes matriculados com contrato vigente.

### Fluxo Principal
1. Gerente solicita "Relatório de Alunos Ativos".
2. O sistema filtra por status do contrato e exibe a lista.

### RF Relacionados
- RF09

### RNF Relacionados
- N/A

### RN Relacionadas
- RN06
