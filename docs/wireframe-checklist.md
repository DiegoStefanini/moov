# 🎨 Wireframe Checklist - MOOV

Checklist prioritizzata delle schermate da wireframare per MOOV, organizzate per priorità e fase di sviluppo.

---

## 🚨 Priorità CRITICA - Da fare subito

Queste schermate sono il **cuore dell'MVP** e devono essere wireframate per prime. Senza queste, l'app non funziona.

### 1. Auth Flow (3 schermate)

#### ✅ 1.1 Splash Screen
- [ ] Logo centrato
- [ ] Loading indicator
- [ ] Versione app (footer)

**Note**: Schermata mostrata all'avvio mentre verifica autenticazione.

---

#### ✅ 1.2 Login
- [ ] Campo email
- [ ] Campo password
- [ ] Pulsante "Accedi"
- [ ] Link "Password dimenticata?"
- [ ] Link "Non hai un account? Registrati"
- [ ] (Opzionale) Social login (Google, Apple)

**Note**: Semplice, pulita, mobile-first.

---

#### ✅ 1.3 Registrazione
- [ ] Campo nome
- [ ] Campo email
- [ ] Campo password
- [ ] Campo conferma password
- [ ] Checkbox "Accetto termini e condizioni"
- [ ] Pulsante "Registrati"
- [ ] Link "Hai già un account? Accedi"

**Note**: Form validation inline (mostra errori sotto ai campi).

---

### 2. Home & Navigazione (2 schermate)

#### ✅ 2.1 Home - Dashboard Utente FREE
- [ ] Header con nome utente e foto profilo
- [ ] CTA grande "Inizia Allenamento" (primary button)
- [ ] Sezione "Statistiche Rapide":
  - [ ] Ultimo allenamento (data + nome routine)
  - [ ] Streak giorni consecutivi
  - [ ] Allenamenti questo mese
- [ ] Sezione "Routine Recenti" (lista 3-4 routine usate di recente)
- [ ] Bottom navigation bar (Home, Routine, Progressi, Profilo)

**Note**: Dashboard motivazionale, deve invogliare a iniziare allenamento.

---

#### ✅ 2.2 Bottom Navigation Bar
- [ ] Tab "Home" (icona casa)
- [ ] Tab "Routine" (icona lista/clipboard)
- [ ] Tab "Progressi" (icona grafico)
- [ ] Tab "Profilo" (icona utente)
- [ ] Active state visibile
- [ ] Badge notifiche (se presenti)

**Note**: Sempre visibile, design minimale.

---

### 3. Allenamento Core (4 schermate)

#### ✅ 3.1 Schermata "Inizia Allenamento"
- [ ] Header "Inizia Allenamento"
- [ ] Lista routine disponibili (cards scrollabili):
  - [ ] Nome routine
  - [ ] Numero esercizi
  - [ ] Durata stimata
  - [ ] Ultimo utilizzo
- [ ] Opzione "Allenamento Libero" (senza routine)
- [ ] Filtri/ricerca routine (opzionale)

**Note**: L'utente seleziona quale routine seguire.

---

#### ✅ 3.2 Allenamento Live - Durante
**LA SCHERMATA PIÙ IMPORTANTE DELL'APP**

- [ ] **Header**:
  - [ ] Timer totale allenamento (MM:SS)
  - [ ] Pulsante pausa
  - [ ] Pulsante chiudi (con conferma)

- [ ] **Esercizio Corrente (Card grande)**:
  - [ ] Nome esercizio
  - [ ] Serie target (es. "Serie 1 di 4")
  - [ ] Reps target (es. "8-10 reps")
  - [ ] **Peso precedente ben visibile** (es. "Ultima volta: 80kg x 8")
  - [ ] Input peso (tastierino numerico)
  - [ ] Input ripetizioni (tastierino numerico)
  - [ ] Pulsante "Completa Serie" (grande, verde)

- [ ] **Timer Riposo** (dopo serie completata):
  - [ ] Countdown circolare (es. 60s, 59s, 58s...)
  - [ ] Pulsante "Salta riposo"
  - [ ] Pulsante +15s / -15s per aggiustare

- [ ] **Serie Completate** (sotto card corrente):
  - [ ] Lista serie già fatte con pesi e reps
  - [ ] Checkbox verdi

- [ ] **Prossimi Esercizi** (preview minima):
  - [ ] Lista scrollabile dei prossimi 2-3 esercizi

