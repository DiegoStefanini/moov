# 🏋️ MOOV

**La piattaforma digitale per il fitness che permette a tutti di monitorare i propri progressi in palestra, e ai personal trainer di gestire in modo semplice e intelligente i propri clienti.**

---

## 🎯 Visione

MOOV è un'app mobile che rivoluziona il modo in cui le persone tracciano i loro allenamenti e i coach gestiscono i loro clienti. Con un'interfaccia semplice e intuitiva in italiano, MOOV combina potenti funzionalità di tracciamento con strumenti professionali per coach.

### Due Modalità

**👤 Utenti FREE** - Tracciamento personale
- Crea esercizi custom e routine personalizzate
- Traccia allenamenti con timer e visualizzazione pesi precedenti
- Grafici progressi (peso per esercizio, frequenza, PR)
- Monitora peso corporeo e foto check fisico

**💼 Coach PRO** - Gestione clienti professionale
- Tutte le funzionalità FREE
- Gestisci clienti illimitati con dashboard dedicata
- Chat diretta con ogni cliente
- Assegna routine e macronutrienti
- Calendario con prenotazioni sedute
- Questionari personalizzabili per onboarding

---

## 📚 Documentazione

Tutta la documentazione del progetto si trova nella cartella [`/docs`](./docs):

- **[obiettivo.md](./docs/obiettivo.md)** - Visione, problema e soluzione
- **[flussi.md](./docs/flussi.md)** - Flussi utente dettagliati
- **[funzionalita.md](./docs/funzionalita.md)** - Tutte le features nel dettaglio
- **[documentazione.md](./docs/documentazione.md)** - Architettura tecnica completa
- **[priorita-sviluppo.md](./docs/priorita-sviluppo.md)** - Roadmap esecutiva fase per fase
- **[database-schema.md](./docs/database-schema.md)** - Schema ER + queries ottimizzate

---

## 🏗️ Stack Tecnologico (Proposto)

### Frontend (Mobile)
- **React Native** - Cross-platform iOS & Android
- **TypeScript** - Type safety
- **Redux Toolkit / Zustand** - State management
- **React Native Paper** - UI components
- **Victory Native** - Grafici
- **React Navigation** - Navigazione

### Backend
- **Node.js + Express / NestJS** - API REST
- **TypeScript**
- **PostgreSQL** - Database relazionale
- **Redis** - Cache e sessioni
- **Socket.io** - Chat real-time
- **AWS S3 / Cloudflare R2** - Storage immagini/video

### Servizi Esterni
- **Stripe** - Pagamenti e abbonamenti
- **Firebase Auth** - Autenticazione
- **Firebase Cloud Messaging** - Notifiche push

---

## 📅 Roadmap

### Fase 1: MVP - Utenti FREE (3 mesi)
- ✅ Autenticazione utenti
- ✅ Creazione esercizi custom (con flag monolaterale)
- ✅ Creazione schede e routine
- ✅ Tracciamento allenamenti con timer
- ✅ Storico allenamenti
- ✅ Grafici progressi base
- ✅ Tracciamento peso corporeo e foto check

**Target**: 100+ utenti attivi, Retention D7 >40%

### Fase 2: Monetizzazione COACH (3 mesi)
- ✅ Sistema coach-cliente
- ✅ Gestione abbonamenti Stripe (trial 1 mese)
- ✅ Questionari personalizzabili
- ✅ Chat 1-to-1
- ✅ Notifiche push
- ✅ Gestione macronutrienti
- ✅ Dashboard coach

**Target**: 20+ coach PRO, MRR €500+

### Fase 3: Features Avanzate (2 mesi)
- ✅ Calendario e prenotazioni
- ✅ Upload video serie
- ✅ Archiviazione routine/schede
- ✅ Export dati PDF/CSV

**Target**: 50 coach PRO, 500+ utenti FREE

### Fase 4: Espansione (Ongoing)
- Integrazione wearables (Apple Health, Google Fit)
- Marketplace routine premium
- Tracciamento nutrizionale avanzato
- Piano per palestre (multi-coach)

---

## 🗄️ Database

Il database è composto da **19 tabelle** organizzate in:
- Autenticazione & Utenti
- Allenamento Core (Exercises, Programs, Routines, Workouts)
- Tracciamento Progressi (Peso, Foto check)
- Sistema Coach-Cliente (Macronutrienti, Questionari)
- Comunicazione (Chat)
- Calendario (Appointments, Availability, Reminders)

Vedi [database-schema.md](./docs/database-schema.md) per diagramma ER completo e query ottimizzate.

---

## 🚀 Getting Started

### Prerequisiti
- Node.js >= 18
- PostgreSQL >= 14
- Redis (opzionale per development)
- React Native CLI o Expo
- Account Stripe (per abbonamenti)

### Setup (Coming Soon)
```bash
# Clone repository
git clone https://github.com/DiegoStefanini/moov.git
cd moov

# Install dependencies
# (TBD: mobile app e backend setup)
```

---

## 📊 Metriche di Successo

### Utenti FREE
- Daily Active Users (DAU)
- Retention D1, D7, D30
- Allenamenti completati/utente/settimana

### Coach PRO
- Tasso conversione FREE → PRO
- Churn rate abbonamenti
- MRR (Monthly Recurring Revenue)
- Numero medio clienti per coach

---

## 🤝 Contribuire

Questo progetto è attualmente in fase di sviluppo iniziale.

---

## 📝 License

TBD

---

## 📧 Contatti

Per domande o informazioni: [TBD]

---

**Made with 💪 in Italy**
