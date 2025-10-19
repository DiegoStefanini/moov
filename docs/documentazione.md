# =� Documentazione Tecnica MOOV

## <� Architettura Generale

### Stack Tecnologico Consigliato

#### Frontend (Mobile App)
- **Framework**: React Native 
  - Cross-platform (iOS + Android)
  - Sviluppo rapido
  - Community attiva
- **Linguaggio**: TypeScript
- **State Management**: Redux Toolkit / Zustand
- **UI Library**: React Native Paper / NativeBase
- **Grafici**: Victory Native / Recharts
- **Navigazione**: React Navigation

#### Backend
- **Runtime**: Node.js + Express / NestJS
- **Linguaggio**: TypeScript
- **Database**: PostgreSQL (relazionale per dati strutturati)
- **Cache**: Redis (sessioni, performance)
- **Storage**: AWS S3 / Cloudflare R2 (immagini foto check, video serie, allegati chat)
- **Real-time**: Socket.io (chat, notifiche live)

#### Servizi Esterni
- **Autenticazione**: Firebase Auth / Supabase Auth
- **Pagamenti**: Stripe
- **Notifiche Push**: Firebase Cloud Messaging (FCM)
- **Analytics**: Mixpanel / Amplitude
- **Hosting Backend**: AWS / Railway / Render
- **CDN**: Cloudflare

---

## =� Modello Dati (Database Schema)

### Tabella: Users
```sql
id: UUID (PK)
email: VARCHAR (unique)
password_hash: VARCHAR
name: VARCHAR
profile_picture: VARCHAR (URL)
role: ENUM ('free', 'coach')
subscription_status: ENUM ('active', 'canceled', 'trial')
subscription_end_date: TIMESTAMP
created_at: TIMESTAMP
updated_at: TIMESTAMP
```

### Tabella: Exercises
```sql
id: UUID (PK)
user_id: UUID (FK � Users)
name: VARCHAR
type: ENUM ('strength', 'cardio', 'flexibility')
is_unilateral: BOOLEAN (se esercizio monolaterale: affondi, curl singolo, etc.)
notes: TEXT
is_template: BOOLEAN (se il coach vuole salvare template riutilizzabili)
created_at: TIMESTAMP
```

### Tabella: Programs (Schede - insieme di routine)
```sql
id: UUID (PK)
user_id: UUID (FK � Users) -- creatore della scheda
assigned_to: UUID (FK � Users, nullable) -- se assegnata a cliente
name: VARCHAR (es. "PPL Split", "Upper/Lower")
description: TEXT
is_archived: BOOLEAN (default false)
created_at: TIMESTAMP
updated_at: TIMESTAMP
```

### Tabella: Routines
```sql
id: UUID (PK)
program_id: UUID (FK � Programs, nullable) -- scheda di appartenenza
user_id: UUID (FK � Users) -- creatore della routine
assigned_to: UUID (FK � Users, nullable) -- se assegnata a cliente
name: VARCHAR
description: TEXT
is_archived: BOOLEAN (default false)
created_at: TIMESTAMP
updated_at: TIMESTAMP
```

### Tabella: Routine_Exercises (Join table)
```sql
id: UUID (PK)
routine_id: UUID (FK � Routines)
exercise_id: UUID (FK � Exercises)
order: INTEGER (ordine esercizio nella routine)
target_sets: INTEGER
target_reps_min: INTEGER
target_reps_max: INTEGER
rest_time_seconds: INTEGER
```

### Tabella: Workouts (Allenamenti completati)
```sql
id: UUID (PK)
user_id: UUID (FK � Users)
routine_id: UUID (FK � Routines, nullable)
started_at: TIMESTAMP
completed_at: TIMESTAMP
duration_minutes: INTEGER
notes: TEXT
```

### Tabella: Workout_Sets (Serie completate)
```sql
id: UUID (PK)
workout_id: UUID (FK � Workouts)
exercise_id: UUID (FK � Exercises)
set_number: INTEGER
weight_kg: DECIMAL
reps: INTEGER
rpe: INTEGER (Rate of Perceived Exertion, opzionale)
video_url: VARCHAR (nullable, URL del video della serie caricato)
completed_at: TIMESTAMP
```

### Tabella: Coach_Clients (Relazione coach-clienti)
```sql
id: UUID (PK)
coach_id: UUID (FK � Users)
client_id: UUID (FK � Users)
status: ENUM ('pending', 'active', 'inactive')
joined_at: TIMESTAMP
```

