## Requisitos Funcionais
### Limites
RF21 - O sistema deve permitir o registro de Limites.

RF22 - O sistema deve permitir a edição de Limites.

RF23 - O sistema deve permitir a remoção de Limites.
### Despesas
RF01 - O sistema deve permitir o registro de despesas.

RF02 - O sistema deve permitir a edição de despesas.

RF03 - O sistema deve permitir a remoção de despesas.

RF04 - O sistema deve permitir a listagem de despesas.

RF06 - O sistema deve validar se uma despesa ultrapassa o limite definido pelo usuário e alertá-lo.

### Rendas
RF07 - O sistema deve permitir o registro de rendas.

RF08 - O sistema deve permitir a edição de rendas.

RF09 - O sistema deve permitir a remoção de rendas.

RF10 - O sistema deve permitir a listagem de rendas.

### Categorias
RF11 - O sistema deve permitir o registro de categorias.

RF12 - O sistema deve permitir a edição de categorias.

RF13 - O sistema deve permitir a remoção de categorias.

RF19 - O sistema deve verificar se a categoria ainda está sendo utilizada antes de excluir.

RF20 - O sistema deve bloquear a exclusão caso a categoria esteja sendo utilizada.

### Consultas
RF14 - O sistema deve permitir a consulta de despesas por período.

RF15 - O sistema deve permitir a consulta de despesas por categoria.

RF16 - O sistema deve permitir a consulta de renda bruta.

RF17 - O sistema deve permitir a consulta de renda líquida.

RF18 - O sistema deve permitir que o usuário habilite notificações quando a renda líquida estiver negativa.

---

## Requisitos Não Funcionais

RNF01 - O sistema deve ser desenvolvido como uma API REST.

RNF02 - O sistema deve validar os dados de entrada antes de processá-los.

RNF03 - O sistema deve retornar respostas padronizadas.

RNF04 - O sistema deve garantir que um usuário acesse apenas seus próprios dados.

RNF05 - O sistema deve tratar erros de forma consistente e informativa.



---

## Regras de Negócio

RN01 - Todos os dados pertencem a um único usuário e não podem ser acessados por outros.

### Despesas
RN02 - Uma despesa só é válida se possuir valor maior que zero.

RN03 - Uma despesa deve obrigatoriamente possuir valor, data, categoria e pode possuir descrição.

### Rendas
RN07 - Uma renda só é válida se possuir valor maior que zero.

RN08 - Uma renda deve possuir obrigatoriamente valor, data, categoria e pode possuir descrição.

### Cálculos
RN09 - A renda líquida é calculada como a soma das rendas menos a soma das despesas dentro de um período selecionado.

RN10 - A renda líquida pode ser menor ou igual a zero.

### Categorias
RN11 - Uma categoria deve possuir nome, descrição e tipo (RENDA|DESPESA).

RN12 - Uma categoria deve ser única por usuário, não podendo existir duas categorias com o mesmo nome e tipo.


### Limites
RN04 - O limite de despesas deve possuir valor maior que zero.

RN05 - O limite de despesas deve possuir valor, data de inicio e data fim.

RN06 - O limite de despesas deve ser aplicado dentro de um período definido.

RN13 - Não é permitido que um usuário possua limites com períodos sobrepostos

RN17 - O limite de despesas considera a soma de todas as despesas no período




### Consistencia
RN16 - A edição de rendas e despesas só pode acontecer se for do mês atual.
