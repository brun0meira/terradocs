# Introdução ao Terraform

## O que é Terraform?

Terraform é uma ferramenta de código aberto desenvolvida pela HashiCorp, que permite a criação, atualização e gerenciamento de infraestrutura de forma segura e eficiente. Usando uma linguagem de configuração declarativa, conhecida como HashiCorp Configuration Language (HCL), você pode definir e provisionar datacenters completos através de código.

## Conceitos Aprendidos

Neste tutorial, você aprenderá:

1. **Instalação do Terraform CLI**: Como instalar a ferramenta Terraform no sistema.
2. **Instalação do AWS CLI**: Como configurar o AWS Command Line Interface para interagir com os serviços da AWS.
3. **Configuração de Credenciais da AWS**: Como configurar as credenciais de acesso para permitir que o Terraform interaja com a AWS.
4. **Criação de uma Instância EC2**: Como usar o Terraform para definir e provisionar uma instância EC2 na AWS.
5. **Inicialização, Planejamento e Aplicação**: Como inicializar um diretório de trabalho Terraform, planejar a infraestrutura e aplicar a configuração.
6. **Resolução de Erros Comuns**: Como solucionar problemas comuns, como a seleção de uma AMI válida.
7. **Limpeza de Infraestrutura**: Como destruir a infraestrutura criada para evitar custos desnecessários.

## Tecnologias Utilizadas

- **Terraform**: Para definição e provisionamento de infraestrutura como código.
- **AWS CLI**: Para interação com os serviços da AWS via linha de comando.
- **Terminal**: Para execução de comandos.

## Importância do Terraform

A infraestrutura como código (IaC) é um componente essencial da automação de TI, permitindo que você trate sua infraestrutura da mesma forma que trata seu código de software. Isso traz diversos benefícios, como:

- **Reprodutibilidade**: A capacidade de recriar ambientes de maneira consistente.
- **Controle de Versão**: Histórico de mudanças na infraestrutura.
- **Automação**: Redução de tarefas manuais, minimizando erros humanos.
- **Escalabilidade**: Facilita a gestão de grandes volumes de recursos de maneira eficiente.

## Desvantagens do Terraform e IaC

Embora a infraestrutura como código traga muitos benefícios, também existem algumas desvantagens a considerar:

- **Complexidade**: Com infraestrutura como código, você acaba com uma grande base de código que pode ser difícil de gerenciar.
- **Tempo**: Escrever infraestrutura como código leva muito tempo inicialmente, então para projetos pequenos pode ser mais eficiente não utilizá-lo!
- **Bloqueio**: A maioria da infraestrutura como código é específica para o provedor de nuvem. Se você quiser mudar de provedor, também precisará migrar todo o seu IaC!