# Privacy Policy — vsmart IDE

**Ultimo aggiornamento / Last Updated:** 11 Novembre 2026 / November 11, 2026  
**Titolare del Trattamento / Data Controller:** Fabio del Bolgia  
**Contatto / Contact:** fabiodelbolgia@gmail.com  
**Applicazione / Application:** vsmart IDE (`dev.vsmart.ide`)

---

## 🇮🇹 Versione Italiana

### 1. Architettura "Local-First" e Zero Raccolta Dati Centralizzata
**vsmart IDE** è un ambiente di sviluppo mobile progettato con un'architettura **completamente locale e privata (Local-First)**:
- **Nessun Server Proprietario:** Lo sviluppatore di vsmart IDE non possiede, non gestisce e non utilizza server centrali, database cloud o backend intermedi per raccogliere, analizzare, conservare o profilare i tuoi dati.
- **Nessun Tracciamento o Pubblicità:** L'applicazione non include librerie di telemetria, cookie, tracker pubblicitari o strumenti di profilazione commerciale (zero Google Analytics, zero Firebase Analytics, zero Facebook SDK).
- **Archiviazione Locale:** Tutti i tuoi file, repository di codice, cronologia delle chat e impostazioni risiedono esclusivamente nella memoria interna isolata della sandbox del tuo dispositivo Android (`context.filesDir`).

### 2. Gestione dei Segreti e Modello BYOK (Bring Your Own Key)
L'applicazione adotta il modello **BYOK**:
- Le chiavi API dei modelli di intelligenza artificiale (Google Gemini, OpenAI, Anthropic, ecc.), i Personal Access Token di GitHub e le chiavi private SSH (.pem / OpenSSH) vengono fornite direttamente dall'utente.
- **Crittografia Hardware:** Tutti i segreti inseriti vengono memorizzati localmente tramite l'Android Keystore nativo con algoritmo **AES-256-GCM** hardware-backed (`EncryptedSharedPreferences`).
- Tali chiavi non vengono mai trasmesse allo sviluppatore di vsmart IDE né a soggetti terzi diversi dai fornitori dei servizi espressamente configurati dall'utente.

### 3. Connessioni a Servizi Terzi Configurati dall'Utente
Quando l'utente utilizza le funzionalità connesse, il dispositivo stabilisce comunicazioni dirette end-to-end con i servizi terzi scelti dall'utente:
- **Provider LLM (Google Gemini, OpenAI, Anthropic):** Le richieste di prompt e il codice inviato per l'analisi transitano direttamente dal tuo smartphone ai server HTTPS del provider selezionato utilizzando la tua chiave API personale. Il trattamento di tali dati è regolato dalle rispettive Privacy Policy dei fornitori.
- **GitHub:** Le operazioni Git (clone, pull, push, creazione PR) comunicano direttamente con i server di GitHub tramite protocollo crittografato HTTPS o SSH con il tuo token o chiave personale.
- **Server Remoto SSH:** Le connessioni terminale o di deploy comunicano direttamente dal tuo telefono all'indirizzo IP del tuo server cloud o server privato tramite protocollo crittografato SSH (porta 22 o custom). Nessun dato transita per intermediari.

### 4. Permessi Dispositivo Richiesti e Giustificazione
- **Internet (`INTERNET`, `ACCESS_NETWORK_STATE`):** Necessario per inviare chiamate API ai provider IA scelti dall'utente, eseguire operazioni Git remote e connettersi via SSH.
- **Microfono (`RECORD_AUDIO`):** Utilizzato **esclusivamente** per consentire l'inserimento vocale dei messaggi in chat tramite il componente nativo Android `SpeechRecognizer`. L'audio viene elaborato in tempo reale per la trascrizione e **non viene mai registrato, memorizzato o inviato a server dello sviluppatore**.
- **Servizio in Primo Piano (`FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_DATA_SYNC`):** Utilizzato per garantire che operazioni lunghe di sincronizzazione Git, refactoring multi-step dell'agente IA o deploy SSH non vengano terminate dal sistema operativo se l'utente cambia applicazione.
- **Notifiche (`POST_NOTIFICATIONS`):** Utilizzato per mostrare lo stato di avanzamento delle attività in background e consentirne l'arresto.

### 5. Diritti dell'Utente e Cancellazione Dati
Poiché nessun dato personale è memorizzato su server esterni dello sviluppatore, l'utente ha il pieno controllo assoluto sui propri dati:
- La cancellazione di un workspace, di una chiave dal Vault o la disinstallazione dell'applicazione comporta la **cancellazione immediata, permanente e irreversibile** di tutti i file e segreti dal dispositivo.

---

## 🇬🇧 English Version

### 1. Local-First Architecture & Zero Central Data Collection
**vsmart IDE** is a mobile developer environment engineered with a **strictly local-first, private architecture**:
- **No Proprietary Servers:** The developer of vsmart IDE does not own, operate, or maintain any central servers, cloud databases, or relay backends to collect, store, analyze, or profile user data.
- **Zero Tracking & Advertising:** The app contains no third-party telemetry SDKs, advertising trackers, or user behavioral analytics.
- **Local Sandbox Storage:** All source code, project files, chat history, and configurations are stored exclusively in your Android device's private sandboxed directory (`context.filesDir`).

### 2. Bring Your Own Key (BYOK) & Secret Vault
- AI API keys (Google Gemini, OpenAI, Anthropic), GitHub Personal Access Tokens, and SSH private keys are entered directly by the user.
- **Hardware-Backed Encryption:** Secrets are stored locally in the Android Keystore using **AES-256-GCM** (`EncryptedSharedPreferences`).
- Secrets are never transmitted to the app developer or any unauthorized entity.

### 3. Direct Third-Party Communications
When network features are invoked, encrypted connections are made directly from your phone to the respective endpoints:
- **LLM Providers:** Prompts and code are sent directly via HTTPS to the provider configured with your API key.
- **GitHub:** Git sync operations communicate directly with GitHub servers.
- **SSH Servers:** Terminal sessions and deployment tasks connect directly to your specified host IP over encrypted SSH.

### 4. Device Permissions Justification
- **Internet:** Required to reach user-configured APIs, Git remotes, and SSH servers.
- **Microphone (`RECORD_AUDIO`):** Used solely for speech-to-text prompt input using the on-device Android SpeechRecognizer. Audio is processed transiently and **never recorded, stored, or uploaded**.
- **Foreground Service (`FOREGROUND_SERVICE_DATA_SYNC`):** Keeps long-running Git clones/pushes, AI turns, and SSH deployments active when switching apps.
- **Notifications:** Displays progress status for active background tasks.

### 5. Contact
For any questions regarding this Privacy Policy, contact: **Fabio del Bolgia** (`fabiodelbolgia@gmail.com`).
