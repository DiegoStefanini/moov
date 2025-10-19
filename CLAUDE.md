# 🤖 CLAUDE.md

Documentazione per Claude Code per assistere nello sviluppo di MOOV.

---

## 📋 Contesto Progetto

**MOOV** è un'app mobile per il tracciamento allenamenti e gestione clienti per personal trainer.

### Stack Tecnologico
- **Frontend**: React Native + TypeScript
- **Backend**: Node.js + Express/NestJS + TypeScript
- **Database**: PostgreSQL
- **Storage**: AWS S3 / Cloudflare R2
- **Real-time**: Socket.io (chat)
- **Pagamenti**: Stripe
- **Notifiche**: Firebase Cloud Messaging

---

## 📂 Struttura Documentazione

Tutta la documentazione è in `/docs`:

1. **obiettivo.md** - Visione del prodotto, problema/soluzione
2. **flussi.md** - Flussi utente dettagliati (FREE e COACH)
3. **funzionalita.md** - Specifiche complete di tutte le features
4. **documentazione.md** - Architettura tecnica, API endpoints, stack
5. **priorita-sviluppo.md** - Roadmap esecutiva settimana per settimana
6. **database-schema.md** - Schema ER completo con query ottimizzate

**IMPORTANTE**: Prima di implementare qualsiasi feature, leggi la documentazione relativa per capire il contesto completo.

---

## 🎯 Principi di Sviluppo

### 1. Seguire la Roadmap
- Rispetta le priorità definite in `priorita-sviluppo.md`
- MVP prima (Fase 1), poi monetizzazione (Fase 2), poi features avanzate (Fase 3)
- Non implementare features Fase 4 fino a completamento Fase 3

### 2. Type Safety First
- **Tutto in TypeScript**: backend e frontend
- Definire interfaces/types PRIMA di implementare
- No `any` types, usare `unknown` se necessario
- Validazione runtime con Zod o Yup

### 3. Database
- Seguire schema in `database-schema.md`
- Usare Prisma come ORM (raccomandato) o TypeORM
- Ogni query deve avere indici appropriati
- Migrations versionati

### 4. API Design
- RESTful endpoints come definiti in `documentazione.md`
- Validazione input con middleware
- Error handling consistente
- Response format standard:
```typescript
{
  success: boolean;
  data?: any;
  error?: {
    code: string;
    message: string;
  };
}
```

### 5. Security
- JWT per autenticazione (access + refresh token)
- Middleware autorizzazione per ogni endpoint protetto
- Coach può accedere SOLO ai dati dei propri clienti
- Sanitizzazione input
- Rate limiting su endpoints critici

### 6. Mobile UI/UX
- Design mobile-first
- Seguire Human Interface Guidelines (iOS) e Material Design (Android)
- Lingua italiana di default
- Dark mode supportato
- Accessibility (screen reader, contrast)

---

## 🏗️ Struttura Progetto (Proposta)

```
moov/
├── docs/                    # Tutta la documentazione
├── mobile/                  # React Native app
│   ├── src/
│   │   ├── components/      # Componenti riutilizzabili
│   │   ├── screens/         # Schermate app
│   │   ├── navigation/      # React Navigation setup
│   │   ├── store/           # Redux/Zustand state
│   │   ├── services/        # API calls
│   │   ├── hooks/           # Custom hooks
│   │   ├── types/           # TypeScript types
│   │   ├── utils/           # Helper functions
│   │   └── theme/           # Colori, font, spacing
│   ├── ios/
│   ├── android/
│   └── package.json
├── backend/                 # Node.js API
│   ├── src/
│   │   ├── routes/          # Express routes
│   │   ├── controllers/     # Business logic
│   │   ├── services/        # Servizi (email, storage, etc)
│   │   ├── middleware/      # Auth, validation, error handling
│   │   ├── models/          # Prisma models / TypeORM entities
│   │   ├── types/           # TypeScript types
│   │   └── utils/           # Helper functions
│   ├── prisma/              # Prisma schema + migrations
│   ├── tests/               # Unit + integration tests
│   └── package.json
├── shared/                  # Codice condiviso (types, utils)
│   └── types/               # Types condivisi frontend/backend
├── .gitignore
├── README.md
└── CLAUDE.md               # Questo file
```

---

## 🚀 Workflow Sviluppo

### Per ogni nuova feature:

1. **Leggi documentazione**
   - Consulta `flussi.md` per capire il flusso utente
   - Leggi `funzionalita.md` per dettagli feature
   - Controlla `database-schema.md` per struttura dati

2. **Design API (se backend)**
   - Verifica endpoint in `documentazione.md`
   - Definisci request/response types
   - Pianifica validazioni e error handling

