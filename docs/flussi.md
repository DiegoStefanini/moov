# = Flussi Utente di MOOV

## 1� Flusso Utente FREE (Monitoraggio Personale)

### Onboarding
1. Download app e apertura
2. Setup profilo base: registrazione, nome
3. Tutorial rapido delle funzionalit�

### Creazione Routine
1. Tab "Routine" � Pulsante "Nuova Routine", l'insieme delle routine è chiamato "scheda"
2. Inserimento nome routine (es. "Push Day", "Gambe A")
3. Aggiunta esercizi:
   - Pulsante "Aggiungi esercizio"
   - Crea esercizio custom: nome, note, opzione esercizio monolaterale o meno
   - Definisce serie e ripetizioni target (es. 4x8-10)
4. Ordina esercizi con drag & drop
5. Salva routine

### Avvio Allenamento
1. Home � "Inizia allenamento"
2. Scelta routine esistente o "Allenamento libero"
3. Per ogni esercizio:
   - Visualizza serie da completare
   - **Vede pesi usati negli ultimi allenamenti** (es. "Ultima volta: 80kg x 8")
   - Inserisce peso e ripetizioni per ogni serie
   - Checkbox per confermare serie completata
   - Timer di riposo automatico (personalizzabile)
4. Note rapide durante l'allenamento
5. Possibilità di caricare video della serie effettuata
6. Fine allenamento � Riepilogo e salvataggio

### Visualizzazione Progressi
1. Tab "Progressi"
2. Selezione periodo (settimana, mese, anno)
3. Grafici disponibili:
   - Progressione peso per singolo esercizio
   - Frequenza allenamenti
   - Personal record (PR)
4. Filtro per esercizio specifico
5. Esportazione dati (PDF/CSV)
6. possibilità di registrare il proprio peso corporeo e carica immagini di check del fisico
### Storico Allenamenti
1. Tab "Storico"
2. Lista allenamenti in ordine cronologico
3. Tap su allenamento � Dettaglio completo:
   - Data e durata
   - Esercizi, serie, ripetizioni, carichi
   - Note dell'allenamento
4. Possibilit� di ripetere lo stesso allenamento

---

## 2� Flusso COACH PRO

### Upgrade a Coach
1. Utente FREE � Profilo � "Diventa Coach"
2. Scelta piano abbonamento (mensile/annuale)
3. Pagamento (Stripe/PayPal)
4. Attivazione funzionalit� Coach

### Gestione Clienti

#### Aggiungere un cliente
1. Tab "Clienti" � "Aggiungi Cliente"
2. Invito via email/link
3. Cliente accetta invito e se non lo ha, crea account
4. Cliente compila modulo che il coach crea di default da far apparire a tutti i nuovi clienti, con domande tipo "esercizi che non ti piacciono" 
5. Cliente appare nella lista del coach

#### Dashboard Clienti
1. Tab "Clienti"
2. Lista clienti con:
   - Nome, foto profilo
   - Ultimo allenamento completato
   - Indicatori di attivit� (verde/giallo/rosso)
3. Tap su cliente � Profilo dettagliato:
   - Storico allenamenti completo
   - Grafici progressi
   - Note del coach
   - Routine assegnate
   - Vedere ultimi check di peso e foto allegate
   - chat diretta con il cliente
   - Macronutrienti assegnati
   - Storico macronutrienti 
   - Grafico macronutrienti e grafico peso comparabili 
4. Possibilità di modificare, archiviare, aggiungere routine 
5. Tap su un allenamento: 
   - Vedere carichi e ripetizioni usati, vedere video se allegati

### Creazione Routine per Clienti
1. Profilo cliente � "Assegna Routine"
2. Scelta:
   - Crea nuova routine specifica per il cliente
3. Assegnazione routine con note/istruzioni
4. Cliente riceve notifica della nuova routine

### Chat con Clienti
1. Se il cliente ha un coach assegnato, li appare una tab Tab "Chat"
2. Messaggistica diretta 1-to-1
3. Possibilit� di inviare:
   - Messaggi di testo
   - Immagini (es. foto form esercizi)
   - Link a video tutorial
4. Notifiche push per nuovi messaggi

### Calendario e Prenotazioni

#### Impostazione disponibilit� (Coach)
1. Tab "Calendario"
2. Visualizzazione settimanale/mensile
3. Blocchi disponibilit�:
   - Giorni e orari disponibili
   - Durata slot (es. 60 minuti)
   - Tipo seduta (live, online, in palestra)
4. Salva disponibilit�
5. Reminder tipo "aggionare scheda" a cliente X

#### Prenotazione seduta (Cliente)
1. Profilo coach � "Prenota seduta"
2. Visualizza calendario disponibilit� coach
3. Scelta data, ora e tipo di seduta
4. Conferma prenotazione
5. Conferma via notifica a coach e cliente

#### Gestione appuntamenti (Coach)
1. Tab "Calendario" � Vista appuntamenti
2. Lista sedute programmate
3. Tap su seduta:
   - Dettagli cliente
   - Note pre-seduta
   - Possibilit� di riprogrammare/cancellare
4. Check seduta completata

### Notifiche e Promemoria
- Nuovo cliente aggiunto
- Cliente completa allenamento
- Nuovo messaggio in chat
- Seduta prenotata/cancellata
- Promemoria seduta (1 ora prima)
- Cliente inattivo da X giorni

---

## 3� Flusso Interazione Coach-Cliente

### Scenario tipo: Nuovo cliente
1. **Coach**: Invita cliente via email
2. **Cliente**: Riceve email, scarica app, crea account, compila questionario, allega foto sulla condizione del fisico
3. **Coach**: Crea prima routine personalizzata e la assegna, crea macro e li assegna
4. **Cliente**: Riceve notifica, vede nuova routine e macronutrienti
5. **Cliente**: Completa primo allenamento
6. **Coach**: Riceve notifica, visualizza progressi del cliente
7. **Coach**: Invia messaggio di congratulazioni via chat
8. **Cliente**: Risponde e chiede info su un esercizio
9. **Coach**: Risponde e invia video tutorial
10. **Cliente**: Prenota seduta live dal calendario
11. **Coach**: Riceve notifica di prenotazione, conferma
12. **Entrambi**: Ricevono promemoria 1 ora prima della seduta

### Scenario: Monitoraggio progressi
1. **Cliente**: Completa allenamenti regolarmente
2. **Coach**: Controlla periodicamente dashboard cliente
3. **Coach**: Nota miglioramento nei carichi
4. **Coach**: Modifica routine aumentando intensit�
5. **Cliente**: Riceve notifica di nuova routine aggiornata
6. **Cliente**: Visualizza progressi personali nei grafici
7. **Cliente**: Condivide screenshot progressi in chat con coach

---

## = Flusso Abbonamenti e Pagamenti

### Per Coach
1. Registrazione come utente FREE
2. Esplorazione funzionalit� base
3. Click su "Diventa Coach PRO"
4. Schermata piani:
   - PRO Mensile (es. �29/mese)
   - PRO Annuale (es. �290/anno - risparmio)
5. Inserimento dati pagamento
6. Conferma e attivazione immediata
7. Gestione abbonamento da "Impostazioni"

### Prova gratuita (opzionale)
- 1 mese di prova gratuita
- Nessuna carta richiesta
- Alla fine del trial: upgrade o downgrade a FREE
