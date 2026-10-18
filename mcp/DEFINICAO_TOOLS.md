# Definição do Servidor MCP - MarcaConsulta

O objetivo deste servidor MCP é permitir que um agente de IA consulte e modifique a agenda de consultas da clínica de forma autônoma.

## 1 e 2. Ferramentas (Tools) disponíveis para o Agente

Abaixo estão as 3 ferramentas que o agente poderá usar, mapeando o que a aplicação já faz:

### Tool 1: `listar_consultas_medico` (LEITURA)
* **O que faz:** Retorna uma lista com todas as consultas agendadas para um médico específico em um determinado dia.
* **Entrada (Input):** `id_medico`, `data_consulta`
* **Saída (Output):** Lista em JSON com nomes dos pacientes, horários e status.

### Tool 2: `cadastrar_novo_paciente` (ESCRITA)
* **O que faz:** Permite que o agente crie um novo registro de paciente no banco de dados, útil quando alguém liga para agendar e ainda não tem cadastro.
* **Entrada (Input):** `nome`, `cpf`, `telefone`, `email`
* **Saída (Output):** ID do paciente criado e mensagem de sucesso.

### Tool 3: `agendar_consulta` (ESCRITA)
* **O que faz:** Marca uma nova consulta para um paciente com um médico em um horário vago.
* **Entrada (Input):** `id_paciente`, `id_medico`, `data_hora`
* **Saída (Output):** Status de confirmação do agendamento.

## 3. Documentação para o Agente (Docstrings)
*Instruções que o agente lerá antes de usar a ferramenta.*
* **Atenção Agente:** Antes de usar a tool `agendar_consulta`, você **DEVE OBRIGATORIAMENTE** usar a tool `listar_consultas_medico` para garantir que não há conflito de horário. Nunca agende duas consultas no mesmo horário.
