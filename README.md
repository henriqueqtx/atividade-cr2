# 📦 Sistema de Delivery & Auditoria Customizada

Este é um sistema de gerenciamento de delivery focado na resolução de regras de negócio complexas para aplicação de cupons e descontos escalonados em pedidos e taxas de entrega. Esse projeto foi desenvolvido dentro da disciplina de projetos de sistemas de software e visa aplicar os conhecimentos obtidos.

**O grande diferencial deste projeto?** Nós não usamos apenas bibliotecas prontas. Desenvolvemos, empacotamos e distribuímos nossa própria biblioteca de Logs de Auditoria utilizando o **JitPack**, integrando-a neste projeto como uma dependência Maven remota real.

## 🎯 Destaque Técnico

O projeto demonstra conhecimentos práticos que vão além da sintaxe da linguagem:
- **Gerenciamento de Pacotes:** O repositório consome o [SistemaLogAuditoria](https://github.com/celin1221/SistemaLogAuditoria) diretamente do JitPack via `pom.xml`.
- **Arquitetura Desacoplada:** O código do delivery não conhece a implementação do log, ele apenas consome a interface `ILogger` da nossa biblioteca.
- **Padrões de Projeto (Design Patterns):** A lógica de descontos não usa cadeias de `if/else`. Aplicamos o padrão **Strategy** (`IFormaDescontoTaxaEntrega`) para calcular taxas dinâmicas baseadas em:
  - Bairro da entrega.
  - Fidelidade do Cliente (Ouro, Prata, Bronze).
  - Categorias de Itens (Educação, Alimentação, Lazer).
  - Valor total da compra.

## 💻 Tecnologias Utilizadas
- **Java 21** (Orientação a Objetos avançada)
- **Maven** (Build e controle de dependências)
- **JitPack** (Publicação e distribuição de artefatos)
- **Git** (Versionamento)

## 🚀 Como rodar o projeto

A demonstração principal do sistema acontece na classe `UmCasoDeUsoDePedido.java`. Para testar na sua máquina, o processo é bem simples:

```bash
# 1. Clone este repositório
git clone https://github.com/henriqueqtx/atividade-cr2.git
# 2. Acesse o diretório do projeto
cd atividade-cr2

# 3. Baixe as dependências (o Maven vai puxar nossa Lib do JitPack automaticamente) e compile
mvn clean install

# 4. Execute a demonstração
mvn exec:java 
```
## Integrantes do Grupo
- Marcelo Vieira Gomes
- Henrique Queiroz Teixeira

## Clonar o Projeto

```bash
git clone https://github.com/henriqueqtx/atividade-cr2.git
```

## Dependência do Sistema de Logs

Este projeto utiliza a biblioteca **ILog (Sistema de Log de Auditoria)**.

Documentação e repositório:
https://github.com/celin1221/SistemaLogAuditoria

## Repositório do Projeto

https://github.com/henriqueqtx/atividade-cr2.git