3. **Design UI/UX (se frontend)**
   - Se esistono wireframe, seguili
   - Altrimenti proponi design basato su best practices
   - Usa componenti UI library (React Native Paper)

4. **Implementa**
   - Scrivi types PRIMA del codice
   - Backend: controller → service → repository
   - Frontend: screen → components → state
   - Commenta codice complesso

5. **Test**
   - Unit test per business logic
   - Integration test per API
   - Manual test per UI

6. **Commit & Push**
   - Commit messages descrittivi
   - Reference issue/task se applicabile

---

## 📱 Schermate Prioritarie MVP (Fase 1)

### Auth Flow
1. **Splash Screen**
2. **Login**
3. **Registrazione**

### Main App (Utenti FREE)
4. **Home** - Dashboard + CTA "Inizia Allenamento"
5. **Esercizi** - Lista + Crea/Modifica esercizio
6. **Schede** - Lista schede (programs)
7. **Routine** - Crea/Modifica routine (con esercizi)
8. **Allenamento Live** - Tracciamento real-time
9. **Storico** - Lista allenamenti passati
10. **Dettaglio Allenamento** - Riepilogo completo
11. **Progressi** - Grafici + Peso corporeo + Foto check
12. **Profilo** - Impostazioni + CTA "Diventa Coach"

---

## 🎨 Design System (Da definire con wireframe)

### Colori (Placeholder)
```typescript
const colors = {
  primary: '#FF6B35',      // Arancione energico
  secondary: '#004E89',    // Blu scuro
  success: '#28A745',      // Verde
  warning: '#FFC107',      // Giallo
  danger: '#DC3545',       // Rosso

  background: {
    light: '#FFFFFF',
    dark: '#121212',
  },

  text: {
    primary: '#212529',
    secondary: '#6C757D',
    inverse: '#FFFFFF',
  },

  border: '#DEE2E6',
  disabled: '#ADB5BD',
};
```

### Typography (Placeholder)
```typescript
const typography = {
  h1: { fontSize: 32, fontWeight: 'bold' },
  h2: { fontSize: 24, fontWeight: 'bold' },
  h3: { fontSize: 20, fontWeight: '600' },
  body: { fontSize: 16, fontWeight: 'normal' },
  caption: { fontSize: 14, fontWeight: 'normal' },
  small: { fontSize: 12, fontWeight: 'normal' },
};
```

### Spacing
```typescript
const spacing = {
  xs: 4,
  sm: 8,
  md: 16,
  lg: 24,
  xl: 32,
  xxl: 48,
};
```

**NOTA**: Questi valori sono placeholder. Aggiornare con design system definitivo da wireframe.

---

## 🔑 Convenzioni Codice

### Naming
- **Components**: PascalCase (`WorkoutCard`, `ExerciseList`)
- **Files**: kebab-case (`workout-card.tsx`, `use-auth.ts`)
- **Functions/Variables**: camelCase (`getUserById`, `isLoading`)
- **Constants**: UPPER_SNAKE_CASE (`MAX_UPLOAD_SIZE`, `API_BASE_URL`)
- **Interfaces/Types**: PascalCase con `I` prefix opzionale (`User`, `IWorkout`)

### File Organization
- Un componente per file
- Export named per utilities, default per components
- Index files per barrel exports

### Comments
- JSDoc per funzioni pubbliche
- Inline comments per logica complessa
- TODO comments con issue reference

---

## 🧪 Testing Strategy

### Backend
- **Unit tests**: Business logic, utils
- **Integration tests**: API endpoints
- **Tool**: Jest + Supertest

### Frontend
- **Component tests**: React Testing Library
- **E2E tests** (Fase 2+): Detox / Maestro
- **Tool**: Jest + React Native Testing Library

### Coverage Target
- Backend: >70%
- Frontend: >60%

---

## 📊 Metriche & Monitoring

### Development
- **Sentry**: Error tracking
- **LogRocket** (opzionale): Session replay
- **Analytics**: Mixpanel / Amplitude

### Logs
- Structured logging (Winston)
- Log levels: error, warn, info, debug
- No sensitive data in logs

---

## 🔄 Git Workflow

### Branches
- `main` - Production
- `develop` - Development
- `feature/nome-feature` - Feature branches
- `fix/nome-fix` - Bug fixes

### Commits
Format: `type(scope): message`

Types:
- `feat`: Nuova feature
- `fix`: Bug fix
- `docs`: Documentazione
- `style`: Formatting
- `refactor`: Code refactoring
- `test`: Aggiunta test
- `chore`: Maintenance

Esempio:
```
feat(auth): implement JWT authentication
fix(workout): correct timer countdown bug
docs(readme): update installation instructions
```

---

## 🚨 Decisioni Architetturali Importanti

### 1. React Native vs Flutter
**Scelta**: React Native
- Ecosistema più maturo
- Hiring developers più facile
- Migliore integrazione con web (future)

