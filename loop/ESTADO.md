# Diário de Bordo do Loop (ESTADO.md)

## Volta 1
* **O que o agente fez:** Tentou alterar o model do banco e o Dockerfile para resolver conflitos de horário.
* **Por que falhou:** O agente violou as regras do PROMPT.md ao tentar alterar o Dockerfile (parte que ele não podia tocar).
* **Decisão do Porteiro:** Reprovar e mandar tentar novamente sem tocar no Dockerfile.

## Volta 2
* **O que o agente fez:** Alterou o `agendamento_service.py` adicionando a verificação `if` de conflito de horário.
* **Por que não parou:** A lógica estava correta, mas o agente não criou uma forma da máquina conferir (teste automatizado).
* **Decisão do Porteiro:** Mandar tentar novamente incluindo testes.

## Volta 3
* **O que o agente fez:** Implementou a lógica no backend e criou o teste `test_conflito_horario` na pasta `tests/`.
* **Por que parou:** O critério de parada foi atingido (o teste automatizado cobre a regra de negócio e a máquina consegue rodar).
* **Decisão do Porteiro:** Aprovado. Loop encerrado.
