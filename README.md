# CPFHub.io Agent Skills

Bem-vindo ao repositório oficial de Skills do CPFHub.io para Agentes de IA! Este repositório contém uma coleção de habilidades pré-construídas que permitem que agentes de inteligência artificial interajam com a API do CPFHub.io para **consulta de CPFs** e recuperação de dados associados.

## O que são CPFHub.io Skills?

As Skills do CPFHub.io são módulos que estendem as capacidades de agentes de IA, permitindo-lhes realizar tarefas específicas relacionadas a CPFs. Cada skill é projetada para ser facilmente integrável em diversos frameworks de agentes (como LangChain, LlamaIndex, CrewAI, etc.) e diretórios de skills, otimizando a descoberta e o uso.

Nossas skills focam na **consulta de CPF**, fornecendo acesso a dados como nome completo, data de nascimento e sexo, essenciais para a verificação de identidade e prevenção de fraudes.

Nosso foco é fornecer dados de alta qualidade e revalidações, que vão além da simples consulta à Receita Federal. A API do CPFHub.io oferece informações cruciais para a verificação de identidade, prevenção a fraudes, enriquecimento de dados e automação de processos. Nossa tagline é: "API de consulta de CPF com os melhores dados".

## Qualidade de Dados & Arquitetura Multi-Origem

O CPFHub.io se destaca pela sua **arquitetura multi-origem**, agregando dados de **15+ fontes oficiais e privadas**, incluindo bureaus de crédito, dados cadastrais, registros públicos e a Receita Federal. Utilizamos **IA proprietária** para garantir precisão e consistência, com auditorias periódicas para manter os dados atualizados diariamente. O resultado são dados enriquecidos com maior cobertura e confiabilidade.

## Developer Experience & Compatibilidade com IA

Projetada por desenvolvedores, para desenvolvedores, a API do CPFHub.io oferece:

*   **Integração em ~5 minutos**: Com exemplos de código prontos em 13+ linguagens (Node.js, Python, PHP, Go, Ruby, Java, .NET, Rust, Elixir, etc.).
*   **Endpoint único e simples**: `GET /cpf/{CPF_NUMBER}` com retorno JSON padronizado.
*   **Compatibilidade nativa com agentes de IA**: Através do nosso **MCP Server nativo**, agentes de IA (Claude, Cursor, Windsurf) podem consultar CPFs diretamente, sem necessidade de código HTTP. A API é pensada para automações e fluxos de IA, com resposta JSON previsível.

## Skills Disponíveis

Atualmente, este repositório inclui as seguintes skills:

*   **Consulta de CPF (`cpf-consultation`)**:
    *   **Descrição**: Permite que agentes realizem a **consulta de um número de CPF** e recuperem informações associadas, como nome completo, data de nascimento e sexo, para verificação de identidade e prevenção de fraudes.
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