### Tabella: Messages (Chat)
```sql
id: UUID (PK)
sender_id: UUID (FK � Users)
receiver_id: UUID (FK � Users)
message: TEXT
attachment_url: VARCHAR (nullable)
read_at: TIMESTAMP (nullable)
created_at: TIMESTAMP
```

### Tabella: Appointments (Sedute programmate)
```sql
id: UUID (PK)
coach_id: UUID (FK � Users)
client_id: UUID (FK � Users)
scheduled_at: TIMESTAMP
duration_minutes: INTEGER
type: ENUM ('live', 'online', 'gym')
status: ENUM ('scheduled', 'completed', 'canceled')
location: VARCHAR (nullable)
notes: TEXT
created_at: TIMESTAMP
```

### Tabella: Coach_Availability (Disponibilit� coach)
```sql
id: UUID (PK)
coach_id: UUID (FK � Users)
day_of_week: INTEGER (0-6)
start_time: TIME
end_time: TIME
slot_duration_minutes: INTEGER
is_active: BOOLEAN
```

### Tabella: Subscriptions (Gestione abbonamenti)
```sql
id: UUID (PK)
user_id: UUID (FK � Users)
stripe_customer_id: VARCHAR
stripe_subscription_id: VARCHAR
plan_type: ENUM ('monthly', 'yearly')
status: ENUM ('active', 'canceled', 'past_due', 'trial')
current_period_start: TIMESTAMP
current_period_end: TIMESTAMP
created_at: TIMESTAMP
```

### Tabella: Body_Weight_Records (Tracciamento peso corporeo)
```sql
id: UUID (PK)
user_id: UUID (FK � Users)
weight_kg: DECIMAL
recorded_at: TIMESTAMP
notes: TEXT (nullable)
```

### Tabella: Body_Check_Photos (Foto check fisico)
```sql
id: UUID (PK)
user_id: UUID (FK � Users)
photo_url: VARCHAR
recorded_at: TIMESTAMP
notes: TEXT (nullable)
```

### Tabella: Macronutrients (Assegnazione macronutrienti)
```sql
id: UUID (PK)
client_id: UUID (FK � Users)
coach_id: UUID (FK � Users)
protein_g: INTEGER
carbs_g: INTEGER
fats_g: INTEGER
calories: INTEGER
notes: TEXT (nullable, istruzioni dietetiche)
valid_from: TIMESTAMP
valid_to: TIMESTAMP (nullable, se NULL = ancora valido)
created_at: TIMESTAMP
```

### Tabella: Coach_Questionnaires (Questionari coach)
```sql
id: UUID (PK)
coach_id: UUID (FK � Users)
is_default: BOOLEAN (se questionario di default per nuovi clienti)
created_at: TIMESTAMP
updated_at: TIMESTAMP
```

### Tabella: Questionnaire_Questions (Domande questionario)
```sql
id: UUID (PK)
questionnaire_id: UUID (FK � Coach_Questionnaires)
question_text: TEXT
question_type: ENUM ('text', 'multiple_choice', 'yes_no')
order: INTEGER
is_required: BOOLEAN
created_at: TIMESTAMP
```

### Tabella: Questionnaire_Answers (Risposte clienti)
```sql
id: UUID (PK)
question_id: UUID (FK � Questionnaire_Questions)
client_id: UUID (FK � Users)
answer_text: TEXT
answered_at: TIMESTAMP
```

### Tabella: Calendar_Reminders (Reminder personalizzati coach)
```sql
id: UUID (PK)
coach_id: UUID (FK � Users)
client_id: UUID (FK � Users, nullable) -- se riferito a un cliente specifico
title: VARCHAR
description: TEXT (nullable)
reminder_date: TIMESTAMP
is_completed: BOOLEAN (default false)
created_at: TIMESTAMP
```

---

## = API Endpoints (Principali)

### Autenticazione
- `POST /auth/register` - Registrazione utente
- `POST /auth/login` - Login
- `POST /auth/logout` - Logout
- `POST /auth/refresh` - Refresh token

### Esercizi
- `GET /exercises` - Lista esercizi dell'utente
- `POST /exercises` - Crea nuovo esercizio
- `PUT /exercises/:id` - Modifica esercizio
- `DELETE /exercises/:id` - Elimina esercizio

