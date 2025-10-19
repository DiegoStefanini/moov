# ⚙️ Funzionalità Dettagliate MOOV

## 📱 Funzionalità Core (Utenti FREE)

### 1. Gestione Esercizi Custom

#### Caratteristiche
- **Creazione libera**: ogni utente crea i propri esercizi senza database predefinito
- **Campi disponibili**:
  - Nome esercizio (es. "Panca Piana", "Squat", "Curl Bicipiti")
  - Tipo: Forza / Cardio / Flessibilità / Altro
  - **Flag esercizio monolaterale**: indica se l'esercizio si esegue un lato alla volta (es. affondi, curl manubrio singolo)
  - Note personali (tecnica, cues, attrezzatura necessaria)
  - Tag personalizzabili (es. "petto", "push", "compound")
- **Ricerca e filtri**: trova rapidamente esercizi per nome o tag
- **Modifica/eliminazione**: gestione completa degli esercizi creati
- **Template riutilizzabili**: salva esercizi per usarli in più routine

#### Idee aggiuntive
- **Foto/video esercizio**: possibilità di allegare media per ricordare la forma
- **Varianti esercizio**: collega varianti dello stesso movimento (es. panca bilanciere, panca manubri)
- **Attrezzatura richiesta**: tag per filtrare esercizi in base all'attrezzatura disponibile

---

### 2. Creazione e Gestione Routine e Schede

#### Concetto di Scheda
- **Scheda**: insieme di routine (es. una scheda PPL contiene 3 routine: Push, Pull, Legs)
- **Routine**: singolo allenamento con lista di esercizi

#### Caratteristiche
- **Routine multiple**: crea routine diverse per split diversi (Push/Pull/Legs, Upper/Lower, ecc.)
- **Schede organizzate**: raggruppa routine correlate in una scheda
- **Builder intuitivo**:
  - Drag & drop per ordinare esercizi
  - Aggiunta rapida esercizi esistenti
  - Duplicazione routine per creare varianti
- **Configurazione dettagliata per esercizio**:
  - Serie target (es. 3, 4, 5)
  - Range ripetizioni (es. 8-12)
  - Tempo di riposo tra serie (30s, 60s, 90s, custom)
  - Note specifiche per l'esercizio
- **Organizzazione**:
  - Etichette colorate
  - Preferiti / più usate
  - Archiviazione routine/schede vecchie
  - Possibilità di modificare, archiviare, aggiungere routine

#### Idee aggiuntive
- **Superset e circuit**: supporto per superset (A1/A2), triset, circuit training
- **Pianificazione settimanale**: assegna routine a giorni specifici della settimana

---

### 3. Tracciamento Allenamento in Real-Time

#### Caratteristiche
- **Interfaccia allenamento live**:
  - Visualizzazione chiara di esercizio corrente e prossimi
  - Checkbox per ogni serie completata
  - Input rapido peso e ripetizioni (tastierino numerico ottimizzato)
  - Visualizzazione pesi precedenti: "Ultima volta: 80kg x 8 reps"
- **Timer automatico**:
  - Countdown riposo tra serie
  - Notifica sonora/vibrazione quando riposo finito
  - Pausa/resume allenamento
- **Cronometro totale**: traccia durata complessiva allenamento
- **Note durante allenamento**: aggiungi note veloci (sensazioni, dolori, ecc.)
- **Modifica on-the-fly**: aggiungi/rimuovi serie o esercizi durante l'allenamento
- **Upload video serie**: possibilità di registrare e caricare video della serie effettuata per rivedere la tecnica

#### Idee aggiuntive
- **RPE (Rate of Perceived Exertion)**: scala 1-10 per tracciare difficoltà percepita
- **Modalità rest-pause**: timer specifici per tecniche avanzate
- **Playlist music integration**: controlli musica integrati (Spotify/Apple Music)

---

### 4. Storico Allenamenti

#### Caratteristiche
- **Vista calendario**: visualizza allenamenti completati per data
- **Lista cronologica**: scroll infinito di tutti gli allenamenti
- **Dettaglio completo**:
  - Data e ora inizio/fine
  - Durata totale
  - Routine utilizzata (se applicabile)
  - Tutti esercizi, serie, ripetizioni, carichi
  - Note dell'allenamento