### 2. ORM
**Scelta**: Prisma (raccomandato)
- Type-safe
- Migrations automatiche
- Excellent DX
- Alternativa: TypeORM

### 3. State Management
**Scelta**: Redux Toolkit o Zustand
- Redux Toolkit: se app complessa, devtools
- Zustand: se app semplice, meno boilerplate

### 4. Backend Hosting
**Scelta**: Railway (MVP) → AWS (Scale)
- Railway: deployment veloce, buon DX
- Migrate ad AWS quando >10k utenti

### 5. Storage
**Scelta**: Cloudflare R2
- Più economico di S3
- Zero egress costs
- S3-compatible API

---

## 📖 Risorse Utili

### React Native
- [Documentazione ufficiale](https://reactnative.dev/docs/getting-started)
- [React Navigation](https://reactnavigation.org/)
- [React Native Paper](https://callstack.github.io/react-native-paper/)

### Backend
- [Prisma Docs](https://www.prisma.io/docs)
- [NestJS Docs](https://docs.nestjs.com/) (se usato)
- [Express Best Practices](https://expressjs.com/en/advanced/best-practice-security.html)

### Database
- [PostgreSQL Docs](https://www.postgresql.org/docs/)
- [Database Indexing](https://use-the-index-luke.com/)

### Stripe
- [Stripe Docs](https://stripe.com/docs)
- [Subscriptions Guide](https://stripe.com/docs/billing/subscriptions/overview)

---

## 🎯 Quick Reference: Feature Status

### ✅ Da Implementare - Fase 1 (Settimane 1-14)
- [ ] Auth (login, register, JWT)
- [ ] Esercizi CRUD
- [ ] Schede (Programs) CRUD
- [ ] Routine CRUD
- [ ] Allenamento live tracking
- [ ] Storico allenamenti
- [ ] Grafici progressi base
- [ ] Peso corporeo tracking
- [ ] Foto check upload

### ⏳ Da Implementare - Fase 2 (Settimane 15-27)
- [ ] Sistema coach-cliente
- [ ] Stripe integration
- [ ] Questionari coach
- [ ] Chat real-time
- [ ] Notifiche push
- [ ] Macronutrienti
- [ ] Dashboard coach

### 🔮 Future - Fase 3+ (Settimane 28+)
- [ ] Calendario prenotazioni
- [ ] Video upload serie
- [ ] Export dati
- [ ] Wearables integration

---

## 💡 Tips per Claude Code

### Quando implementi una feature:
1. **Chiedi sempre** se non sei sicuro del design/architettura
2. **Riferisci** sempre alla documentazione in `/docs`
3. **Proponi** miglioramenti se vedi opportunità
4. **Segnala** possibili problemi o edge cases
5. **Scrivi codice pulito** e ben commentato

### Quando visualizzi wireframe:
1. Analizza layout, spacing, componenti
2. Identifica componenti riutilizzabili
3. Proponi struttura componenti React
4. Chiedi chiarimenti su interazioni/animazioni
5. Suggerisci miglioramenti UX se appropriato

### Priorità:
1. **Functionality** > Perfection
2. **MVP velocity** > Over-engineering
3. **Type safety** > Dynamic code
4. **User experience** > Feature richness
5. **Code quality** > Speed (ma balance)

---

## 📝 Checklist Pre-Release

### MVP (Fase 1)
- [ ] Tutti i test passano
- [ ] No console errors/warnings
- [ ] Performance accettabile (60fps su device medio)
- [ ] Auth flow completo funzionante
- [ ] Database migrations testate
- [ ] API endpoints documentati
- [ ] Error handling robusto
- [ ] Alpha test con 10+ utenti
- [ ] Privacy policy e Terms of Service
- [ ] App store assets (screenshots, description)

---

## 🆘 Troubleshooting Comuni

### React Native
- **Metro bundler stuck**: `npx react-native start --reset-cache`
- **iOS build fail**: `cd ios && pod install && cd ..`
- **Android build fail**: `cd android && ./gradlew clean && cd ..`

### Database
- **Migration fail**: Controllare schema conflicts, rollback e riapplica
- **Slow queries**: Verificare indici in `database-schema.md`

### Git
- **Merge conflicts**: Comunicare con team, risolvere manualmente
- **Large files**: Usare Git LFS per video/immagini grandi

---

## 🎓 Apprendimento Continuo

Durante lo sviluppo:
- Documenta decisioni architetturali importanti
- Aggiorna CLAUDE.md con nuove convenzioni
- Rifattorizza codice legacy quando possibile
- Monitora performance e ottimizza bottleneck
- Raccogli feedback utenti e itera

---

**Ultimo aggiornamento**: 2025-01-20
**Versione**: 1.0.0 (Pre-MVP)
