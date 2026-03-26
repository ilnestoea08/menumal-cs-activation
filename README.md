# Menumal — CS Activation Machine

Dashboard operativa per il Customer Success di Menumal, costruita come progetto di selezione.

**Live:** https://ilnestoea08.github.io/menumal-cs-activation/

**Documentazione strategica (Notion):** https://www.notion.so/32fd9b01f9d48125ba3ac6ad6c8b9457

---

## Cosa fa

Un sistema che accompagna il cliente nei momenti chiave del lifecycle, con azioni suggerite automaticamente in base ai segnali di utilizzo. Tre sezioni operative:

### Nuovi Clienti — Activation Machine
Clienti in fase di onboarding (setup non completato). Mostra il progresso su 5 step sequenziali:

| Step | Descrizione |
|------|-------------|
| 1 | Account creato |
| 2 | Product Tour completato |
| 3 | Setup profilo completato |
| 4 | Prima scansione QR ricevuta |
| 5 | Survey D7 completata |

L'azione suggerita viene calcolata automaticamente combinando giorni dal signup e step raggiunto:
- `D14+ e step ≤ 2` → Chat CSM diretta
- `D7+ e Product Tour non fatto` → Avvia Product Tour
- `D7+ e step < 3` → Banner in-app "Completa il setup" *(es. iscritto da 7 giorni ma ha completato meno di 3 step su 5)*
- `D3+ e step ≥ 3 ma senza survey` → Survey di configurazione

### Clienti Onboardati — Health Dashboard
Clienti con setup completato. Health Score calcolato da 3 segnali: scansioni QR, login frequenza, engagement Intercom. Semaforo verde/giallo/rosso con azioni contestuali per ogni cliente.

KPI in evidenza: health medio, clienti a rischio, priorità CS attive, ticket aperti.

### Menumal Fund — Pipeline
Clienti idonei a bandi e agevolazioni pubbliche. Pipeline a 4 stadi: Da contattare → Proposta inviata → In candidatura → Ottenuto.

**Bandi presidiati:**
- Fondo Turismo 2026 (Invitalia) — fino al 30% a fondo perduto
- Eccellenze Gastronomia (MASAF) — fino al 70%, max 30K€
- Resto al Sud 2.0 (Invitalia) — fino al 100%, max 200K€

Success fee Menumal: 9% sul contributo ottenuto.

---

## Stack

HTML + Tailwind CSS (CDN) + Vanilla JS · nessun build tool · dati da Airtable

## Dati

100 clienti reali dall'Airtable di Menumal, importati come dataset statico (`data.js`).
