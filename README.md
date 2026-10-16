# Nilton Cabral

Desenvolvedor full stack formado em **Análise e Desenvolvimento de Sistemas (ADS)**. Construo aplicações web com **TypeScript + Supabase** e APIs em **Java**, com foco em resolver problemas reais da operação. Uso ferramentas de IA — **OpenCode, Cursor e ChatGPT** — como parte do meu fluxo de desenvolvimento.

## Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)

Também trabalho com Spring Boot, PostgreSQL, Tailwind CSS e Docker.

## Projetos

Projetos em produção — em uso por clientes reais e na operação.

### Indicadores MedMais

Plataforma de gestão de indicadores operacionais usada pela **MedMais**, empresa multinacional de grande porte. Permite lançar e conferir indicadores por base e equipe, acompanhar painéis analíticos, gerir usuários e colaboradores e exportar relatórios. O acesso é controlado por perfil e os dados de cada base ficam isolados no banco (Row Level Security no PostgreSQL, via Supabase) — cada unidade enxerga apenas o que é seu.

`React` · `TypeScript` · `Supabase` · `Vite` · `Recharts`

### New Jiu Jitsu

Sistema completo de gestão para academias de jiu-jitsu, com suporte a múltiplas academias. Cobre o fluxo inteiro do estúdio: cadastro de alunos e famílias, grade de aulas e calendário, presença com check-in manual e por QR code, controle de faixas e graduações, planos de mensalidade e módulo financeiro. Backend em Java 21 + Spring Boot com autenticação por JWT e refresh token rotativo; frontend em React.

`Java 21` · `Spring Boot` · `PostgreSQL` · `React` · `Docker` · [código](https://github.com/NiltonFilhoprofessionalDEV/New-Jiujitsu)

### FireCheck

Sistema de gestão e inspeção de extintores usado por equipes de campo. Faz importação de planilhas (Excel/CSV), mapeamento dos equipamentos sobre a planta do local e conferência em campo pelo celular (PWA). Tem níveis de acesso distintos — corporativo, base, liderança e operacional — além de um perfil cliente somente-leitura para consulta e download de relatórios, com os dados de cada base isolados.

`Next.js` · `TypeScript` · `Supabase` · `PWA`

### Venda Fácil

App web mobile-first para registrar vendas com produtos e clientes, organizar as entregas do dia e otimizar automaticamente a rota (via OSRM), reduzindo o deslocamento. Roda direto do navegador do celular como PWA.

`React` · `TypeScript` · `Supabase` · `PWA`

### Backup Supabase

Rotina de backup automático do banco de dados do Supabase que roda inteiramente no **GitHub Actions**, sem servidor próprio para manter. Todos os dias — e também sob demanda — o workflow conecta no PostgreSQL do projeto, gera o dump dos schemas `public` e `auth` em três formatos (o `database.dump` em formato custom, pronto para restauração, além de `schema.sql` e `data.sql` em texto), valida o arquivo com `pg_restore --list` e compacta tudo em um `.zip`. O pacote vai para o Google Drive via `rclone`, organizado por ano/mês, com um `latest.zip` apontando sempre para o backup mais recente; arquivos com mais de 30 dias são apagados automaticamente.

Um segundo workflow — um teste de restauração semanal — baixa o `latest.zip`, sobe um PostgreSQL 17 temporário, recria as roles, schemas e extensões padrão do Supabase (`anon`, `authenticated`, `service_role`, `uuid-ossp`, `pgcrypto`) e restaura o dump com `--exit-on-error`, conferindo que os schemas e as tabelas voltaram. Ou seja, o backup não é só gerado: é provado restaurável de tempos em tempos. Sucesso e falha disparam notificação no Telegram com tamanho, duração e link da execução, e o log fica salvo como artefato.

`GitHub Actions` · `Bash` · `PostgreSQL` · `pg_dump` · `rclone` · `Docker`

> Os projetos de uso interno têm repositórios privados — acesso sob autorização.

## Contato

- GitHub: [NiltonFilhoprofessionalDEV](https://github.com/NiltonFilhoprofessionalDEV)
- E-mail: cabralsussa@gmail.com
