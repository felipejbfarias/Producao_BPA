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

# Roteiro de Entrevista com Stakeholder
## Módulo de Produção BPA — Sistema NUTES-HC/UFPE

---

| Campo | Informação |
|---|---|
| **Projeto** | Sistema Integrado NUTES-HC/UFPE |
| **Módulo** | Produção BPA (BPA-C e BPA-I) |
| **Stakeholders** | Gestora do NUTES-HC + Analista de Sistemas do HC/UFPE |
| **Duração estimada** | 60 – 90 minutos |

---

## 1. Contexto e Processo Atual

**P1. Como o registro da produção ambulatorial funciona hoje no NUTES-HC? Existe algum sistema ou planilha sendo usado atualmente?**

> 💡 *Identifique se há processo manual, sistema legado (ex.: BPA Magnético do DATASUS), planilhas Excel ou qualquer outro fluxo paralelo.*

Resposta:

---

**P2. Quem são os responsáveis por lançar e validar a produção BPA hoje? Existe uma equipe de faturamento separada dos profissionais de saúde?**

- Há digitadores dedicados ou cada profissional lança seu próprio atendimento?
- Quantas pessoas estão envolvidas nesse processo mensalmente?

Resposta:

---

**P3. ⚠️ Quais são as maiores dores e dificuldades do processo atual de produção BPA? O que gera mais retrabalho ou erro?**

> 💡 *Aqui costumam surgir os requisitos mais importantes. Anote exemplos concretos de problemas que o stakeholder citar.*

Resposta:

---

**P4. Com qual frequência a produção é consolidada e enviada? Existe um calendário fixo (ex.: fechamento até dia X de cada mês)?**

Resposta:

---

## 2. Escopo e Modalidades do BPA

**P5. ⚠️ Quais tipos de procedimentos são registrados no NUTES-HC? O volume é maior em BPA-C (Consolidado) ou BPA-I (Individualizado)?**

- Há procedimentos que usam as duas modalidades (duplo registro)?
- Existe algum procedimento que exige APAC além do BPA?

Resposta:

---

**P6. O sistema precisa cobrir apenas atendimentos do NUTES, ou também de outras unidades do HC que o NUTES apoia?**

- Há mais de um CNES envolvido?

Resposta:

---

**P7. Existe necessidade de registrar procedimentos de múltiplas competências (meses anteriores) de forma retroativa? Qual o limite de competências anteriores aceito pelo gestor?**

Resposta:

---

## 3. Dados e Campos Obrigatórios

**P8. ⚠️ Para o BPA-C, além de CNES, procedimento, CBO e quantidade, o NUTES precisa registrar algum campo complementar (ex.: idade para procedimentos que exigem faixa etária)?**

> 💡 *Verificar SIGTAP: alguns procedimentos têm atributo 012 – exige idade no BPA-C.*

Resposta:

---

**P9. ⚠️ Para o BPA-I, como o NUTES obtém e valida o CNS do paciente? Existe integração com prontuário eletrônico ou base cadastral?**

- Qual é o comportamento esperado quando o CNS não é encontrado ou é inválido?
- O CID é preenchido pelo profissional no momento do atendimento ou em etapa posterior?

Resposta:

---

**P10. Como o CBO dos profissionais é gerenciado? Existe um cadastro interno de profissionais com CNS e CBO já vinculados, ou isso é digitado manualmente a cada registro?**

Resposta:

---

**P11. O sistema precisa suportar o campo de autorização (número de autorização do gestor) em algum procedimento específico?**

Resposta:

---

## 4. Fluxo de Validação e Envio

**P12. ⚠️ Como funciona o fluxo de validação antes do envio? Quem aprova a produção — a gestora, o analista, ou é automático?**

- Existe uma etapa de conferência das críticas do SIA antes do envio definitivo?
- O que acontece quando um procedimento é glosado (recusado pelo SIA)?

Resposta:

---

**P13. ⚠️ O arquivo de envio ao SIA (formato `PA*.xxx`) é gerado diretamente pelo novo sistema ou enviado via BPA Magnético do DATASUS? O sistema deve gerar o arquivo no formato correto para importação no SIA?**

> 💡 *Isso define se o sistema precisa implementar a geração do arquivo magnético BPA ou apenas exportar dados para o BPA Magnético legado.*

Resposta:

---

**P14. Após o envio, o retorno do SIA (arquivo de crítica) é analisado? O sistema precisa importar e exibir esse retorno?**

Resposta:

---

## 5. Integrações e Sistemas Existentes

**P15. ⚠️ Quais sistemas o módulo BPA precisa se integrar? (ex.: prontuário eletrônico, agendamento, SISREG, e-SUS, SIGTAP, CNES online)**

- Essas integrações são via API, banco de dados compartilhado, ou exportação/importação de arquivos?
- A tabela SIGTAP precisa ser atualizada automaticamente dentro do sistema?

Resposta:

---

**P16. O analista que implementou o sistema atual pode compartilhar a estrutura de banco de dados ou documentação técnica existente? Há algo que o novo sistema deve obrigatoriamente herdar ou respeitar?**

Resposta:

---

**P17. Existe alguma restrição tecnológica? (sistema operacional, banco de dados preferido, linguagem de programação, necessidade de funcionar offline)**

Resposta:

---

## 6. Relatórios e Gestão

**P18. Quais relatórios gerenciais a gestora precisa extrair do módulo BPA? (ex.: produção por profissional, por procedimento, por período, comparativo de metas)**

- Os relatórios precisam ser exportados em algum formato específico (Excel, PDF, CSV)?

Resposta:

---

**P19. Há metas de produção definidas? O sistema precisa mostrar indicadores de atingimento de metas ou alertas de subfaturamento?**

Resposta:

---

**P20. Existe necessidade de auditoria — histórico de quem inseriu, alterou ou excluiu registros de produção?**

Resposta:

---

## 7. Usuários, Perfis e Segurança

**P21. ⚠️ Quais perfis de usuário o sistema deve ter? (ex.: profissional de saúde, digitador, auditor, gestor) Quais permissões cada perfil deve ter?**

- Um profissional pode corrigir o registro de outro?
- Somente a gestora pode fazer o fechamento e envio mensal?

Resposta:

---

**P22. O sistema será acessado apenas dentro da rede do HC ou também remotamente (home office, unidades externas)?**

Resposta:

---

## 8. Expectativas, Prioridades e Restrições

**P23. ⚠️ Se você pudesse escolher apenas três funcionalidades que o sistema entregue primeiro, quais seriam?**

> 💡 *Útil para definir o MVP (Mínimo Produto Viável) e priorizar o backlog da equipe.*

Resposta:

---

**P24. Há algum prazo crítico? (ex.: competência que precisa ser fechada, entrega para auditoria, data de apresentação do sistema)**

Resposta:

---

**P25. O que faria o sistema ser considerado um FRACASSO pela equipe do NUTES? Quais erros ou limitações seriam inaceitáveis?**

> 💡 *Perguntas negativas revelam requisitos ocultos e restrições não ditas.*

Resposta:

---

**P26. Há alguma questão que não foi abordada e que você considera importante para o módulo de produção BPA?**
