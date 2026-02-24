# Alert ERP – Notifiche Giornaliere Codici Tecnici e Articoli Certificati

Coppia di funzioni alert integrate nel gestionale **Business Cube** per notifiche automatiche giornaliere su eventi rilevanti.

## 🛠️ Tecnologie
- VB.NET
- Funzioni alert native di Business Cube
- Query SQL su tabelle ERP (`TABHHIN`, `testord`, `movord`)

## 📋 Descrizione
Le funzioni generano notifiche automatiche su due eventi: la creazione di nuovi codici tecnici nel giorno corrente e la presenza di articoli certificati inseriti in ordini nella giornata. Entrambe interrogano il database ERP, compongono un messaggio riepilogativo e lo passano al sistema di alerting nativo di Business Cube.

## ✅ Funzionalità principali
- **CodiciTecniciOdierni:** interroga `TABHHIN` per recuperare le note di creazione dei codici tecnici del giorno
- **ArticoliCertificatiOdierni:** JOIN tra testata e corpo ordini (`testord`/`movord`) filtrando per articoli certificati (`mo_hhcert='S'`) del giorno corrente
- Entrambe alimentano la struttura `dttMsgOutParam` del sistema alert nativo

## 💡 Punti di forza
- Conoscenza del modello dati ERP Business Cube
- Utilizzo del sistema di alerting nativo del gestionale
- Query SQL con JOIN su tabelle ERP per estrazioni dati complesse

## 🏢 Contesto d'uso
Ambito ERP / controllo qualità — monitoraggio giornaliero di eventi rilevanti per la gestione articoli e ordini in Business Cube.

> **Nota:** Business Cube è un gestionale ERP diffuso in ambito manifatturiero italiano.