- **Filtri**:
  - Per periodo (ultima settimana, mese, anno)
  - Per routine specifica
  - Per esercizio
- **Azioni rapide**:
  - "Ripeti questo allenamento"
  - Modifica allenamento passato (correggere errori)
  - Elimina allenamento

#### Idee aggiuntive
- **Streak tracking**: conta giorni consecutivi di allenamento
- **Badge e achievement**: premi per milestone (100 allenamenti, 1 anno streak, ecc.)
- **Confronto allenamenti**: metti a confronto due allenamenti dello stesso tipo

---

### 5. Grafici e Progressi

#### Caratteristiche principali
- **Progressione peso per esercizio**:
  - Seleziona esercizio specifico
  - Vedi andamento del massimale stimato (1RM)
  - Vedi peso medio usato nel tempo
- **Frequenza allenamenti**: quanti allenamenti a settimana/mese
- **Personal Records (PR)**:
  - Lista PR per esercizio
  - Notifica quando stabilisci nuovo PR
  - Cronologia PR
- **Tracciamento peso corporeo**:
  - Registra peso corporeo nel tempo
  - Grafico andamento peso corporeo
- **Check fisico fotografico**:
  - Carica foto del fisico con data
  - Galleria cronologica delle foto per vedere trasformazione
  - Confronto foto side-by-side

#### Grafici aggiuntivi
- **Volume per gruppo muscolare**: se esercizi sono taggati (petto, schiena, ecc.)
- **Andamento ripetizioni**: vedi se stai aumentando volume via reps o peso
- **Tempo sotto tensione**: se tracciato, vedi TUT totale nel tempo
- **Calorie stimate**: basato su tipo allenamento e durata

#### Visualizzazioni
- **Periodo personalizzabile**: 7 giorni, 30 giorni, 3 mesi, 6 mesi, 1 anno, tutto
- **Export grafici**: salva come immagine o PDF
- **Export dati raw**: CSV per analisi esterne (Excel, Google Sheets)

#### Idee aggiuntive
- **Confronto con periodo passato**: "questo mese vs mese scorso"
- **Heatmap attività**: visual style GitHub contributions

---

## 💼 Funzionalità COACH PRO

### 6. Gestione Clienti

#### Dashboard Clienti
- **Vista elenco**:
  - Foto profilo, nome, status
  - Ultimo allenamento completato
  - Indicatore attività (verde: attivo, giallo: poco attivo, rosso: inattivo >7gg)
- **Ricerca e filtri**:
  - Cerca per nome
  - Filtra per stato (attivo, inattivo, trial)
  - Ordina per ultima attività, nome, data iscrizione

#### Profilo Cliente Dettagliato
- **Informazioni base**: nome, email, telefono, data inizio
- **Storico completo allenamenti** del cliente
  - Tap su un allenamento: vedere carichi e ripetizioni usati, vedere video se allegati
- **Grafici progressi** del cliente (stesse funzionalità utente FREE)
- **Routine assegnate**: quali routine/schede ha il cliente
- **Note private del coach**: note visibili solo al coach
- **Obiettivi**: obiettivi concordati con il cliente
- **Check fisico e peso**:
  - Vedere ultimi check di peso corporeo
  - Galleria foto allegate dal cliente
- **Chat diretta**: accesso diretto alla chat con il cliente
- **Macronutrienti**:
  - Macronutrienti attualmente assegnati
  - Storico macronutrienti assegnati nel tempo
  - Grafico macronutrienti e grafico peso comparabili (stesso periodo, visualizzazione affiancata)
- **Gestione routine**: possibilità di modificare, archiviare, aggiungere routine/schede

#### Invito Clienti
- **Via email**: inserisci email cliente, invio automatico link registrazione
- **Link univoco**: genera link condivisibile (WhatsApp, SMS)
- **Accettazione**:
  - Cliente riceve invito
  - Se non ha account, crea account
  - Compila questionario di onboarding creato dal coach
  - Viene connesso al coach
- **Limite clienti**: nessun limite (o limite basato su piano abbonamento)