- [ ] **Bottom Actions**:
  - [ ] Pulsante "Note" (aggiungi nota rapida)
  - [ ] Pulsante "Video" (registra/carica video serie)
  - [ ] Progress bar (es. "3/10 esercizi completati")

- [ ] **Fine Allenamento**:
  - [ ] Pulsante "Completa Allenamento"

**Note**: Questa è la schermata dove l'utente passa la maggior parte del tempo. Deve essere CHIARISSIMA, con input facili e veloci. Il peso precedente deve essere MOLTO visibile.

---

#### ✅ 3.3 Riepilogo Allenamento
- [ ] Header "Allenamento Completato!" (con emoji 💪)
- [ ] Durata totale
- [ ] Esercizi completati
- [ ] Serie totali
- [ ] Volume totale sollevato
- [ ] Lista esercizi con dettaglio serie/peso/reps
- [ ] Campo note allenamento
- [ ] Pulsanti:
  - [ ] "Salva e Chiudi"
  - [ ] "Ripeti questo allenamento"

**Note**: Schermata di successo, dare feedback positivo.

---

#### ✅ 3.4 Storico Allenamenti
- [ ] Header "Storico"
- [ ] Lista allenamenti (cards cronologiche):
  - [ ] Data e ora
  - [ ] Nome routine (se usata)
  - [ ] Durata
  - [ ] Numero esercizi
  - [ ] Preview esercizi principali
- [ ] Filtri:
  - [ ] Periodo (ultima settimana, mese, anno)
  - [ ] Routine specifica
- [ ] Tap su allenamento → Dettaglio completo

**Note**: Vista calendario opzionale (heatmap GitHub-style).

---

### 4. Routine & Esercizi (3 schermate)

#### ✅ 4.1 Lista Esercizi
- [ ] Header "Esercizi"
- [ ] Pulsante FAB "+" (floating action button) per creare
- [ ] Lista esercizi (cards):
  - [ ] Nome esercizio
  - [ ] Tipo (forza/cardio/flessibilità)
  - [ ] Tag monolaterale (se applicabile)
  - [ ] Note brevi
- [ ] Search bar
- [ ] Swipe per eliminare
- [ ] Tap per modificare

**Note**: Semplice lista, focus su creazione rapida.

---

#### ✅ 4.2 Crea/Modifica Esercizio
- [ ] Header "Nuovo Esercizio" / "Modifica Esercizio"
- [ ] Campo nome esercizio
- [ ] Dropdown tipo esercizio (Forza, Cardio, Flessibilità)
- [ ] Toggle "Esercizio monolaterale"
- [ ] Campo note (multiline)
- [ ] Pulsanti:
  - [ ] "Salva"
  - [ ] "Annulla"

**Note**: Form semplice, 4-5 campi max.

---

#### ✅ 4.3 Lista Routine
- [ ] Header "Routine"
- [ ] Tabs:
  - [ ] "Le mie routine"
  - [ ] "Schede" (programs)
- [ ] Lista routine (cards espandibili):
  - [ ] Nome routine
  - [ ] Numero esercizi
  - [ ] Durata stimata
  - [ ] Preview esercizi (primi 3)
  - [ ] Badge "Scheda: PPL" (se parte di scheda)
- [ ] Pulsante FAB "+" per creare
- [ ] Swipe/menu per:
  - [ ] Modifica
  - [ ] Archivia
  - [ ] Elimina

**Note**: Le schede sono gruppi di routine (es. PPL = 3 routine).

---

#### ✅ 4.4 Crea/Modifica Routine
- [ ] Header "Nuova Routine" / "Modifica Routine"
- [ ] Campo nome routine
- [ ] Dropdown "Scheda" (opzionale, seleziona program)
- [ ] Lista esercizi aggiunti:
  - [ ] Nome esercizio
  - [ ] Serie target (input number)
  - [ ] Reps min-max (input range, es. 8-10)
  - [ ] Riposo (secondi, input number)
  - [ ] Drag handle per riordinare
  - [ ] Pulsante rimuovi
- [ ] Pulsante "Aggiungi Esercizio":
  - [ ] Mostra modal/lista esercizi esistenti
  - [ ] Possibilità creare nuovo al volo
- [ ] Pulsanti:
  - [ ] "Salva Routine"
  - [ ] "Annulla"

**Note**: Drag & drop essenziale per riordinare esercizi.