### Schede (Programs)
- `GET /programs` - Lista schede dell'utente
- `POST /programs` - Crea scheda
- `GET /programs/:id` - Dettaglio scheda con routine
- `PUT /programs/:id` - Modifica scheda
- `DELETE /programs/:id` - Elimina scheda
- `PUT /programs/:id/archive` - Archivia scheda
- `POST /programs/:id/assign` - Assegna scheda a cliente (solo coach)

### Routine
- `GET /routines` - Lista routine dell'utente
- `POST /routines` - Crea routine
- `GET /routines/:id` - Dettaglio routine
- `PUT /routines/:id` - Modifica routine
- `DELETE /routines/:id` - Elimina routine
- `PUT /routines/:id/archive` - Archivia routine
- `POST /routines/:id/assign` - Assegna routine a cliente (solo coach)

### Allenamenti
- `POST /workouts` - Inizia nuovo allenamento
- `PUT /workouts/:id/complete` - Completa allenamento
- `GET /workouts` - Storico allenamenti
- `GET /workouts/:id` - Dettaglio allenamento
- `POST /workouts/:id/sets` - Aggiungi serie completata
- `POST /workouts/sets/:setId/upload-video` - Upload video serie (multipart/form-data)

### Progressi
- `GET /progress/overview` - Panoramica progressi
- `GET /progress/exercise/:exerciseId` - Progressi per esercizio specifico
- `GET /progress/frequency` - Frequenza allenamenti

### Peso Corporeo e Check Fisico
- `POST /body-weight` - Registra peso corporeo
- `GET /body-weight` - Storico peso corporeo
- `GET /body-weight/chart` - Dati per grafico peso
- `POST /body-check-photos` - Upload foto check fisico
- `GET /body-check-photos` - Galleria foto check
- `DELETE /body-check-photos/:id` - Elimina foto

### Coach - Clienti (solo per coach PRO)
- `POST /coach/invite-client` - Invita cliente
- `GET /coach/clients` - Lista clienti
- `GET /coach/clients/:id` - Dettaglio cliente e progressi
- `DELETE /coach/clients/:id` - Rimuovi cliente

### Chat
- `GET /messages/:userId` - Conversazione con utente
- `POST /messages` - Invia messaggio
- `PUT /messages/:id/read` - Segna come letto

### Calendario
- `GET /appointments` - Lista appuntamenti
- `POST /appointments` - Crea appuntamento
- `PUT /appointments/:id` - Modifica appuntamento
- `DELETE /appointments/:id` - Cancella appuntamento
- `GET /coach/availability` - Disponibilit� coach
- `POST /coach/availability` - Imposta disponibilit�
- `GET /calendar/reminders` - Lista reminder coach
- `POST /calendar/reminders` - Crea reminder personalizzato
- `PUT /calendar/reminders/:id` - Modifica reminder
- `PUT /calendar/reminders/:id/complete` - Segna reminder come completato
- `DELETE /calendar/reminders/:id` - Elimina reminder

### Macronutrienti (Coach)
- `POST /coach/clients/:clientId/macros` - Assegna macronutrienti a cliente
- `GET /coach/clients/:clientId/macros` - Storico macro cliente
- `GET /coach/clients/:clientId/macros/current` - Macro attuali del cliente
- `PUT /coach/clients/:clientId/macros/:id` - Modifica macro
- `GET /coach/clients/:clientId/macros-weight-chart` - Dati comparabili macro/peso

### Questionari (Coach)
- `GET /coach/questionnaires` - Lista questionari del coach
- `POST /coach/questionnaires` - Crea questionario
- `PUT /coach/questionnaires/:id` - Modifica questionario
- `PUT /coach/questionnaires/:id/set-default` - Imposta come questionario default
- `GET /coach/clients/:clientId/questionnaire-answers` - Risposte del cliente
- `POST /questionnaire-answers` - Cliente invia risposte (durante onboarding)

### Abbonamenti
- `POST /subscription/create-checkout` - Crea sessione pagamento
- `POST /subscription/webhook` - Webhook Stripe
- `GET /subscription/status` - Stato abbonamento
- `POST /subscription/cancel` - Cancella abbonamento

---

## <� Struttura UI/UX

### Navigazione Principale (Bottom Tab)

