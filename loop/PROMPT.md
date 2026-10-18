# Loop da AP1 - MarcaConsulta

## 1. Tarefa Recorrente e Gatilho
* **Tarefa:** Melhorar a validação de horário na tela de agendamento da recepção.
* **Gatilho (Evento):** Quando o usuário clica no botão "Confirmar Agendamento".

## 2. Critério de Parada (O que a máquina deve conferir)
* O critério de parada é **ESTRITAMENTE** que o código não permita que dois agendamentos sejam feitos para o mesmo médico no mesmo horário.
* A máquina deve verificar se a regra de negócio está implementada no backend (Python/FastAPI).

## 3. Limites do Agente (Quando parar e chamar os humanos)
* **Parar imediatamente e chamar os humanos se:** precisar alterar o banco de dados de produção, se precisar mexer em arquivos de autenticação ou se precisar alterar o `render.yaml` ou `Dockerfile`.
* **Não pode tocar em:** pastas `.github/`, arquivos `.env`, configurações do Docker.

## Instrução para a IA
Você é um agente de IA trabalhando no projeto MarcaConsulta. Leia as especificações acima. Gere o código necessário para garantir que a regra de conflito de horário funcione. Se precisar alterar arquivos fora do escopo permitido, pare e avise.