---

### 5. Progressi (2 schermate)

#### ✅ 5.1 Progressi - Overview
- [ ] Header "Progressi"
- [ ] Tabs:
  - [ ] "Allenamenti"
  - [ ] "Peso Corporeo"
  - [ ] "Foto Check"

**Tab Allenamenti**:
- [ ] Selettore periodo (7gg, 30gg, 90gg, anno)
- [ ] Grafico frequenza allenamenti (bar chart)
- [ ] Sezione "Progressi per Esercizio":
  - [ ] Dropdown seleziona esercizio
  - [ ] Grafico peso nel tempo (line chart)
  - [ ] Lista Personal Records

**Tab Peso Corporeo**:
- [ ] Pulsante "Registra Peso"
- [ ] Grafico peso corporeo (line chart)
- [ ] Lista registrazioni peso (data + kg)

**Tab Foto Check**:
- [ ] Pulsante "Carica Foto"
- [ ] Galleria foto cronologica (grid)
- [ ] Tap su foto → fullscreen con data

**Note**: Grafici devono essere chiari e interattivi (zoom, pan).

---

#### ✅ 5.2 Dettaglio Progressi Esercizio
- [ ] Header con nome esercizio
- [ ] Selettore periodo
- [ ] Grafico principale:
  - [ ] Peso massimo nel tempo (line chart)
  - [ ] Punti dati cliccabili
- [ ] Metriche:
  - [ ] PR attuale
  - [ ] Incremento % ultimo mese
  - [ ] Volume totale
- [ ] Lista allenamenti dove esercizio è stato fatto:
  - [ ] Data
  - [ ] Serie x Reps x Peso
  - [ ] Note
- [ ] Pulsante "Esporta Dati" (CSV/PDF)

**Note**: Focus su visualizzazione chiara progressione.

---

### 6. Profilo (1 schermata)

#### ✅ 6.1 Profilo Utente FREE
- [ ] Header con foto profilo (editabile)
- [ ] Nome utente (editabile)
- [ ] Email
- [ ] **CTA "Diventa Coach PRO"** (banner grande, colorato)

- [ ] Sezioni Settings:
  - [ ] **Account**:
    - [ ] Modifica profilo
    - [ ] Cambia password
  - [ ] **Preferenze**:
    - [ ] Unità di misura (kg/lbs)
    - [ ] Dark mode toggle
    - [ ] Lingua (IT, EN)
  - [ ] **Notifiche**:
    - [ ] Promemoria allenamenti
    - [ ] Nuovi PR
    - [ ] Streak
  - [ ] **Dati**:
    - [ ] Esporta dati
    - [ ] Elimina account
  - [ ] **Altro**:
    - [ ] Privacy policy
    - [ ] Termini di servizio
    - [ ] Versione app
    - [ ] Logout

**Note**: CTA "Diventa Coach" deve essere molto visibile.

---

## 🔶 Priorità ALTA - Dopo le critiche

Queste servono per completare l'MVP ma non bloccano il primo test.

### 7. Onboarding (2 schermate)

#### ✅ 7.1 Onboarding Tutorial (3-4 slides)
- [ ] Slide 1: "Benvenuto in MOOV" + illustrazione
- [ ] Slide 2: "Traccia i tuoi allenamenti" + screenshot
- [ ] Slide 3: "Vedi i tuoi progressi" + grafici
- [ ] Slide 4 (opzionale): "Diventa Coach PRO" + features
- [ ] Pulsanti navigazione (Avanti, Indietro, Salta)

**Note**: Solo al primo avvio, dopo registrazione.

---

#### ✅ 7.2 Setup Profilo Iniziale
- [ ] Header "Completa il tuo profilo"
- [ ] Upload foto profilo
- [ ] Campo nome
- [ ] (Opzionale) Selezione obiettivi (forza, ipertrofia, resistenza)
- [ ] Pulsante "Inizia"

**Note**: Step opzionale post-registrazione.

---

### 8. Ricerca & Filtri (1 schermata)

#### ✅ 8.1 Ricerca Globale
- [ ] Search bar
- [ ] Risultati categorizzati:
  - [ ] Esercizi
  - [ ] Routine
  - [ ] Allenamenti passati
- [ ] Filtri rapidi
- [ ] Recent searches

**Note**: Aiuta navigazione rapida.

---

## 🔵 Priorità MEDIA - Fase 2 (Coach)