#### Per utenti FREE:
1. **Home** - Dashboard, inizia allenamento
2. **Routine** - Gestione routine
3. **Progressi** - Grafici e statistiche
4. **Profilo** - Impostazioni, upgrade

#### Per Coach PRO:
1. **Home** - Dashboard, inizia allenamento
2. **Clienti** - Lista e gestione clienti
3. **Calendario** - Sedute e disponibilit�
4. **Routine** - Gestione routine (personali e clienti)
5. **Profilo** - Impostazioni, abbonamento

### Schermate Principali

#### Home (FREE)
- Benvenuto con nome utente
- CTA "Inizia Allenamento"
- Statistiche veloci: ultimo allenamento, streak, PR recenti
- Lista ultime routine usate

#### Home (COACH)
- Dashboard clienti attivi
- Prossimi appuntamenti oggi
- Notifiche: nuovi messaggi, allenamenti completati
- CTA "Allena un cliente" / "Inizia allenamento personale"

#### Schermata Allenamento
- Timer in alto
- Lista esercizi con checkbox
- Per ogni serie: input peso + reps
- Visualizzazione peso precedente
- Timer riposo tra serie
- Note rapide
- Pulsante "Completa allenamento"

#### Grafici Progressi
- Selettore periodo (7gg, 30gg, 90gg, anno)
- Grafico volume totale (line chart)
- Grafico peso per esercizio (line chart)
- Lista personal records
- Esportazione dati

---

## = Sicurezza e Privacy

### Autenticazione
- Password hash con bcrypt
- JWT per sessioni (access + refresh token)
- Rate limiting su login
- 2FA opzionale (futura implementazione)

### Autorizzazione
- Middleware per verificare ruolo utente
- Coach pu� accedere solo ai dati dei propri clienti
- Utenti vedono solo i propri dati

### Privacy
- GDPR compliant
- Opzione esportazione dati utente
- Opzione cancellazione account
- Privacy policy e termini d'uso

---

## =� Analytics e Metriche da Tracciare

### Metriche Utente
- Daily Active Users (DAU)
- Tasso di retention (D1, D7, D30)
- Allenamenti completati per utente
- Tempo medio in app
- Feature pi� usate

### Metriche Coach
- Numero medio clienti per coach
- Tasso di conversione FREE � PRO
- Churn rate abbonamenti
- Utilizzo calendario e chat
- Revenue per coach

### Metriche Business
- MRR (Monthly Recurring Revenue)
- LTV (Lifetime Value)
- CAC (Customer Acquisition Cost)
- Conversion rate trial � paid

---

## =� Roadmap di Sviluppo

### MVP (Fase 1) - 3 mesi
- [ ] Autenticazione utenti
- [ ] Creazione esercizi custom (con flag monolaterale)
- [ ] Creazione schede e routine
- [ ] Tracciamento allenamenti base con timer
- [ ] Storico allenamenti
- [ ] Grafici progressi base (peso per esercizio, frequenza)
- [ ] Tracciamento peso corporeo
- [ ] Upload foto check fisico
- [ ] Visualizzazione peso precedente durante allenamento

### Fase 2 - 3 mesi
- [ ] Sistema coach-cliente
- [ ] Gestione abbonamenti Stripe (con trial 1 mese)
- [ ] Questionari personalizzabili per onboarding clienti
- [ ] Chat 1-to-1
- [ ] Notifiche push
- [ ] Assegnazione routine/schede ai clienti
- [ ] Gestione macronutrienti (assegnazione e storico)
- [ ] Grafici comparabili macro/peso
- [ ] Dashboard coach con metriche clienti

### Fase 3 - 2 mesi
- [ ] Calendario e prenotazioni
- [ ] Gestione disponibilit� coach
- [ ] Reminder personalizzati calendario
- [ ] Upload video serie durante allenamento
- [ ] Visualizzazione video allenamenti clienti (coach)
- [ ] Archiviazione routine/schede
- [ ] Export dati PDF/CSV
- [ ] Grafici avanzati (PRs, confronti foto)

### Fase 4 (Future)
- [ ] Programmi di allenamento multi-settimana (periodizzazione)
- [ ] Integrazione con wearables (Apple Health, Google Fit)
- [ ] Tracciamento intake nutrizionale giornaliero (opzionale)
- [ ] Analisi video con annotazioni
- [ ] Marketplace routine/programmi
- [ ] Community e social features
- [ ] Piano per palestre (gestione multipla coach)
