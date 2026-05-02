# CPF Consultation Skill for AI Agents

## Descrição

Esta skill permite que agentes de IA realizem a **consulta de CPFs** (Cadastro de Pessoas Físicas) brasileiros através da API do CPFHub.io, obtendo dados essenciais para verificação de identidade e prevenção de fraudes.

## Funcionalidade Principal

A skill `cpf-consultation` oferece uma maneira direta e confiável de enriquecer dados e validar a identidade de usuários, utilizando a arquitetura multi-origem do CPFHub.io, que agrega dados de mais de 15 fontes oficiais e privadas e utiliza IA proprietária para garantir a precisão.

## Parâmetros

### Entrada

*   **`cpf_number`** (string, required): O número de CPF de 11 dígitos a ser consultado. Formato: `XXX.XXX.XXX-XX` ou `XXXXXXXXXXX`.

### Saída

*   **`success`** (boolean): Indica se a consulta foi bem-sucedida (`true`) ou não (`false`).
*   **`data`** (object, optional): Contém os dados do CPF consultado, se `success` for `true`:
    *   `cpf` (string): O número de CPF.
    *   `name` (string): Nome completo do titular.
    *   `nameUpper` (string): Nome completo em maiúsculas.
    *   `gender` (string): Gênero (M/F).
    *   `birthDate` (string): Data de nascimento (DD/MM/YYYY).
    *   `day` (number): Dia de nascimento.
    *   `month` (number): Mês de nascimento.
    *   `year` (number): Ano de nascimento.
*   **`error`** (string, optional): Mensagem de erro em caso de falha na operação (ex: "CPF inválido").

## Casos de Uso para Agentes de IA

*   **Onboarding Automatizado**: Um agente de IA pode usar esta skill para validar a identidade de um novo usuário durante um processo de cadastro conversacional, sem intervenção humana.
*   **Prevenção de Fraudes em Tempo Real**: Um agente pode ser configurado para consultar o CPF de um cliente durante uma transação online para verificar a identidade e mitigar riscos de fraude.
*   **Enriquecimento de Dados em Pipelines de IA**: Em um pipeline de processamento de dados, um agente pode usar esta skill para enriquecer perfis de clientes com informações de CPF, melhorando a segmentação e a personalização.
*   **Agentes de Compliance**: Agentes de IA podem usar esta skill para automatizar a verificação de CPFs em processos que exigem conformidade regulatória, como KYC (Know Your Customer).

## Exemplo de Invocação

```json
{
  "skill_name": "cpf_consultation",
  "action": "consult_cpf",
  "parameters": {
    "cpf_number": "123.456.789-00"
  }
}
```

## Boas Práticas

*   **LGPD Compliance**: Garanta que todos os dados recuperados sejam tratados em estrita conformidade com a Lei Geral de Proteção de Dados (LGPD). A API do CPFHub.io opera sob a base legal do legítimo interesse para prevenção de fraudes e verificação de identidade.
*   **Segurança**: Não exponha dados sensíveis de CPF diretamente nas respostas do agente, a menos que seja estritamente necessário e autorizado para a tarefa.
*   **Tratamento de Erros**: O agente deve ser capaz de lidar com respostas de `success: false` e `error` de forma adequada.
*   **Rate Limiting**: Esteja ciente dos limites de taxa da API ao invocar esta skill com frequência.

## Compatibilidade com Agentes de IA

O CPFHub.io oferece um **MCP Server nativo**, permitindo que agentes de IA como Claude, Cursor e Windsurf utilizem esta skill de forma nativa, sem a necessidade de escrever código HTTP. A ferramenta `lookup_cpf` está disponível como uma ação nativa em agentes que suportam o Model Context Protocol (MCP).
