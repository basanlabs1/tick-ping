# Pinger do agente (GitHub Actions)

Chama `/cron/tick` do agente a cada 5 minutos (follow-ups, avisos que falharam, limpeza de dados, autoaprendizado).
O repositório guarda SÓ este workflow; a URL e o segredo ficam em Actions secrets (`TICK_URL`, `CRON_SECRET`).
Repositório público = minutos de Actions ilimitados. O GitHub desativa agendamentos após 60 dias sem atividade no repositório:
se isso acontecer, reative em Actions > tick > Enable workflow.

Instalação (uma vez):
    gh repo create tick-ping --public --source . --push
    gh secret set TICK_URL --body "https://agente-vendedor-havana.vercel.app/cron/tick"
    gh secret set CRON_SECRET   # cole o valor de CRON_SECRET do .env

Atualizado em 2026-11-15: secrets TICK_URL e CRON_SECRET configurados.