#### Questionario Onboarding Personalizzabile
- **Creato dal coach**: ogni coach crea il proprio questionario di default
- **Domande personalizzabili**:
  - Esercizi che non piacciono al cliente
  - Obiettivi
  - Esperienza in palestra
  - Infortuni passati
  - Disponibilità settimanale
- **Compilazione cliente**: all'accettazione invito, cliente compila questionario
- **Visibile al coach**: risposte visibili nel profilo cliente

#### Idee aggiuntive
- **Check-in periodici**: promemoria al coach per check-in settimanale/mensile
- **Progress report automatici**: report mensili generati automaticamente
- **Tag clienti**: organizza clienti per categorie (principiante, avanzato, ipertrofia, forza)

---

### 7. Creazione Routine/Schede per Clienti

#### Caratteristiche
- **Tutte le funzionalità routine FREE** disponibili per coach
- **Assegnazione a cliente**:
  - Seleziona cliente
  - Crea nuova routine/scheda specifica per il cliente
  - Aggiungi istruzioni/note per il cliente
  - Cliente riceve notifica push
- **Modifica routine cliente**:
  - Aggiorna routine in qualsiasi momento
  - Cliente vede modifiche immediatamente
  - Storico modifiche (optional)

#### Idee aggiuntive
- **Periodizzazione**: pianifica progressione su più settimane
- **Deload week**: programma automaticamente settimane di scarico
- **Routine condivise tra clienti**: assegna stessa routine a più clienti con un click

---

### 8. Chat Coach-Cliente

#### Caratteristiche
- **Visibilità chat cliente**: se il cliente ha un coach assegnato, vede una tab "Chat" nella sua app
- **Messaggistica 1-to-1**: chat separata per ogni cliente
- **Tipi di contenuto**:
  - Messaggi di testo
  - Immagini (foto form, progressi fisici)
  - Link (video YouTube tutorial)
  - (Future: video brevi, note vocali)
- **Notifiche push**: entrambi ricevono notifiche per nuovi messaggi
- **Badge non letti**: indica messaggi non letti
- **Stato online/ultimo accesso** (opzionale)

#### Idee aggiuntive
- **Messaggi programmati**: scrivi messaggio e programmalo per invio futuro
- **Risposte rapide**: template risposte frequenti del coach
- **Traduzioni automatiche** (per espansione internazionale)
- **Chat di gruppo**: opzionale per team/gruppi di clienti
- **Feedback post-allenamento**: cliente può inviare feedback rapido dopo allenamento

---

### 9. Calendario e Prenotazioni

#### Funzionalità Coach

##### Impostazione Disponibilità
- **Calendario settimanale ricorrente**:
  - Imposta giorni disponibili (es. Lun, Mer, Ven)
  - Fasce orarie (es. 9:00-13:00, 16:00-20:00)
  - Durata slot (30min, 45min, 60min, 90min)
  - Tipo seduta disponibile: Live in presenza, Online, In palestra
- **Eccezioni**:
  - Blocca date specifiche (vacanze, malattia)
  - Aggiungi disponibilità extra in date specifiche
- **Limiti**:
  - Massimo prenotazioni per giorno
  - Buffer time tra appuntamenti

##### Vista Calendario Coach
- **Visualizzazioni**: giorno, settimana, mese
- **Appuntamenti confermati**: visualizzati con nome cliente
- **Reminder personalizzati**:
  - Crea reminder custom (es. "Aggiornare scheda cliente X")
  - Notifiche in-app per reminder
  - Gestione reminder completati
- **Click su appuntamento**:
  - Dettagli cliente
  - Tipo seduta, durata, location
  - Note pre-seduta
  - Check seduta completata (registra presenza)
  - Opzioni: riprogramma, cancella, invia promemoria
- **Colori**: codifica colore per tipo seduta o stato

#### Funzionalità Cliente

##### Prenotazione Seduta
- **Vista disponibilità coach**: vede slot liberi del proprio coach
- **Selezione**:
  - Scelta data e ora
  - Tipo di seduta (se coach offre più opzioni)
  - Note opzionali per il coach
