# claude-sessioni

Regole di permesso per le sessioni Claude Code in cloud del gruppo (decisioni n. 165 e 165-a, pendenza 822 di ERU).

Chi apre una sessione Claude Code in cloud con questo repository selezionato parte come dal PC di un collaboratore
(`CLAUDE.md` fisso, tutto letto da ERU) e non riceve piu' la richiesta di consenso per i connettori elencati in
`.claude/settings.json`. Le protezioni dei connettori restano: finestra di scrittura di
ERU, tocco del custode per la produzione, approvazione delle mail di Claude.

## Il repository e' PUBBLICO: niente segreti, mai

Qui non vanno, in nessuna forma, nemmeno per un minuto:
- password, token, chiavi API, chiavi SSH o certificati, codici di accesso;
- indirizzi interni (Tailscale, IP di rete), nomi di macchine, percorsi del NAS;
- dati delle aziende servite (clienti, importi, nomi di persone), codice delle aziende.

Un segreto spinto qui va considerato bruciato: si revoca subito, anche se il commit si toglie.

## Cosa puo' contenere

Solo questi file (il controllo automatico rifiuta tutto il resto):
- `README.md`
- `CLAUDE.md`: copia esatta del modello `intermedio/pc/CLAUDE_COLLABORATORE.md` delle istruzioni di ERU, uguale per
  tutti e mai aggiornato (Nicola, 27/11/2026). Fa leggere a ogni sessione il ponte dal connettore di ERU: le regole
  stanno li', non qui. Si cambia solo se cambia il modello in ERU.
- `.claude/settings.json`, con la sola chiave `permissions.allow` e voci di connettori `mcp__<nome>` o
  `mcp__<nome>__<strumento>`
- `.github/workflows/controllo.yml` e `.github/CODEOWNERS`

## Come si cambia

Da un ramo, con una richiesta di modifica (pull request): `main` accetta solo modifiche che passano il controllo
«controllo». Le modifiche a `.github/` le approva il proprietario del codice (Nicola).
