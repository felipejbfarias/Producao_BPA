# Producao_BPA
# Repositório da atividade da disciplina Desenvolvimento de Software - CIN/UFPE

---

## Produção e BPA

O módulo de Produção e BPA faz parte do projeto Clínica Digital UFPE e tem como objetivo organizar as informações relacionadas aos atendimentos e procedimentos realizados nas clínicas-escola.

### Produção

A produção representa os atendimentos e procedimentos realizados pelos profissionais nas clínicas.

O módulo deve permitir que essas informações sejam registradas e organizadas, relacionando cada produção ao atendimento correspondente. Esses registros poderão ser consolidados por período, profissional, clínica e procedimento.

Além disso, o módulo deve ajudar na identificação de pendências e inconsistências nos registros, facilitando a conferência das informações antes de sua utilização.

### BPA

BPA significa **Boletim de Produção Ambulatorial**.

No contexto do projeto, o BPA está relacionado à organização e preparação das informações da produção ambulatorial. Após os atendimentos e procedimentos serem registrados, os dados precisam ser conferidos e consolidados para que possam ser utilizados na preparação do BPA.

O módulo busca facilitar esse processo, permitindo revisar pendências, identificar inconsistências e gerar uma visão organizada da produção para conferência.

### Objetivo do módulo

A principal questão que orienta o desenvolvimento do módulo é:

Como transformar registros assistenciais em informação de produção organizada e conferível para o BPA, reduzindo retrabalho?

# Workflow do BPA numa Clínica do SUS
 
O **BPA (Boletim de Produção Ambulatorial)** é um dos instrumentos de registro do **SIA/SUS** (Sistema de Informações Ambulatoriais) usado para informar a produção de serviços ambulatoriais prestados por unidades de saúde, permitindo o repasse de recursos financeiros do Ministério da Saúde aos municípios/estabelecimentos.
 
## 1. Atendimento e registro do procedimento
 
Quando o paciente é atendido (consulta, exame, curativo, procedimento, etc.), o profissional de saúde registra o atendimento — seja em prontuário físico, seja diretamente no sistema (e-SUS AB, sistemas próprios da secretaria de saúde, etc.). Esse registro precisa conter:
 
- Código do procedimento realizado, conforme a tabela **SIGTAP** (Sistema de Gerenciamento da Tabela de Procedimentos, Medicamentos e OPM do SUS)
- CID (quando aplicável)
- CNS (Cartão Nacional de Saúde) do paciente
- CBO (Código Brasileiro de Ocupação) do profissional executante
- Data do atendimento
## 2. Consolidação da produção
 
No fim do dia (ou em intervalos definidos pela gestão), a equipe administrativa ou o setor de faturamento consolida os atendimentos registrados. Isso pode ser feito de duas formas, dependendo do tipo de BPA:
 
- **BPA Individualizado (BPA-I)**: identifica o paciente individualmente — obrigatório para determinados procedimentos (alta complexidade, procedimentos que exigem identificação nominal, cotas, etc.)
- **BPA Consolidado (BPA-C)**: agrupa procedimentos por código, sem identificar o paciente — usado para procedimentos simples e de grande volume (ex.: curativos, aferição de pressão)
## 3. Digitação/exportação no sistema
 
A produção é lançada em um sistema de captação, geralmente o **SISAB/e-SUS AB** (para atenção básica) ou sistemas próprios de faturamento ambulatorial integrados ao BPA Magnético/SIA. Muitas clínicas usam softwares de gestão que já geram o arquivo no layout exigido pelo Ministério da Saúde.
 
## 4. Validação e crítica
 
Antes do envio, os dados passam por uma checagem de consistência — verificação de CNS válido, compatibilidade entre CID e procedimento, CBO compatível com o procedimento, cotas físicas e orçamentárias do estabelecimento, entre outras regras do **SIGTAP**. Erros aqui geram "glosas" (rejeição de itens da produção).
 
## 5. Envio à Secretaria Municipal/Estadual de Saúde
 
O arquivo consolidado (BPA magnético) é enviado à Secretaria Municipal de Saúde, geralmente dentro do calendário de competência mensal estabelecido pelo DATASUS. A secretaria municipal, por sua vez, consolida os dados de todas as unidades e os transmite ao **DATASUS/Ministério da Saúde** através do sistema SIA/SUS.
 
## 6. Processamento nacional e repasse financeiro
 
O Ministério da Saúde processa os dados nacionalmente, calcula o valor correspondente à produção (conforme valores da tabela SIGTAP) e realiza o repasse do Piso da Atenção Básica Variável/Fixa ou de outros blocos de financiamento, conforme a modalidade vigente (hoje majoritariamente vinculada ao Previne Brasil, para atenção básica, e demais tabelas para média/alta complexidade).
 
## 7. Retroalimentação e correção de glosas
 
Caso haja inconsistências (BPA "glosado"), a unidade recebe um relatório de erros e pode corrigir e reenviar dentro do prazo da competência seguinte.
 
---
 
## Resumo do fluxo
 
Atendimento → Registro (SIGTAP/CID/CNS/CBO) → Consolidação (BPA-I ou BPA-C) → Digitação no sistema → Validação/crítica → Envio à Secretaria de Saúde → Consolidação municipal/estadual → Envio ao DATASUS → Processamento e repasse financeiro
