# Vulnerability Assessment Tecnico - Metasploitable (192.168.50.101)

**Data della Scansione:** 23 settembre 2025  
**Strumento:** Nessus Essentials  
**Target:** 192.168.50.101 (Porte comuni)  
**Totale Vulnerabilità:** 155  
**Configurazione:** Basic Network Scan su porte comuni  

## Vulnerabilità Critiche (7 trovate)

### 1. Bind Shell Backdoor Detection
- **Severità:** Critica (CVSS 9.8)
- **Porte:** Varie (backdoor attiva)
- **Descrizione:** Rilevata una backdoor shell bind che consente accesso non autorizzato al sistema.
- **Impatto:** Possibilità di esecuzione remota di comandi senza autenticazione.
- **Risoluzione:** Rimuovere immediatamente la backdoor, aggiornare il sistema e implementare firewall per bloccare connessioni non autorizzate. Verificare l'integrità del sistema con scansioni antivirus.

### 2. Apache Tomcat SEoL (<= 5.5.x)
- **Severità:** Critica (CVSS 10.0)
- **Porte:** 8080 (HTTP)
- **Descrizione:** Versione end-of-life di Apache Tomcat con vulnerabilità note non patchate.
- **Impatto:** Esposizione a exploit remoti, inclusi RCE (Remote Code Execution).
- **Risoluzione:** Aggiornare Tomcat alla versione più recente supportata. Applicare patch di sicurezza e configurare autenticazione forte.

### 3. Canonical Ubuntu Linux SEoL (8.04.x)
- **Severità:** Critica (CVSS 10.0)
- **Porte:** Varie
- **Descrizione:** Sistema operativo Ubuntu end-of-life con vulnerabilità non risolte.
- **Impatto:** Sistema completamente vulnerabile a exploit noti.
- **Risoluzione:** Migrare a una versione supportata di Ubuntu. Applicare tutti gli aggiornamenti di sicurezza e isolare la macchina in un ambiente di test.

### 4. Debian OpenSSH/OpenSSL Package Random Number Generator Weakness
- **Severità:** Critica (CVSS 10.0)
- **Porte:** 22 (SSH)
- **Descrizione:** Generatore di numeri casuali debole in OpenSSH/OpenSSL, che compromette la sicurezza delle chiavi.
- **Impatto:** Possibilità di predire chiavi crittografiche.
- **Risoluzione:** Aggiornare OpenSSH e OpenSSL alle versioni patched. Rigenerare tutte le chiavi SSH e certificati.

### 5. UnrealIRCd Backdoor Detection
- **Severità:** Critica (CVSS 10.0)
- **Porte:** 6667 (IRC)
- **Descrizione:** Backdoor integrata in UnrealIRCd che consente accesso remoto.
- **Impatto:** Controllo completo del server IRC.
- **Risoluzione:** Rimuovere e reinstallare UnrealIRCd da fonti affidabili. Verificare l'integrità del software.

## Vulnerabilità Alte (9 trovate)

### 1. Apache PHP-CGI Remote Code Execution
- **Severità:** Alta (CVSS 9.8)
- **Porte:** 80 (HTTP)
- **Descrizione:** Esecuzione remota di codice tramite PHP-CGI mal configurato.
- **Impatto:** Attaccante può eseguire comandi arbitrari.
- **Risoluzione:** Disabilitare CGI o configurare correttamente PHP. Aggiornare Apache e PHP.

### 2. phpMyAdmin prior to 4.8.6 SQLi Vulnerability
- **Severità:** Alta (CVSS 9.8)
- **Porte:** 80 (HTTP)
- **Descrizione:** Iniezione SQL in phpMyAdmin.
- **Impatto:** Accesso non autorizzato al database.
- **Risoluzione:** Aggiornare phpMyAdmin alla versione 4.8.6 o successiva. Implementare WAF (Web Application Firewall).

## Vulnerabilità Medie (Esempi selezionati)

### 1. NFS Shares World Readable
- **Severità:** Media (CVSS 7.5)
- **Porte:** 2049 (NFS)
- **Descrizione:** Condivisioni NFS leggibili da tutti.
- **Impatto:** Esposizione di file sensibili.
- **Risoluzione:** Configurare permessi NFS per limitare l'accesso. Usare autenticazione.

### 2. SSL Certificate Cannot Be Trusted
- **Severità:** Media (CVSS 6.5)
- **Porte:** 443 (HTTPS)
- **Descrizione:** Certificato SSL non affidabile.
- **Impatto:** Possibili attacchi man-in-the-middle.
- **Risoluzione:** Ottenere un certificato valido da una CA riconosciuta.

## Raccomandazioni Generali
- **Aggiornamenti:** Applicare patch di sicurezza immediate per tutte le vulnerabilità.
- **Firewall:** Bloccare porte non necessarie.
- **Monitoraggio:** Implementare logging e monitoring per rilevare attività sospette.
- **Formazione:** Educare il team su best practices di sicurezza.