- **Conferma**: prenotazione confermata immediatamente, entrambi ricevono notifica
- **Gestione prenotazioni**:
  - Lista proprie prenotazioni
  - Cancella prenotazione (con eventuale policy cancellazione)
  - Riprogramma (se permesso)

#### Notifiche e Promemoria
- **24h prima**: promemoria seduta domani
- **1h prima**: promemoria imminente
- **Coach invia promemoria custom**: possibilità di inviare promemoria manuale

#### Idee aggiuntive
- **Integrazione Google Calendar / Apple Calendar**: sync bidirezionale
- **Pagamenti per seduta**: opzionale, sistema di crediti o pagamento per sessione
- **Waitlist**: se slot pieno, cliente può mettersi in lista d'attesa
- **Recensioni sedute**: cliente lascia feedback dopo ogni seduta

---

### 10. Gestione Macronutrienti (Coach)

#### Caratteristiche
- **Assegnazione macronutrienti al cliente**:
  - Inserisci valori: Proteine (g), Carboidrati (g), Grassi (g), Calorie totali
  - Data inizio validità
  - Note/istruzioni dietetiche per il cliente
- **Storico macronutrienti**:
  - Timeline di tutte le assegnazioni macro passate
  - Vedi quando e come sono cambiate le macro nel tempo
- **Visualizzazione nel profilo cliente**:
  - Macro attuali ben visibili
  - Link rapido per modificare
- **Grafici comparabili**:
  - Grafico andamento peso corporeo
  - Grafico macronutrienti assegnati (sovrapponibili o affiancati)
  - Stesso periodo temporale per confronto diretto
  - Utile per vedere correlazione tra cambio macro e peso

#### Visualizzazione Cliente
- **Macro assegnate**: cliente vede le proprie macro nella dashboard
- **Notifica cambio macro**: quando il coach modifica le macro, cliente riceve notifica
- **Storico visibile**: cliente può vedere storico dei propri macro

#### Idee aggiuntive (future)
- **Tracciamento giornaliero intake**: cliente registra cosa mangia (optional, feature avanzata)
- **Suggerimenti pasti**: basato su macro assegnate
- **Grafico aderenza**: se cliente traccia intake, vedi % aderenza alle macro

---

### 11. Dashboard Analytics Coach

#### Metriche Visibili
- **Overview**:
  - Numero totale clienti attivi
  - Allenamenti completati questa settimana (da tutti i clienti)
  - Prossimi appuntamenti oggi/domani
  - Messaggi non letti
- **Performance Clienti**:
  - Classifica clienti più attivi
  - Lista clienti inattivi (alert)
  - Tasso di completamento allenamenti per cliente
- **Revenue** (se applicabile):
  - Guadagni mensili (se sistema pagamenti integrato)
  - Previsione guadagni
  - Sedute completate vs. programmate

#### Idee aggiuntive
- **Report settimanali automatici**: email riassuntiva ogni lunedì
- **Retention rate**: monitora churn clienti
- **Goal tracking clienti**: visualizza quanti clienti stanno raggiungendo obiettivi

---

## 🔔 Sistema Notifiche

### Notifiche Utenti FREE
- **Promemoria allenamento**: "Non ti alleni da 3 giorni, è ora di muoversi!"
- **Nuovo PR**: "Congratulazioni, nuovo record su Squat: 120kg!"
- **Streak achievement**: "10 giorni di fila, continua così!"
- **Routine assegnata** (se ha un coach): "Il tuo coach ti ha assegnato una nuova routine"

### Notifiche Coach
- **Nuovo cliente**: "Mario Rossi ha accettato il tuo invito!"
- **Cliente completa allenamento**: "Luca ha completato Push Day A"
- **Nuovo messaggio**: "Messaggio da Giulia"
- **Nuova prenotazione**: "Anna ha prenotato una seduta per domani alle 15:00"
- **Cancellazione**: "Marco ha cancellato la seduta di oggi"
- **Cliente inattivo**: "Sara non si allena da 7 giorni"
- **Promemoria seduta**: "Seduta con Paolo tra 1 ora"

### Personalizzazione Notifiche
- **Impostazioni granulari**: attiva/disattiva ogni tipo di notifica
- **Quiet hours**: silenzio notifiche in orari specifici
- **Frequenza promemoria**: personalizza frequenza promemoria allenamento

