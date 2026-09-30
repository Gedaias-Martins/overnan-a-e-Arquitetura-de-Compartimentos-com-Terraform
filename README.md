# OCI IAM: Governança e Arquitetura de Compartimentos

Este repositório contém um projeto prático desenvolvido durante os meus estudos para a certificação **Oracle Cloud Infrastructure (OCI) Foundations / Architect**. O objetivo é demonstrar a automação da estrutura de **Compartimentos**, que serve como base para o isolamento de recursos, políticas de segurança granulares e gestão de custos eficientes na nuvem Oracle.

## 🚀 Visão Geral do Projeto

Os compartimentos na OCI não são apenas pastas organizacionais, mas barreiras lógicas fundamentais para governança. Este projeto automatiza a criação de uma topologia padrão de mercado dividida por ambientes.

### Arquitetura de Compartimentos Criada:
``` text
[Compartimento Raiz (Tenancy)]
       └── oci-governance-root (Compartimento Pai do Projeto)
             ├── oci-ambient-dev (Desenvolvimento)
             ├── oci-ambient-hml (Homologação)
             └── oci-ambient-prd (Produção)
```

## 🛠️ Tecnologias Utilizadas
* **Oracle Cloud Infrastructure (OCI)** - Provedor de nuvem.
* **Terraform (IaC)** - Ferramenta para provisionamento automático da infraestrutura.

## 📁 Estrutura do Código

* `main.tf`: Define o provedor OCI e a criação dos compartimentos hierárquicos utilizando o recurso `oci_identity_compartment`.
* `variables.tf`: Centraliza as variáveis como o `tenancy_ocid` para manter o código seguro e reutilizável.
* `outputs.tf`: Exporta os OCIDs (Oracle Cloud Identifiers) dos novos compartimentos criados para auditoria.

## 🔧 Como Executar Este Projeto

1. **Pré-requisitos:** Ter o Terraform instalado e a CLI da OCI configurada com as suas credenciais.
2. **Clonar o repositório:**
   ```bash
   git clone https://github.com
   cd oci-iam-compartments
   ```
3. **Inicializar o Terraform:**
   ```bash
   terraform init
   ```
4. **Planejar e Validar:**
   ```bash
   terraform plan -var="tenancy_ocid=seu_ocid_aqui"
   ```
5. **Aplicar a infraestrutura:**
   ```bash
   terraform apply -var="tenancy_ocid=seu_ocid_aqui"
   ```

---
💡 *Estudo baseado no curso oficial de Fundamentos da Infraestrutura de Nuvem Oracle (OCI).*