Queste schermate sono per la **Fase 2 - Coach PRO**. Non servono per l'MVP utenti FREE.

### 9. Coach - Gestione Clienti (5 schermate)

#### ⏳ 9.1 Dashboard Coach
- [ ] Header con nome coach
- [ ] Overview:
  - [ ] Numero clienti attivi
  - [ ] Allenamenti completati oggi
  - [ ] Messaggi non letti
  - [ ] Prossimi appuntamenti
- [ ] Lista clienti (cards):
  - [ ] Foto, nome
  - [ ] Status attività (verde/giallo/rosso)
  - [ ] Ultimo allenamento
  - [ ] Pulsanti rapidi (chat, profilo)
- [ ] Pulsante FAB "Invita Cliente"

**Note**: Sostituisce Home quando utente è coach.

---

#### ⏳ 9.2 Profilo Cliente (Coach view)
- [ ] Header con nome cliente e foto
- [ ] Tabs:
  - [ ] **Overview**:
    - [ ] Info base (email, telefono, data inizio)
    - [ ] Obiettivi
    - [ ] Note coach (private)
    - [ ] Risposte questionario
  - [ ] **Allenamenti**:
    - [ ] Storico allenamenti cliente
    - [ ] Grafici progressi
    - [ ] Possibilità vedere video serie
  - [ ] **Routine**:
    - [ ] Routine assegnate
    - [ ] Pulsante "Assegna Routine"
    - [ ] Pulsante "Crea Nuova"
  - [ ] **Macro**:
    - [ ] Macro attuali
    - [ ] Pulsante "Modifica Macro"
    - [ ] Grafico comparabile macro/peso
  - [ ] **Check Fisico**:
    - [ ] Grafico peso corporeo
    - [ ] Galleria foto check cliente
  - [ ] **Chat**:
    - [ ] Conversazione diretta

**Note**: Schermata complessa, molto contenuto.

---

#### ⏳ 9.3 Assegna Macro
- [ ] Header "Assegna Macronutrienti - [Nome Cliente]"
- [ ] Input Proteine (g)
- [ ] Input Carboidrati (g)
- [ ] Input Grassi (g)
- [ ] Input Calorie totali (calcolate automaticamente)
- [ ] Campo note/istruzioni dietetiche
- [ ] Data inizio validità (default: oggi)
- [ ] Pulsante "Salva e Notifica Cliente"

**Note**: Form semplice, calcolo calorie automatico.

---

#### ⏳ 9.4 Invita Cliente
- [ ] Header "Invita Nuovo Cliente"
- [ ] Opzione 1: Invito via email
  - [ ] Input email
  - [ ] Preview email
  - [ ] Pulsante "Invia Invito"
- [ ] Opzione 2: Link condivisibile
  - [ ] Genera link univoco
  - [ ] Pulsanti condivisione (WhatsApp, Telegram, Copia)
- [ ] Lista inviti pendenti

**Note**: Semplice, focus su condivisione rapida.

---

#### ⏳ 9.5 Crea Questionario (Coach)
- [ ] Header "Questionario Onboarding"
- [ ] Toggle "Imposta come default"
- [ ] Lista domande (drag & drop per ordinare):
  - [ ] Testo domanda
  - [ ] Tipo (testo libero, multipla, si/no)
  - [ ] Flag "obbligatoria"
  - [ ] Pulsante elimina
- [ ] Pulsante "Aggiungi Domanda"
- [ ] Pulsanti:
  - [ ] "Salva Questionario"
  - [ ] "Anteprima"

**Note**: Builder domande flessibile.

---

### 10. Chat (2 schermate)

#### ⏳ 10.1 Lista Conversazioni
- [ ] Header "Chat"
- [ ] Lista conversazioni (cards):
  - [ ] Foto e nome contatto
  - [ ] Ultimo messaggio (preview)
  - [ ] Timestamp
  - [ ] Badge messaggi non letti
- [ ] Tap → Apri chat

**Note**: Solo per utenti con coach o coach con clienti.

---

#### ⏳ 10.2 Chat Conversazione
- [ ] Header con nome contatto e foto
- [ ] Messaggi (scrollabile):
  - [ ] Bubbles differenziate (sender/receiver)
  - [ ] Timestamp
  - [ ] Immagini inline
  - [ ] Link cliccabili
  - [ ] Status lettura (✓✓)
