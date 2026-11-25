# Sistema de Contas - Pousada Maré Alta

Trabalho prático da disciplina de **Programação Backend** (2º TDE), focado em Programação Orientada a Objetos (POO) em Java.

O projeto simula o sistema de fechamento de contas de uma pousada, calculando diárias de diferentes tipos de quartos, passeios e consumos extras, aplicando descontos e gerando um extrato final.

##  Tecnologias Utilizadas
- **Java** (JDK 17 ou superior)
- **IntelliJ IDEA** (IDE utilizada para o desenvolvimento)

##  Estrutura do Projeto

O sistema foi modelado com os seguintes componentes:

### Classes Principais
- **`Quarto`**: Classe base (mãe) que contém número e diária base.
- **`QuartoLuxo`**: Herda de `Quarto`. Adiciona taxa de luxo e inclui café da manhã/frigobar.
- **`Chale`**: Herda de `Quarto`. Adiciona o valor por hóspede extra (R$ 45,00).
- **`Reserva`**: Liga um quarto a um número de noites.
- **`Conta`**: Agrupa os itens (`Cobravel[]`) e gera o extrato com total e desconto.

### Interface
- **`Cobravel`**: Contrato que define que qualquer item cobrável deve ter `descricao()` e `calcularValor()`. Implementada por `Reserva`, `Passeio` e `ConsumoRestaurante`.

### Classe de Extensão (Criada pela Equipe)
- **`ConsumoRestaurante`**: Representa um item extra na conta (prato, valor e quantidade). Foi adicionada ao vetor de itens sem alterar a classe `Conta`, demonstrando o uso de polimorfismo.

##  Como Executar

1. Clone o repositório ou baixe o arquivo `.zip`.
2. Abra o projeto no **IntelliJ IDEA**.
3. Certifique-se de que todos os arquivos `.java` estão na pasta `src`.
4. Localize a classe `Main.java` e execute-a (Run 'Main.main()').

##  Diagrama de Classes e Justificativas

O diagrama UML completo e a tabela de justificativa das relações estão disponíveis no arquivo **'BACKEND_Diagrama_E_Tabela.pdf'* (incluído no repositório/entrega).

Abaixo, o resumo das relações do sistema:

| Relação | Frase-teste | Em Java |
| :--- | :--- | :--- |
| **QuartoLuxo e Quarto** | "QuartoLuxo **é um** Quarto" | `extends` |
| **Chale e Quarto** | "Chale **é um** Quarto" | `extends` |
| **Reserva e Quarto** | "Reserva **tem um** Quarto" | `atributo` |
| **Conta e Cobravel** | "Conta **tem vários** itens Cobravel" | `atributo` (que é vetor) |
| **Reserva e Cobravel** | "Reserva **sabe se cobrar**" | `implements` |
| **Passeio e Cobravel** | "Passeio **sabe se cobrar**" | `implements` |
| **ConsumoRestaurante e Cobravel** | "ConsumoRestaurante **sabe se cobrar**" | `implements` |

## 👨‍💻 Autor
- **Oliver Wemilly Lima dos Anjos Oliveira** (Desenvolvimento individual)

*Trabalho desenvolvido para a disciplina de Programação Backend - 4º Período - 2026.*
