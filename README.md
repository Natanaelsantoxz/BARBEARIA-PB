# Barbearia P.B — Agendamento online

Site estático (HTML/CSS/JS) + banco de dados Supabase (PostgreSQL), hospedável de graça no GitHub Pages.

- `index.html` — área do **cliente**: escolhe serviço, dia e horário e agenda.
- `admin.html` — área do **profissional**: login único, agenda do dia, concluir/cancelar.
- `config.js` — chaves do Supabase, horário de funcionamento e tabela de preços.
- `supabase.sql` — cria a tabela e as regras de segurança.

## Passo a passo
1. Crie um projeto grátis em supabase.com.
2. **Authentication > Providers > Email**: desative "Allow new users to sign up" (assim só existe 1 login).
3. **Authentication > Users > Add user**: crie o e-mail e a senha do profissional.
4. Abra `supabase.sql`, troque `SEU_EMAIL_AQUI` pelo mesmo e-mail (2 lugares) e rode no **SQL Editor**.
5. **Project Settings > API**: copie a *Project URL* e a chave *anon public* para o `config.js`.
6. Suba esta pasta em um repositório no GitHub, depois **Settings > Pages > Deploy from branch (main)**.

A chave `anon` é pública por natureza; quem protege os dados são as regras (RLS) do `supabase.sql`.
Nunca coloque a chave `service_role` no site.
