# CPFHub.io Agent Skills

Bem-vindo ao repositório oficial de Skills do CPFHub.io para Agentes de IA! Este repositório contém uma coleção de habilidades pré-construídas que permitem que agentes de inteligência artificial interajam com a API do CPFHub.io para validação de CPFs e recuperação de dados associados.

## O que são CPFHub.io Skills?

As Skills do CPFHub.io são módulos que estendem as capacidades de agentes de IA, permitindo-lhes realizar tarefas específicas relacionadas a CPFs. Cada skill é projetada para ser facilmente integrável em diversos frameworks de agentes (como LangChain, LlamaIndex, CrewAI, etc.) e diretórios de skills, otimizando a descoberta e o uso.

Nosso foco é fornecer dados de alta qualidade e revalidações, que vão além da simples consulta à Receita Federal. A API do CPFHub.io oferece informações cruciais para a verificação de identidade, prevenção a fraudes, enriquecimento de dados e automação de processos. Nossa tagline é: "API de consulta de CPF com os melhores dados".

## Verificação de Identidade e Mais

A API do CPFHub.io não se limita a uma simples validação de CPF. Ela oferece um conjunto de informações que, quando combinadas, permitem uma verificação de identidade mais robusta e confiável. Alguns dos dados que podem ser obtidos através da nossa API incluem:

*   **Nome Completo**: Confirmação do nome associado ao CPF.
*   **Situação Cadral na Receita Federal**: Verificação se o CPF está regular, pendente de regularização, suspenso, cancelado ou nulo.
*   **Data de Nascimento**: Validação da idade do titular do CPF.
*   **Endereço Parcial**: Informações de endereço que podem ser usadas para validação adicional.

Essas informações são essenciais para uma variedade de casos de uso, desde o onboarding de clientes até a prevenção de fraudes.

## Skills Disponíveis

Atualmente, este repositório inclui as seguintes skills:

*   **Validação de CPF (`cpf-validation`)**:
    *   **Descrição**: Permite que agentes verifiquem a validade sintática de um número de CPF e recuperem informações públicas associadas, se disponíveis.
    *   **Detalhes**: [cpf-validation/SKILL.md](cpf-validation/SKILL.md)

## Como Usar

Para utilizar as skills do CPFHub.io em seu agente de IA, siga as instruções detalhadas no arquivo `SKILL.md` de cada skill. Geralmente, o processo envolve:

1.  **Integração**: Adicione a skill ao seu framework de agente preferido.
2.  **Configuração**: Forneça as credenciais necessárias para acessar a API do CPFHub.io.
3.  **Invocação**: Chame a skill com os parâmetros de entrada apropriados.

## Contribuição

Aceitamos contribuições da comunidade para melhorar as skills existentes ou adicionar novas. Por favor, consulte nosso guia de contribuição (em breve) para mais detalhes sobre como submeter Pull Requests.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Contato

Para dúvidas, suporte ou parcerias, entre em contato conosco em contact@cpfhub.io.
