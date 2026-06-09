# Estudo de Caso I – Sistemas Operacionais

## Planejamento de Infraestrutura para a DevStore

### 1. Introdução

A DevStore é uma startup de desenvolvimento de sites que enfrenta dificuldades relacionadas à escalabilidade, organização e segurança de sua infraestrutura de Tecnologia da Informação. Atualmente, a empresa utiliza servidores locais sem padronização, o que dificulta o gerenciamento dos sistemas, aumenta custos operacionais e limita o crescimento sustentável da organização.

O objetivo deste planejamento é propor uma arquitetura moderna, segura e escalável, utilizando conceitos de sistemas operacionais, virtualização, containerização e computação em nuvem.

---

## 2. Problemas Identificados

Os principais problemas encontrados na infraestrutura atual são:

* Utilização de servidores locais sem padronização.
* Desenvolvimento realizado diretamente na máquina dos desenvolvedores.
* Ausência de ambientes separados para desenvolvimento, testes e produção.
* Falta de controle de versões e automação de testes.
* Dificuldade de escalabilidade.
* Falta de monitoramento centralizado.
* Riscos de segurança devido à ausência de políticas de acesso e proteção.

---

## 3. Arquitetura Proposta

A nova infraestrutura será composta pelos seguintes elementos:

### Ambiente Local

Os desenvolvedores utilizarão seus computadores apenas para codificação e testes iniciais.

### Ambiente Virtualizado

Será utilizada virtualização para criar máquinas virtuais destinadas a:

* Testes de sistemas operacionais.
* Validação de aplicações.
* Simulação de ambientes de produção.
* Treinamentos e homologações.

#### Configuração das Máquinas Virtuais

| Recurso             | Configuração      |
| ------------------- | ----------------- |
| Sistema Operacional | Ubuntu Server LTS |
| CPU                 | 2 vCPUs           |
| Memória RAM         | 4 GB              |
| Armazenamento       | 40 GB             |
| Rede                | Adaptador Bridge  |

#### Finalidade

Garantir isolamento completo dos ambientes de testes, evitando impactos nos sistemas em produção.

#### Controle de Recursos

* Limitação de CPU e memória.
* Snapshots para recuperação rápida.
* Monitoramento de consumo de recursos.

---

## 4. Utilização de Containerização

Para o desenvolvimento e implantação das aplicações será utilizado o Docker.

### Vantagens

* Padronização dos ambientes.
* Portabilidade.
* Menor consumo de recursos.
* Inicialização rápida.
* Facilidade de escalabilidade.

### Estrutura dos Containers

#### Container Front-end

* Nginx
* React ou Vue.js

#### Container Back-end

* Node.js
* PHP
* Python

#### Container Banco de Dados

* PostgreSQL
* MySQL

#### Container de Testes

* Execução automatizada de testes.

---

## 5. Fluxo de Desenvolvimento

### Etapa 1 – Desenvolvimento

O desenvolvedor realiza alterações em sua máquina local.

### Etapa 2 – Controle de Versão

O código é enviado para um repositório Git.

### Etapa 3 – Integração Contínua

Ferramentas como GitHub Actions executam:

* Testes automatizados.
* Análise de qualidade.
* Verificação de segurança.

### Etapa 4 – Ambiente de Homologação

A aplicação é implantada em containers para validação.

### Etapa 5 – Produção

Após aprovação, a aplicação é publicada no ambiente em nuvem.

---

## 6. Computação em Nuvem

A infraestrutura principal será hospedada na AWS.

### Serviços Utilizados

#### Amazon EC2

Hospedagem dos serviços principais.

#### Amazon RDS

Banco de dados gerenciado.

#### Amazon S3

Armazenamento de arquivos e backups.

#### Elastic Load Balancer

Distribuição de carga entre servidores.

#### CloudWatch

Monitoramento e geração de alertas.

---

## 7. Configuração de Rede

### Estrutura

#### Rede Pública

* Balanceador de carga.
* Gateway de acesso externo.

#### Rede Privada

* Servidores de aplicação.
* Banco de dados.
* Serviços internos.

### Benefícios

* Maior segurança.
* Isolamento dos serviços críticos.
* Melhor desempenho.

---

## 8. Armazenamento

### Estratégia

#### Banco de Dados

Amazon RDS com backups automáticos.

#### Arquivos

Amazon S3 com versionamento habilitado.

#### Backups

* Backup diário.
* Retenção de 30 dias.
* Replicação geográfica.

---

## 9. Segurança

### Controle de Acesso

* Usuários individuais.
* Autenticação multifator (MFA).
* Política de senhas fortes.

### Permissões

Aplicação do princípio do menor privilégio:

* Desenvolvedores.
* Administradores.
* Equipe de suporte.

### Firewall

Configuração de regras para:

* HTTP (80)
* HTTPS (443)
* SSH (22) apenas para IPs autorizados

### Proteção Adicional

* Atualizações automáticas.
* Criptografia de dados.
* Logs de auditoria.

---

## 10. Monitoramento

### Ferramentas

#### CloudWatch

Monitoramento da infraestrutura em nuvem.

#### Prometheus

Coleta de métricas.

#### Grafana

Visualização de dashboards.

### Indicadores Monitorados

* Uso de CPU.
* Consumo de memória.
* Espaço em disco.
* Latência.
* Disponibilidade dos serviços.

### Benefícios

* Identificação rápida de falhas.
* Redução de indisponibilidade.
* Melhor planejamento de capacidade.

---

## 11. Papel dos Sistemas Operacionais

### Ambiente Local

Windows ou Linux para desenvolvimento.

### Ambiente Virtualizado

Ubuntu Server para testes e homologação.

### Containers

Linux como sistema base para execução dos containers Docker.

### Ambiente em Nuvem

Ubuntu Server LTS hospedado na AWS devido à sua estabilidade, segurança e ampla compatibilidade com aplicações web.

---

## 12. Justificativa das Escolhas Técnicas

| Critério        | Justificativa                                                    |
| --------------- | ---------------------------------------------------------------- |
| Desempenho      | Containers consomem menos recursos que máquinas virtuais.        |
| Escalabilidade  | AWS permite crescimento sob demanda.                             |
| Segurança       | Controle de acesso, firewall e monitoramento contínuo.           |
| Custo           | Redução da necessidade de servidores físicos.                    |
| Compatibilidade | Linux possui ampla compatibilidade com tecnologias web modernas. |
| Manutenção      | Automação reduz esforço operacional.                             |

---

## 13. Estratégia de Implantação

### Fase 1

Implementação do Git e do controle de versão.

### Fase 2

Criação dos ambientes virtualizados.

### Fase 3

Migração das aplicações para Docker.

### Fase 4

Implantação da infraestrutura AWS.

### Fase 5

Configuração de monitoramento e segurança.

---

## 14. Estratégia de Expansão

Conforme o crescimento da empresa, será possível:

* Adicionar novas instâncias EC2.
* Utilizar Kubernetes para orquestração dos containers.
* Implementar balanceamento avançado de carga.
* Adicionar novos bancos de dados.
* Expandir armazenamento automaticamente.
