# 🎯 Priorità di Sviluppo MOOV

## 📋 Strategia di Rilascio

### Approccio: Build-Measure-Learn
1. **MVP veloce**: 3 mesi per validare il prodotto con utenti FREE
2. **Monetizzazione**: 3 mesi per funzionalità COACH e iniziare revenue
3. **Scale**: 2 mesi per funzionalità avanzate e ottimizzazione
4. **Espansione**: features future basate su feedback

---

## 🚀 FASE 1: MVP - Utenti FREE (3 mesi)

**Obiettivo**: Creare un'app funzionante per utenti individuali che vogliono tracciare i propri allenamenti.

### Settimane 1-4: Foundation & Auth
**Priorità: CRITICA**

#### Backend
- [ ] Setup progetto Node.js + TypeScript + PostgreSQL
- [ ] Schema database (Users, Exercises, Programs, Routines, Routine_Exercises)
- [ ] API Authentication (register, login, logout, refresh token)
- [ ] Middleware autorizzazione e validazione
- [ ] Setup AWS S3 / Cloudflare R2 per storage immagini

#### Frontend
- [ ] Setup React Native + TypeScript
- [ ] Navigazione base (React Navigation)
- [ ] Schermate Auth (Login, Registrazione)
- [ ] State management (Redux Toolkit / Zustand)
- [ ] UI Library setup (React Native Paper)
- [ ] Gestione token e auth flow

**Deliverable**: Utente può registrarsi, fare login e vedere schermata home vuota.

---

### Settimane 5-8: Esercizi & Routine
**Priorità: CRITICA**

#### Backend
- [ ] API Exercises CRUD
- [ ] API Programs CRUD
- [ ] API Routines CRUD (con relazione a Programs)
- [ ] API Routine_Exercises (join table)

#### Frontend
- [ ] Schermata "Esercizi"
  - [ ] Lista esercizi
  - [ ] Creazione esercizio (nome, tipo, flag monolaterale, note)
  - [ ] Modifica/eliminazione esercizio
  - [ ] Ricerca esercizi
- [ ] Schermata "Schede"
  - [ ] Lista schede (programs)
  - [ ] Creazione scheda
  - [ ] Visualizzazione routine di una scheda
- [ ] Schermata "Routine"
  - [ ] Creazione routine (seleziona scheda, aggiungi esercizi)
  - [ ] Drag & drop ordinamento esercizi
  - [ ] Configurazione serie/reps/riposo per esercizio
  - [ ] Salva routine

**Deliverable**: Utente può creare esercizi custom e organizzarli in schede/routine.

---

### Settimane 9-12: Tracciamento Allenamento
**Priorità: CRITICA**

#### Backend
- [ ] API Workouts (start, complete)
- [ ] API Workout_Sets (aggiungi serie)
- [ ] Query per recuperare pesi precedenti per esercizio
- [ ] Tabella Body_Weight_Records
- [ ] Tabella Body_Check_Photos
- [ ] API upload foto check fisico

#### Frontend
- [ ] Schermata "Inizia Allenamento"
  - [ ] Selezione routine
  - [ ] Visualizzazione esercizi
  - [ ] **Mostra peso/reps ultimo allenamento** per ogni esercizio
  - [ ] Input peso e reps per ogni serie
  - [ ] Checkbox serie completata
  - [ ] Timer riposo automatico tra serie (personalizzabile)
  - [ ] Cronometro totale allenamento
  - [ ] Note allenamento
  - [ ] Bottone "Completa allenamento"
- [ ] Schermata "Storico"
  - [ ] Lista allenamenti cronologica
  - [ ] Dettaglio allenamento (tutti i dati)
  - [ ] Possibilità ripetere allenamento
- [ ] Schermata "Progressi"
  - [ ] Input peso corporeo
  - [ ] Upload foto check fisico
  - [ ] Galleria foto cronologica

**Deliverable**: Utente può completare allenamenti, vedere storico e tracciare peso corporeo/foto.

---

### Settimane 13-14: Grafici & Polish MVP
**Priorità: ALTA**

#### Backend
- [ ] API grafici (progressi per esercizio, frequenza allenamenti)
- [ ] API grafico peso corporeo

#### Frontend
- [ ] Grafici con Victory Native / Recharts:
  - [ ] Progressione peso per esercizio (line chart)
  - [ ] Frequenza allenamenti (bar chart)
  - [ ] Grafico peso corporeo (line chart)
  - [ ] Personal Records lista
- [ ] Filtri periodo (7gg, 30gg, 90gg, anno)
- [ ] Polish UI/UX generale
- [ ] Dark mode
- [ ] Onboarding tutorial

