# 📦 Sistema de Delivery & Auditoria Customizada

Este é um sistema de gerenciamento de delivery focado na resolução de regras de negócio complexas para aplicação de cupons e descontos escalonados em pedidos e taxas de entrega. Projeto desenvolvido para a disciplina de Projetos de Sistemas de Software (UFES).

**O grande diferencial deste projeto?** Não usamos apenas bibliotecas prontas. Desenvolvemos, empacotamos e distribuímos nossa própria biblioteca de Logs de Auditoria utilizando o **JitPack**, integrando-a neste projeto como uma dependência Maven remota real.

### 🛠️ Tecnologias Utilizadas
- **Linguagem:** Java 21 
- **Design:** Padrões de Projeto (GoF), Orientação a Objetos Avançada
- **Ferramentas:** Maven (Build e Dependências), JitPack (Distribuição de Artefatos)

---

## 🎯 Destaque Técnico

O projeto demonstra conhecimentos práticos que vão além da sintaxe da linguagem:
- **Gerenciamento de Pacotes:** O repositório consome o sistema [ILog (Sistema de Log de Auditoria)](https://github.com/celin1221/SistemaLogAuditoria) diretamente do JitPack via `pom.xml`.
- **Arquitetura Desacoplada:** O código do delivery não conhece a implementação do log, ele apenas consome a interface `ILogger` da nossa biblioteca.
- **Padrões de Projeto (Design Patterns):** A lógica de descontos não usa cadeias de `if/else`. Aplicamos o padrão **Strategy** (`IFormaDescontoTaxaEntrega`) para calcular taxas dinâmicas baseadas em:
  - Bairro da entrega.
  - Fidelidade do Cliente (Ouro, Prata, Bronze).
  - Categorias de Itens (Educação, Alimentação, Lazer).
  - Valor total da compra.

## 💻 Demonstração

<img width="1170" height="639" alt="auditoria" src="https://github.com/user-attachments/assets/c9e1da8d-10d9-4af5-a23b-0d3b618d62ac" />


## 🚀 Como rodar o projeto na sua máquina

A demonstração principal do sistema acontece na classe `UmCasoDeUsoDePedido.java`. Para testar:

```bash
# 1. Clone este repositório
git clone https://github.com/henriqueqtx/sistema-delivery-auditoria.git

# 2. Acesse o diretório do projeto
cd sistema-delivery-auditoria

# 3. Baixe as dependências (o Maven puxa nossa Lib do JitPack automaticamente) e compile
mvn clean install

# 4. Execute a demonstração
mvn exec:java
