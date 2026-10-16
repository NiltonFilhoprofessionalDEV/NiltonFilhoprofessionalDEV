<div align="center">

# Nilton Cabral

**Desenvolvedor Full Stack** · Análise e Desenvolvimento de Sistemas

Aplicações web com TypeScript & Supabase · APIs com Java
Transformando problemas reais da operação em software sob medida

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)

</div>

---

## Sobre mim

Desenvolvedor full stack formado em **Análise e Desenvolvimento de Sistemas (ADS)**. Construo software que precisa funcionar de verdade — do modelo de dados à interface, passando pela infraestrutura.

Trabalho principalmente com **TypeScript** e **Supabase** na web e com **Java** no backend, sempre buscando soluções enxutas e fáceis de manter. Ferramentas de IA como **OpenCode, Cursor e ChatGPT** fazem parte do meu fluxo diário de desenvolvimento — é assim que vou de ideia a produto em produção mais rápido.

---

## Stack

| Área | Tecnologias |
| --- | --- |
| **Frontend** | React, TypeScript, Next.js, Tailwind CSS |
| **Backend & Dados** | Java, Spring Boot, PostgreSQL, Supabase |
| **Infra & Deploy** | Docker, GitHub Actions, Vercel |

---

## Projetos

> Produtos em produção — usados por clientes reais e na própria operação.

### Indicadores MedMais
*Indicadores operacionais de várias bases, com segurança por perfil.*

Plataforma de gestão de indicadores operacionais usada pela **MedMais**, empresa multinacional de grande porte. As equipes lançam e conferem indicadores por base, acompanham painéis analíticos, gerenciam usuários e colaboradores e exportam relatórios. Cada unidade enxerga apenas os próprios dados graças ao isolamento por linha (*Row Level Security*) no PostgreSQL, e o acesso é controlado por perfil.

`React` · `TypeScript` · `Supabase` · `Vite` · `Recharts`

### New Jiu Jitsu
*O sistema completo de uma academia de jiu-jitsu.*

Do cadastro de alunos e famílias ao financeiro. Grade de aulas e calendário, presença com check-in manual e por QR code, controle de faixas e graduações e planos de mensalidade — tudo sobre uma base multiacademia. Backend em **Java 21 + Spring Boot** com autenticação por JWT e refresh token rotativo; frontend em **React**.

`Java 21` · `Spring Boot` · `PostgreSQL` · `React` · `Docker` · [código](https://github.com/NiltonFilhoprofessionalDEV/New-Jiujitsu)

### FireCheck
*Inspeção de extintores, do escritório ao campo.*

Sistema de gestão e inspeção de extintores usado por equipes de campo: importação de planilhas (Excel/CSV), mapeamento dos equipamentos sobre a planta do local e conferência direto do celular (PWA). Traz níveis de acesso corporativo, base, liderança e operacional — além de um perfil cliente somente-leitura — com os dados de cada base isolados.

`Next.js` · `TypeScript` · `Supabase` · `PWA`

### Venda Fácil
*Vendas, entregas e rotas na palma da mão.*

App web mobile-first que registra vendas com produtos e clientes, organiza as entregas do dia e otimiza automaticamente a rota (via OSRM) para reduzir o deslocamento. Roda direto do navegador do celular como PWA.

`React` · `TypeScript` · `Supabase` · `PWA`

### Backup Supabase
*Backups automáticos que se provam restauráveis.*

Rotina de backup do banco Supabase que roda inteiramente no **GitHub Actions**, sem servidor para manter. Todos os dias — e também sob demanda — o workflow conecta no PostgreSQL do projeto, gera o dump dos schemas `public` e `auth` em três formatos (o `database.dump` em formato custom, pronto para restauração, além de `schema.sql` e `data.sql` em texto), valida o arquivo com `pg_restore --list` e compacta tudo em um `.zip`. O pacote vai para o Google Drive via `rclone`, organizado por ano/mês, com um `latest.zip` apontando sempre para o backup mais recente; arquivos com mais de 30 dias são apagados automaticamente.

Um segundo workflow — um teste de restauração semanal — baixa o `latest.zip`, sobe um PostgreSQL 17 temporário, recria as roles, schemas e extensões padrão do Supabase (`anon`, `authenticated`, `service_role`, `uuid-ossp`, `pgcrypto`) e restaura o dump com `--exit-on-error`, conferindo que os schemas e as tabelas voltaram. Ou seja, o backup não é apenas gerado: é provado restaurável de tempos em tempos. Sucesso e falha disparam notificação no Telegram com tamanho, duração e link da execução, e o log fica salvo como artefato.

`GitHub Actions` · `Bash` · `PostgreSQL` · `pg_dump` · `rclone` · `Docker`

> Os projetos de uso interno têm repositórios privados — acesso sob autorização.

---

## Contato

Fico à disposição para conversar sobre projetos, oportunidades e ideias.

- **GitHub:** [NiltonFilhoprofessionalDEV](https://github.com/NiltonFilhoprofessionalDEV)
- **E-mail:** cabralsussa@gmail.com