- [ ] Input message:
  - [ ] Campo testo
  - [ ] Pulsante allegato (immagine)
  - [ ] Pulsante invio
- [ ] Typing indicator ("sta scrivendo...")

**Note**: Chat standard, real-time con Socket.io.

---

### 11. Abbonamenti (2 schermate)

#### ⏳ 11.1 Diventa Coach - Paywall
- [ ] Header "Diventa Coach PRO"
- [ ] Hero section con benefici:
  - [ ] Clienti illimitati
  - [ ] Chat diretta
  - [ ] Calendario prenotazioni
  - [ ] Dashboard analytics
  - [ ] Gestione macro
- [ ] Piani (cards):
  - [ ] **Mensile**: €29/mese
    - [ ] Fatturato mensilmente
  - [ ] **Annuale**: €290/anno (risparmio)
    - [ ] Fatturato annualmente
    - [ ] Badge "Risparmia €58/anno"
- [ ] Banner "1 mese di prova gratuita"
- [ ] Pulsante "Inizia Trial Gratuito"
- [ ] Link "Termini e condizioni"

**Note**: Design persuasivo, highlight trial gratuito.

---

#### ⏳ 11.2 Gestione Abbonamento
- [ ] Header "Il tuo Abbonamento"
- [ ] Card piano attuale:
  - [ ] Tipo piano (Mensile/Annuale)
  - [ ] Prezzo
  - [ ] Prossimo rinnovo (data)
  - [ ] Stato (Attivo, Trial, Cancellato)
- [ ] Pulsanti:
  - [ ] "Cambia Piano"
  - [ ] "Cancella Abbonamento"
- [ ] Sezione "Fatture":
  - [ ] Lista fatture scaricabili
- [ ] Sezione "Metodi Pagamento":
  - [ ] Carta salvata
  - [ ] Pulsante "Aggiorna Metodo"

**Note**: Integrato con Stripe Customer Portal se possibile.

---

## 🟢 Priorità BASSA - Fase 3+

### 12. Calendario (2 schermate)

#### 🔮 12.1 Calendario Coach
- [ ] Vista calendario (settimana/mese)
- [ ] Slot disponibilità (verde)
- [ ] Appuntamenti confermati (blu)
- [ ] Pulsante "Imposta Disponibilità"
- [ ] Lista appuntamenti giorno selezionato
- [ ] Pulsante "Aggiungi Reminder"

---

#### 🔮 12.2 Prenota Seduta (Cliente view)
- [ ] Calendario con slot disponibili coach
- [ ] Selezione data/ora
- [ ] Tipo seduta (Live, Online, In palestra)
- [ ] Note opzionali
- [ ] Pulsante "Conferma Prenotazione"

---

### 13. Export & Settings Avanzati (2 schermate)

#### 🔮 13.1 Export Dati
- [ ] Selezione periodo
- [ ] Opzioni export:
  - [ ] CSV (storico allenamenti)
  - [ ] PDF (report progressi)
  - [ ] Immagini (grafici)
- [ ] Pulsante "Genera Export"

---

#### 🔮 13.2 Impostazioni Notifiche (Dettaglio)
- [ ] Toggle per ogni tipo notifica:
  - [ ] Promemoria allenamento
  - [ ] Nuovo PR
  - [ ] Streak
  - [ ] Nuovo messaggio
  - [ ] Cliente completa allenamento (coach)
  - [ ] Nuovo cliente (coach)
  - [ ] Seduta prenotata (coach)
- [ ] Quiet hours (da/a)
- [ ] Frequenza promemoria allenamento

---

## 📊 Riepilogo Priorità

### ✅ CRITICA (12 schermate) - Da wireframare SUBITO
1. Splash Screen
2. Login
3. Registrazione
4. Home Dashboard FREE
5. Bottom Nav
6. Inizia Allenamento
7. **Allenamento Live** ⭐ (LA PIÙ IMPORTANTE)
8. Riepilogo Allenamento
9. Storico Allenamenti
10. Lista Esercizi
11. Crea/Modifica Esercizio
12. Lista Routine
13. Crea/Modifica Routine
14. Progressi Overview
15. Dettaglio Progressi Esercizio
16. Profilo FREE

**Totale: ~16 schermate critiche**

---

### 🔶 ALTA (3 schermate) - Dopo critiche
17. Onboarding Tutorial
18. Setup Profilo Iniziale
19. Ricerca Globale

**Totale: ~3 schermate**

---