#### Testing & Deployment
- [ ] Testing end-to-end flussi principali
- [ ] Deploy backend (Railway / Render / AWS)
- [ ] Build app (TestFlight iOS, Google Play Beta)
- [ ] **Alpha test con 10-20 utenti**

**Deliverable**: MVP completo pronto per test con utenti reali FREE.

---

## 💼 FASE 2: Monetizzazione COACH (3 mesi)

**Obiettivo**: Introdurre funzionalità COACH PRO e iniziare a generare revenue.

### Settimane 15-18: Sistema Coach-Cliente
**Priorità: CRITICA**

#### Backend
- [ ] Tabella Coach_Clients
- [ ] Tabella Coach_Questionnaires, Questionnaire_Questions, Questionnaire_Answers
- [ ] API invito cliente (email/link)
- [ ] API questionari coach (CRUD)
- [ ] API risposte questionario (cliente compila)
- [ ] API lista clienti coach
- [ ] API dettaglio cliente (progressi, allenamenti)
- [ ] Middleware verifica coach può accedere solo ai propri clienti

#### Frontend
- [ ] Upgrade UI: aggiungere tab "Clienti" per coach
- [ ] Schermata "Diventa Coach" (CTA upgrade)
- [ ] Schermata "Invita Cliente" (email/link)
- [ ] Schermata "Lista Clienti"
  - [ ] Cards clienti con status (verde/giallo/rosso)
  - [ ] Filtri e ricerca
- [ ] Schermata "Profilo Cliente"
  - [ ] Info base
  - [ ] Storico allenamenti
  - [ ] Grafici progressi
  - [ ] Visualizza peso e foto check cliente
- [ ] Schermata "Crea Questionario" (coach)
- [ ] Schermata "Compila Questionario" (cliente onboarding)

**Deliverable**: Coach può invitare clienti, clienti compilano questionario e appaiono nella dashboard coach.

---

### Settimane 19-22: Abbonamenti & Macronutrienti
**Priorità: CRITICA**

#### Backend
- [ ] Setup Stripe
- [ ] Tabella Subscriptions
- [ ] API create checkout session
- [ ] Webhook Stripe (gestione eventi subscription)
- [ ] API subscription status / cancel
- [ ] Middleware verifica subscription attivo per funzionalità coach
- [ ] **Trial 1 mese gratuito** (logica)
- [ ] Tabella Macronutrients
- [ ] API assegnazione macro a cliente
- [ ] API storico macro cliente
- [ ] API dati grafici macro/peso comparabili

#### Frontend
- [ ] Schermata "Abbonamento Coach"
  - [ ] Piani (mensile €29, annuale €290)
  - [ ] Integrazione Stripe Checkout
  - [ ] Gestione abbonamento (cancellazione, modifica piano)
- [ ] Schermata "Macronutrienti" (nel profilo cliente)
  - [ ] Form assegnazione macro (proteine, carbo, grassi, calorie, note)
  - [ ] Storico macro timeline
  - [ ] Grafico comparabile macro/peso (affiancato o sovrapposto)
- [ ] Notifica cliente quando macro vengono assegnate/modificate

**Deliverable**: Coach può abbonarsi (con trial), gestire macro clienti e iniziare revenue.

---

### Settimane 23-26: Chat & Notifiche
**Priorità: ALTA**

#### Backend
- [ ] Tabella Messages
- [ ] Setup Socket.io per real-time
- [ ] API messaggi (invio, lista conversazione, segna letto)
- [ ] Upload allegati chat (immagini)
- [ ] Setup Firebase Cloud Messaging (FCM)
- [ ] Sistema notifiche push:
  - [ ] Nuovo messaggio
  - [ ] Cliente completa allenamento
  - [ ] Nuovo cliente
  - [ ] Cliente inattivo
  - [ ] Routine assegnata
  - [ ] Macro modificate

#### Frontend
- [ ] Tab "Chat" (visibile solo se cliente ha coach)
- [ ] Schermata Chat 1-to-1
  - [ ] Messaggi testo
  - [ ] Invio immagini
  - [ ] Badge messaggi non letti
- [ ] Integrazione notifiche push
- [ ] Gestione permessi notifiche
- [ ] Schermata impostazioni notifiche (granulari)

**Deliverable**: Coach e clienti possono chattare, sistema notifiche funzionante.

---

### Settimane 27: Dashboard Coach & Polish
**Priorità: MEDIA**

#### Backend
- [ ] API analytics coach (numero clienti, allenamenti completati, ecc.)

