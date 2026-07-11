# Revisão Completa de Segurança da Informação — Concurso Dataprev (Desenvolvimento de Software)

Material de estudo focado em: Segurança da Informação, OWASP, LGPD, Criptografia, Vulnerabilidades, Gestão de Riscos e Principais Ameaças Cibernéticas.

## Sumário

- Fundamentos de Segurança da Informação
- Princípios da Segurança
- Gestão de Riscos
- Criptografia
- Certificados Digitais
- Autenticação e Autorização
- OWASP Top 10
- Principais Ameaças Cibernéticas
- Segurança em APIs
- LGPD
- Segurança em DevOps (DevSecOps)
- Boas Práticas de Segurança
- Exercícios de Fixação
- Referências

---

# 1. Fundamentos de Segurança da Informação

## O que é Segurança da Informação?

Conjunto de práticas destinadas a proteger informações contra acessos não autorizados, alterações indevidas ou indisponibilidade.

### Objetivos

- Proteger dados
- Reduzir riscos
- Garantir continuidade do negócio
- Atender exigências legais

---

# 2. Princípios da Segurança

## Tríade CIA

### Confidencialidade

Garante acesso apenas para usuários autorizados.

### Integridade

Assegura que os dados não sejam alterados indevidamente.

### Disponibilidade

Garante acesso aos sistemas quando necessário.

## Outros Princípios

- Autenticidade
- Não Repúdio
- Rastreabilidade
- Auditoria

---

# 3. Gestão de Riscos

## Conceitos

### Ativo

Bem que possui valor para a organização.

### Ameaça

Evento capaz de causar dano.

### Vulnerabilidade

Fraqueza explorável por uma ameaça.

### Risco

Probabilidade de exploração de uma vulnerabilidade.

### Mitigação

Ações para reduzir impactos.

---

# 4. Criptografia

## Criptografia Simétrica

Utiliza a mesma chave para criptografar e descriptografar.

### Exemplos

- AES
- DES
- 3DES

### Vantagem

Alta velocidade.

### Desvantagem

Distribuição da chave.

---

## Criptografia Assimétrica

Utiliza par de chaves.

- Chave Pública
- Chave Privada

### Exemplos

- RSA
- ECC

### Aplicações

- Assinatura digital
- Certificados digitais
- HTTPS

---

## Funções Hash

Transformam dados em valor único.

### Exemplos

- SHA-256
- SHA-512

### Características

- Irreversíveis
- Integridade dos dados

---

# 5. Certificados Digitais

## Conceito

Documento eletrônico utilizado para validar identidades digitais.

## Aplicações

- HTTPS
- Assinaturas digitais
- Autenticação

## Infraestrutura PKI

- Autoridade Certificadora (CA)
- Certificados
- Chaves Públicas
- Chaves Privadas

---

# 6. Autenticação e Autorização

## Autenticação

Verifica quem é o usuário.

Exemplos:

- Senha
- Biometria
- Token

## Autorização

Define o que o usuário pode fazer.

## MFA (Multi-Factor Authentication)

Combina múltiplos fatores.

- Senha
- Aplicativo autenticador
- Biometria

---

# 7. OWASP Top 10

## O que é OWASP?

Open Worldwide Application Security Project.

Organização focada em segurança de aplicações.

### Principais Vulnerabilidades

#### Broken Access Control

Falhas no controle de acesso.

#### Cryptographic Failures

Uso inadequado de criptografia.

#### Injection

Ex.: SQL Injection.

#### Insecure Design

Problemas de arquitetura.

#### Security Misconfiguration

Configurações inseguras.

#### Vulnerable Components

Dependências vulneráveis.

#### Identification and Authentication Failures

Falhas de autenticação.

#### Software and Data Integrity Failures

Comprometimento da integridade.

#### Security Logging and Monitoring Failures

Deficiências de auditoria.

#### SSRF (Server-Side Request Forgery)

Requisições indevidas executadas pelo servidor.

---

# 8. Principais Ameaças Cibernéticas

## Malware

Software malicioso.

### Tipos

- Vírus
- Worm
- Trojan
- Spyware
- Ransomware

## Phishing

Tentativa de obter informações por engenharia social.

## DoS e DDoS

Ataques de negação de serviço.

## Engenharia Social

Manipulação de pessoas para obter acesso indevido.

## Ataque Man-in-the-Middle

Interceptação da comunicação entre duas partes.

---

# 9. Segurança em APIs

## Boas Práticas

- HTTPS obrigatório
- OAuth2
- JWT
- Rate Limiting
- Logs de auditoria

## Vulnerabilidades Comuns

- Exposição excessiva de dados
- Falta de autenticação
- Falta de autorização
- Injeção de comandos

---

# 10. LGPD

## O que é LGPD?

Lei Geral de Proteção de Dados (Lei nº 13.709/2018).

Regulamenta tratamento de dados pessoais no Brasil.

## Conceitos Principais

### Dado Pessoal

Informação relacionada a pessoa identificada ou identificável.

### Dado Sensível

- Saúde
- Religião
- Biometria
- Origem racial

### Titular

Pessoa a quem os dados pertencem.

### Controlador

Responsável pelas decisões sobre tratamento dos dados.

### Operador

Executa tratamento em nome do controlador.

## Princípios da LGPD

- Finalidade
- Necessidade
- Transparência
- Segurança
- Responsabilização

---

# 11. Segurança em DevOps (DevSecOps)

## Conceito

Integra práticas de segurança ao ciclo de desenvolvimento.

## Práticas

- Análise estática (SAST)
- Análise dinâmica (DAST)
- Scan de dependências
- Scan de containers
- Gestão de segredos

---

# 12. Boas Práticas de Segurança

- Utilizar MFA
- Aplicar princípio do menor privilégio
- Atualizar softwares regularmente
- Criptografar dados sensíveis
- Utilizar HTTPS
- Realizar backups periódicos
- Monitorar logs
- Executar testes de segurança

---

# 13. Exercícios de Fixação

1. Explique a tríade CIA.
2. Diferencie autenticação e autorização.
3. Qual diferença entre criptografia simétrica e assimétrica?
4. O que é hash?
5. O que é SQL Injection?
6. O que é phishing?
7. Cite princípios da LGPD.
8. O que é MFA?
9. O que representa a OWASP?
10. Explique risco, ameaça e vulnerabilidade.

---

# 14. Referências

- OWASP Top 10
- LGPD (Lei 13.709/2018)
- NIST Cybersecurity Framework
- ISO 27001
- ISO 27002
- OWASP API Security Top 10
- CIS Controls

## Dicas para Prova

✅ Tríade CIA

✅ Criptografia Simétrica e Assimétrica

✅ Hash

✅ Certificados Digitais

✅ OWASP Top 10

✅ SQL Injection

✅ XSS

✅ Phishing

✅ LGPD

✅ OAuth2 e JWT

✅ DevSecOps
