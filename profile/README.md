# DOLOBOT



Benvenuto nell'organizzazione GitHub ufficiale di **Dolobot**, azienda di robotica avanzata con sede nel cuore delle Dolomiti Bellunesi (Italia). Siamo specializzati nello sviluppo di soluzioni robotiche all'avanguardia progettate per l'esplorazione sicura di ambienti estremi e l'ispezione intelligente delle infrastrutture.

Questa organizzazione funge da hub centrale per il nostro firmware, le piattaforme software, i livelli di integrazione hardware e gli strumenti di intelligenza artificiale che guidano l'ecosistema del rover anfibio **GECO**.

---

## 🚀 Chi siamo & Cos'è GECO

Dolobot unisce professionisti con decenni di esperienza nell'esplorazione di ambienti estremi e nella robotica avanzata. La nostra piattaforma di punta, **GECO**, è un rover robotico anfibio progettato per rivoluzionare l'ispezione di condotte, tubazioni e ambienti sottomarini (operativo fino a 500 metri di profondità).

### Caratteristiche chiave dell'ecosistema GECO:
*   **Operatività Anfibia:** Piena capacità di operare sia in condotte asciutte che in ambienti completamente sommersi fino a 500m.
*   **Controllo Remoto in Tempo Reale:** Massima sicurezza per l'operatore grazie a una gestione remota ad alta fedeltà.
*   **Reportistica Istantanea:** Generazione automatica di report strutturati completi di acquisizione immagini, annotazioni e geolocalizzazione spaziale.
*   **Ispezione ad Alta Risoluzione:** Integrazione di sistemi di zoom ottico 40x per rilevare anomalie strutturali a distanza.
*   **Analisi dei Difetti basata su IA:** Pipeline software di intelligenza artificiale in tempo reale per la classificazione dei difetti e la mappatura dello stato di servizio ("Fitness for Service").
*   **Integrazione Digital Twin:** Monitoraggio del ciclo di vita dell'asset tramite ricostruzione 3D e tracciamento temporale del degrado e della corrosione.

---

## 🗂️ Struttura dell'Organizzazione & Repository Principali

Il nostro flusso di sviluppo è strutturato in diversi moduli chiave, che spaziano dal firmware bare-metal di basso livello fino all'orchestrazione cloud.

### 🔌 1. Firmware (`/firmware`)
Contiene il codice sorgente C/C++ per microcontrollori, responsabile dell'attuazione in tempo reale, della gestione della potenza e dell'acquisizione dei dati sensoriali.
*   **`geco-firmware`**: Firmware core multi-modulo per ESP32 / ESP32-P4 ("Geco_fw"). Gestisce i loop di controllo di basso livello, i driver dei motori e i protocolli seriali.
*   **`pmbus-power-management`**: Implementazione dello stack di comunicazione PMBus/I2C per unità di alimentazione di livello server (es. HP DPS-1200FB, Mean Well UHP-2500) tramite architetture Arduino/ESP32.
*   **`sensor-drivers`**: Driver dedicati per i carichi utili strutturali e ambientali, inclusi il sensore di profondità ad alta pressione `MS5837` e i moduli di rilevamento attivo delle perdite d'acqua.

### 🤖 2. Robotica & Controllo (`/robotics`)
Ospita i framework di autonomia di medio livello, i motori cinematici e le pipeline di localizzazione.
*   **`geco-ros2`**: Workspace ROS 2 (Jazzy Jalisco) che definisce l'URDF del robot, i parametri di simulazione e gli stack di navigazione.
*   **`kinematics-odometry`**: Pacchetti matematici che gestiscono l'odometria skid-steering, la profilazione personalizzata del movimento per robot cingolati e la cinematica inversa.
*   **`visual-inertial-navigation`**: Moduli di stima dello stato che integrano i flussi di profondità delle telecamere stereo con la telemetria dei sensori IMU High-G per la navigazione stimata (dead reckoning) all'interno di condotte chiuse.

### 🧠 3. IA & Digital Twin (`/analytics`)
Ospita le piattaforme di computazione edge e cloud dedicate alla computer vision e all'analisi strutturale.
*   **`defect-detection-ai`**: Modelli di deep learning specializzati nella segmentazione strutturale in tempo reale, nel rilevamento delle crepe e nell'isolamento delle anomalie sui giunti delle condotte.
*   **`digital-twin-pipeline`**: Stack software per la generazione di ricostruzioni interne delle tubazioni, mappatura dello stato dell'asset e analisi predittiva della corrosione nel tempo.

### 🖥️ 4. Tooling & Configurazione (`/tools`)
*   **`development-env`**: Blueprint dell'infrastruttura di progetto standardizzata che sfrutta ambienti Conda/Miniforge environments, tracciamento di AppImage standalone (KiCad, Arduino IDE, strutture di documentazione Obsidian) e script unificati per il flash del firmware.

---

## 🛠️ Stack Tecnologico

Utilizziamo uno stack tecnologico moderno e robusto in tutta la nostra architettura software e hardware:
*   **Linguaggi:** C++, Python, Scripting Shell
*   **Framework:** ROS 2 (Jazzy), PyTorch / TensorFlow (AI Engine)
*   **Ambienti Hardware:** ESP32-P4, Arduino, Linux Embedded (runtime basati su Ubuntu)
*   **Protocolli:** PMBus, I2C, CAN Bus, Custom Network Event Streaming

---

## 👥 Linee Guida Interne & Contributi

L'accesso alle repository di questa organizzazione è gestito in base ai team di progetto (Firmware, Integrazione ROS, Sistemi di Visione).

1. **Strategia di Branching:** Seguiamo un approccio GitFlow modificato. I commit diretti su `main` o `develop` sono protetti. Tutte le modifiche richiedono una Pull Request (PR) e almeno una revisione paritaria (peer review).
2. **Standard di Codifica:** 
    * Assicurarsi che tutto il codice C++ embedded rispetti rigidi limiti di sicurezza della memoria per prevenire eccezioni runtime durante le missioni critiche.
    * I nodi Python all'interno di ROS 2 devono seguire gli standard PEP 8 e includere i type hint dove applicabile.
3. **Documentazione:** Ogni funzionalità o sotto-modulo deve aggiornare la propria documentazione locale o lo spazio di lavoro globale del team (integrazione con la base di conoscenza Obsidian) descrivendo mappe dei registri, passaggi di calibrazione o strutture aggiornate dei payload di rete.

---

## 📬 Contatti & Supporto

Per accessi amministrativi, chiavi API hardware o documentazione operativa, contatta il team di ingegneria:
*   **Sito Web:** [www.dolobot.com](https://www.dolobot.com/)
*   **Email:** info@dolobot.com
*   **Sede legale:** Ponte Nelle Alpi, Belluno, Italia