#### Frontend
- [ ] Dashboard Coach avanzata:
  - [ ] Overview clienti attivi
  - [ ] Allenamenti completati questa settimana (tutti clienti)
  - [ ] Messaggi non letti
  - [ ] Lista clienti inattivi (alert)
- [ ] Assegnazione routine a cliente (coach crea routine → assegna)
- [ ] Cliente visualizza routine assegnate dal coach
- [ ] Testing completo flusso coach-cliente
- [ ] **Beta test con 5-10 coach**

**Deliverable**: Funzionalità coach complete, pronte per lancio beta.

---

## 🔥 FASE 3: Funzionalità Avanzate (2 mesi)

**Obiettivo**: Aggiungere calendario, video, archiviazione e features premium.

### Settimane 28-31: Calendario & Prenotazioni
**Priorità: MEDIA**

#### Backend
- [ ] Tabella Appointments
- [ ] Tabella Coach_Availability
- [ ] Tabella Calendar_Reminders
- [ ] API disponibilità coach (CRUD)
- [ ] API appuntamenti (CRUD, prenotazione cliente)
- [ ] API reminder personalizzati coach
- [ ] Logica controllo slot disponibili

#### Frontend
- [ ] Tab "Calendario" (coach)
- [ ] Schermata "Imposta Disponibilità" (coach)
  - [ ] Giorni/orari ricorrenti
  - [ ] Durata slot
  - [ ] Tipo seduta (live, online, gym)
- [ ] Visualizzazione calendario (settimana/mese)
- [ ] Schermata "Prenota Seduta" (cliente)
  - [ ] Visualizza disponibilità coach
  - [ ] Selezione data/ora/tipo
  - [ ] Conferma prenotazione
- [ ] Gestione appuntamenti (coach)
  - [ ] Check seduta completata
  - [ ] Riprogramma/cancella
- [ ] Reminder personalizzati (es. "aggiornare scheda cliente X")
- [ ] Notifiche prenotazione/cancellazione

**Deliverable**: Sistema calendario completo e funzionante.

---

### Settimane 32-35: Video Serie & Export Dati
**Priorità: MEDIA**

#### Backend
- [ ] API upload video serie (multipart/form-data)
- [ ] Storage video su S3/R2 con compressione
- [ ] API recupero video serie
- [ ] API export dati (PDF/CSV) allenamenti e grafici

#### Frontend
- [ ] Durante allenamento: possibilità registrare/caricare video serie
- [ ] Visualizzazione video nel dettaglio allenamento (utente)
- [ ] Coach: vedere video serie clienti
- [ ] Archiviazione routine/schede (flag is_archived)
- [ ] Sezione "Archivio" per routine/schede
- [ ] Export dati:
  - [ ] Export storico allenamenti (CSV)
  - [ ] Export grafici (PDF/PNG)
- [ ] Grafici avanzati:
  - [ ] Confronto foto check side-by-side
  - [ ] Heatmap attività
  - [ ] Confronto periodi (questo mese vs scorso)

**Deliverable**: Video serie, archiviazione e export dati disponibili.

---

## 🔮 FASE 4: Features Future (Roadmap aperta)

**Priorità: DA VALUTARE** basandosi su feedback utenti e metriche

### Periodizzazione & Programmi Multi-Settimana
- [ ] Tabella Programs_Weeks (settimane di un programma)
- [ ] Assegnazione progressiva settimane
- [ ] Deload week automatici
- [ ] Vista timeline programma

### Integrazione Wearables
- [ ] Apple Health integration (HealthKit)
- [ ] Google Fit integration
- [ ] Sync allenamenti, frequenza cardiaca, calorie

### Tracciamento Nutrizionale (Opzionale)
- [ ] Tabella Daily_Food_Logs
- [ ] Input pasti giornalieri
- [ ] Calcolo macro giornaliere
- [ ] Grafico aderenza macro assegnate vs consumate

### Marketplace & Community
- [ ] Routine/programmi premium vendibili
- [ ] Revenue share coach (80/20)
- [ ] Feed pubblico (opzionale, privacy-first)
- [ ] Leaderboard amici
- [ ] Challenge community

### Piano Palestre
- [ ] Multi-coach management
- [ ] Gestione abbonamenti palestra
- [ ] Report aggregati palestra
- [ ] Check-in QR code

---

## 📊 Metriche di Successo per Fase

### MVP (Fase 1)
- **Target**: 100 utenti attivi in 1 mese dal lancio
- **Retention D7**: >40%
- **Retention D30**: >20%
- **Allenamenti per utente/settimana**: ≥2