### 🔵 MEDIA (14 schermate) - Fase 2 Coach
20-34. Tutte le schermate Coach (Dashboard, Clienti, Chat, Abbonamenti, ecc.)

**Totale: ~14 schermate**

---

### 🟢 BASSA (4+ schermate) - Fase 3+
35+. Calendario, Export, Settings avanzati

**Totale: ~4+ schermate**

---

## 🎯 Raccomandazione Workflow

### Week 1: Wireframe Critici Core (6 schermate)
Focus su allenamento flow:
1. Login
2. Home
3. Inizia Allenamento
4. **Allenamento Live** ⭐
5. Riepilogo Allenamento
6. Storico

**Obiettivo**: Validare user flow principale.

---

### Week 2: Wireframe Routine & Esercizi (4 schermate)
7. Lista Esercizi
8. Crea Esercizio
9. Lista Routine
10. Crea Routine

**Obiettivo**: Completare loop creazione → allenamento.

---

### Week 3: Wireframe Progressi & Profilo (4 schermate)
11. Progressi Overview
12. Dettaglio Esercizio
13. Profilo
14. Registrazione

**Obiettivo**: Completare MVP utente FREE.

---

### Week 4+: Wireframe Fase 2 (Coach)
Solo dopo validazione MVP FREE con utenti reali.

---

## 📱 Tool Consigliati per Wireframing

### Opzione 1: Figma (Raccomandato)
- ✅ Gratuito per uso personale
- ✅ Collaborative
- ✅ Mobile frames predefiniti (iPhone, Android)
- ✅ Components riutilizzabili
- ✅ Prototyping interattivo
- 🔗 [figma.com](https://figma.com)

### Opzione 2: Adobe XD
- ✅ Gratuito (plan starter)
- ✅ Mobile frames
- ✅ Prototyping

### Opzione 3: Sketch (Mac only)
- ✅ Industry standard
- ❌ A pagamento

### Opzione 4: Carta & Penna
- ✅ Velocissimo per primi draft
- ✅ Nessuna curva apprendimento
- Poi digitalizza con Figma

---

## 💡 Tips per Wireframing

### Low-Fidelity (Primi Draft)
- Focus su layout e flusso, non colori
- Usa grigi e box placeholder
- Testo lorem ipsum ok
- Velocità > Perfezione

### High-Fidelity (Dopo validazione)
- Aggiungi colori brand
- Font reali
- Icone definitive
- Spacing preciso

### Mobile-First
- Wireframe sempre per mobile (iPhone 14/15 o Pixel)
- 375x812px (iPhone) o 360x800px (Android)
- Pollice-friendly: pulsanti grandi, CTA in basso

### Componenti Riutilizzabili
- Crea components in Figma per:
  - Buttons (primary, secondary, text)
  - Input fields
  - Cards (esercizio, routine, allenamento)
  - Navigation bar
  - Headers

---

## 🎨 Design System Baseline

Quando crei wireframe, pensa a:

### Colori
- [ ] Primary color (brand, CTA)
- [ ] Secondary color
- [ ] Success (verde)
- [ ] Warning (giallo)
- [ ] Danger (rosso)
- [ ] Background (light + dark mode)
- [ ] Text (primary + secondary)

### Typography
- [ ] Heading (H1, H2, H3)
- [ ] Body text
- [ ] Small text
- [ ] Font family (es. Inter, Roboto, Poppins)

### Spacing
- [ ] Grid 8pt (8px, 16px, 24px, 32px, 48px)
- [ ] Padding componenti
- [ ] Margin tra sezioni

### Componenti
- [ ] Buttons (primary, secondary, text, disabled)
- [ ] Input fields (text, number, dropdown)
- [ ] Cards (varie tipologie)
- [ ] Lists
- [ ] Navigation
- [ ] Modals

---

## ✅ Checklist Finale

Quando hai completato wireframe per una schermata:

- [ ] Layout chiaro e organizzato
- [ ] Gerarchia visiva (cosa è più importante?)
- [ ] CTA principale evidente
- [ ] Stati gestiti (loading, error, empty state)
- [ ] Responsive (come si adatta a schermi diversi?)
- [ ] Accessibilità (touch target ≥44x44px)
- [ ] Navigazione chiara (come torno indietro?)

---

**Ready to wireframe!** 🎨

Inizia con le 6 schermate critiche core (Week 1) e condividile con me per feedback e implementazione!