---

## 💳 Sistema Abbonamenti e Pagamenti

### Piani Disponibili

#### FREE
- Tutte le funzionalità di tracciamento personale
- Esercizi e routine illimitati
- Grafici progressi base
- Nessun cliente gestibile

#### COACH PRO - Mensile
- Tutte le funzionalità FREE
- Clienti illimitati (o limite alto, es. 50)
- Chat illimitata
- Calendario e prenotazioni
- Dashboard analytics avanzata
- Supporto prioritario
- **Prezzo**: €29/mese (esempio)

#### COACH PRO - Annuale
- Tutte le funzionalità PRO Mensile
- Sconto rispetto al mensile
- **Prezzo**: €290/anno (esempio, ~€24/mese)

### Gestione Abbonamento
- **Upgrade**: da FREE a PRO in qualsiasi momento
- **Downgrade**: da PRO a FREE (mantiene storico, perde accesso clienti)
- **Cancellazione**: termina abbonamento, valido fino a fine periodo
- **Modifica piano**: switch mensile ↔ annuale
- **Fatture**: storico fatture scaricabili
- **Metodi di pagamento**: carte credito/debito via Stripe

### Trial Gratuito (Opzionale)
- **1 mese gratis**: prova tutte le funzionalità PRO
- **Nessuna carta richiesta** all'inizio del trial
- **Fine trial**: scelta se abbonarsi o tornare a FREE

---

## 🎨 Funzionalità UX/UI

### Tema e Personalizzazione
- **Dark mode / Light mode**: switch automatico o manuale
- **Colori accent personalizzabili**: scegli colore tema preferito
- **Unità di misura**: kg/lbs, cm/inches

### Accessibilità
- **Supporto multi-lingua**: italiano, inglese (espandibile)
- **Font size**: regolazione dimensione testo
- **Contrasto alto**: per ipovedenti
- **Screen reader support**: compatibilità con lettori schermo

### Onboarding e Tutorial
- **First-time user experience**: tutorial interattivo al primo accesso
- **Tooltips contestuali**: spiegazioni inline per nuove funzionalità
- **Video tutorial**: libreria video guide (optional)

---

## 🔮 Funzionalità Future (Post-MVP)

### Integrazioni Wearables
- **Apple Health / Google Fit**: sync allenamenti, frequenza cardiaca, calorie
- **Smartwatch**: app companion per Apple Watch / Wear OS
- **Fitness tracker**: Whoop, Oura, Garmin sync

### Community e Social
- **Feed pubblico**: condividi allenamenti con community (optional, privacy-first)
- **Leaderboard amici**: confronta progressi con amici
- **Sfide**: partecipa a challenge community (es. "Squat Challenge")

### Marketplace
- **Routine premium**: coach possono vendere routine su marketplace
- **Programmi multi-settimana**: pacchetti allenamento a pagamento
- **Revenue share**: coach guadagnano su vendite template

### Analisi Avanzata (Future)
- **Injury prevention**: rileva pattern che potrebbero portare a infortuni basandosi su dati storici
- **Analisi tecnica video**: possibilità di rivedere video caricati con strumenti di annotazione

### Espansione Verticale
- **Nutrizionisti**: funzionalità per tracciare nutrizione
- **Fisioterapisti**: gestione riabilitazione e recovery
- **Team sportivi**: gestione rosa completa (calcio, basket, ecc.)
- **Palestre**: piano enterprise per gestire multipli coach e aree

---

## 🛡️ Funzionalità Sicurezza e Privacy

### Controllo Dati Utente
- **Export completo**: esporta tutti i dati in formato JSON/CSV
- **Cancellazione account**: elimina permanentemente tutti i dati
- **Privacy granulare**: controlla chi vede cosa (se funzionalità social)
- **2FA (Two-Factor Authentication)**: protezione extra account (futura)

### GDPR e Compliance
- **Cookie consent**: banner GDPR-compliant
- **Privacy policy**: chiara e accessibile
- **Termini di servizio**: trasparenti
- **Data retention policy**: chiarezza su quanto tempo conserviamo dati