### Coach (Fase 2)
- **Target**: 20 coach PRO in 2 mesi dal lancio funzionalità
- **Conversion FREE → PRO**: >5%
- **Trial → Paid**: >30%
- **MRR**: €500+ a fine Fase 2

### Advanced (Fase 3)
- **Target**: 50 coach PRO, 500+ utenti FREE
- **Churn rate coach**: <10%/mese
- **Utilizzo calendario**: >60% coach
- **Upload video**: >30% allenamenti

---

## 🎯 Decisioni Critiche Early-Stage

### Da Decidere Subito (Fase 1)
1. **Framework mobile**: React Native o Flutter?
   - **Raccomandazione**: React Native (ecosistema più maturo, hiring più facile)
2. **Hosting backend**: AWS, Railway, Render?
   - **Raccomandazione**: Railway (MVP veloce, poi migrate AWS se scala)
3. **Storage**: S3 o Cloudflare R2?
   - **Raccomandazione**: Cloudflare R2 (più economico, egress gratis)

### Da Decidere Fase 2
1. **Trial duration**: 14 giorni o 1 mese?
   - **Confermato**: 1 mese (più tempo per coach provare con clienti reali)
2. **Prezzi**: €29/mese, €290/anno?
   - **Da validare**: A/B test su pricing
3. **Limite clienti coach**: illimitati o tier (es. 10/30/unlimited)?
   - **Raccomandazione**: Iniziare illimitati, valutare tier dopo

### Da Decidere Fase 3
1. **Video storage**: quanto storage per video?
   - **Raccomandazione**: 500MB/utente, poi tier premium
2. **Marketplace**: quando introdurlo?
   - **Raccomandazione**: Solo dopo 100+ coach attivi

---

## 🚦 Go/No-Go Milestones

### Fine Fase 1 (Mese 3)
**GO se**:
- ✅ 50+ utenti attivi
- ✅ Retention D7 >35%
- ✅ 0 bug critici
- ✅ Feedback positivo (NPS >30)

**NO-GO se**:
- ❌ <20 utenti attivi
- ❌ Retention D7 <20%
- ❌ Bug critici irrisolti

### Fine Fase 2 (Mese 6)
**GO se**:
- ✅ 10+ coach PRO paganti
- ✅ MRR >€300
- ✅ Churn <15%/mese
- ✅ Coach feedback positivo

**NO-GO se**:
- ❌ <5 coach PRO
- ❌ Churn >30%/mese
- ❌ Coach non usano funzionalità

---

## 💡 Quick Wins (Low-Effort, High-Impact)

### Durante MVP
- [ ] **Streak counter**: mostra giorni consecutivi allenamento (motivazione++)
- [ ] **PR notifications**: notifica quando stabilisci nuovo record
- [ ] **Quick start**: bottone "Ripeti ultimo allenamento"
- [ ] **Template routine**: 3-4 routine pre-built (PPL, Full Body) per onboarding

### Durante Fase Coach
- [ ] **Referral program**: coach invita coach, sconto 1 mese
- [ ] **Email marketing**: welcome email sequence per nuovi coach
- [ ] **Tutorial video**: 2-3 video tutorial per coach su come usare app
- [ ] **Template questionario**: questionario di default già pre-compilato

---

## 🔧 Tech Debt & Maintenance

### Ogni Sprint (2 settimane)
- [ ] Code review 100% PR
- [ ] Fix bug critici entro 24h
- [ ] Test coverage >70% (backend)
- [ ] Performance monitoring (Sentry, LogRocket)

### Ogni Fase
- [ ] Refactoring codice legacy
- [ ] Update dipendenze
- [ ] Security audit
- [ ] Database optimization (indexes, queries)

### Pre-Produzione Fase 1
- [ ] Setup CI/CD (GitHub Actions)
- [ ] Staging environment
- [ ] Automated testing pipeline
- [ ] Monitoring & alerting (Datadog / New Relic)

---

## 📅 Timeline Recap

| Fase | Duration | Focus | Output |
|------|----------|-------|--------|
| **Fase 1** | 3 mesi | MVP Utenti FREE | App funzionante, 100+ utenti |
| **Fase 2** | 3 mesi | Monetizzazione COACH | 20+ coach PRO, MRR €500+ |
| **Fase 3** | 2 mesi | Features Avanzate | Calendario, Video, Export |
| **Fase 4** | Ongoing | Espansione | Marketplace, Wearables, Gym |

**Total time to revenue**: 6 mesi
**Total time to product-market fit**: 8-12 mesi
