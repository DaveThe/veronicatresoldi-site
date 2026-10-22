# Proposta: posizione dei pulsanti di prenotazione

> Stato: **da scegliere**.
> Già fatto: in fondo al quiz il pulsante principale ora è **"Prenota su Doctolib"**, con
> "Preferisco scriverti prima" come alternativa (porta al modulo precompilato).

## Situazione attuale

Su ogni pagina ci sono fino a tre inviti all'azione con significati diversi:

| Pulsante | Dove | A cosa serve |
|---|---|---|
| "Richiedi valutazione" | menu in alto | porta al modulo contatti |
| Bussola (quiz) | tondo fisso in basso a destra | "non so da dove iniziare" |
| Doctolib | pillola fissa in basso a destra | "so già cosa mi serve, prenoto" |

Su mobile i due pulsanti fissi occupano l'angolo in basso a destra e coprono parte dei contenuti.

## Opzione A — Barra in basso su mobile, menu su desktop (consigliata)

- **Mobile**: una barra sottile fissa in basso, divisa in due:
  `[ 🧭 Da dove inizio? ]  [ 📅 Prenota ]`.
  Spariscono i due pulsanti tondi, nessun contenuto coperto.
- **Desktop**: nel menu il pulsante "Richiedi valutazione" diventa "Prenota online" (Doctolib).
  Il quiz resta come pulsante tondo in basso a destra, l'unico fisso.
- Il modulo contatti resta raggiungibile da "Contatti e prenotazioni" e dalla fine del quiz.

Pro: ordinato, pattern familiare (app di prenotazione), separa bene le due intenzioni.
Contro: la barra occupa circa 56px fissi su mobile.

## Opzione B — Un solo pulsante fisso che si apre

Un unico pulsante tondo "Come posso aiutarti?" che, toccato, mostra tre scelte:
- "So già cosa mi serve" → Doctolib
- "Non so da dove iniziare" → Bussola (quiz)
- "Preferisco scrivere" → modulo contatti

Pro: un solo elemento fisso, minimo ingombro.
Contro: un tocco in più per prenotare; Doctolib meno visibile.

## Opzione C — Doctolib solo nei contenuti

- Nessun pulsante Doctolib fisso: compare nel menu, nei box finali di ogni pagina servizi, nella pagina
  contatti e alla fine del quiz.
- Resta fisso solo il quiz.

Pro: pagina più pulita.
Contro: chi vuole prenotare subito deve scorrere o aprire il menu.

## Come decidere

Con le statistiche GoatCounter attive (vedi README) i click su ogni pulsante sono già tracciati
(`doctolib-fab`, `doctolib-home`, `doctolib-contatti`, `quiz-doctolib`, `quiz-contatto`,
`modulo-inviato`). Dopo 4–6 settimane si può vedere quale percorso usano davvero le famiglie.
