# Procedura test app Protetti Android v. 0.3.0

## Indicare i device utilizzati per il test  
Nella descrizione dei test puoi fare riferimento al numero del device (es: #1)  

| Numero Device     | Modello       |  Versione SO      | Versione App (se usata diversa dalla 0.3.0)       |  
| :---------------- | :------------ | :---------------- | :----------------------------------------------   |  
| #1                |               |                   |                                                   |  
| #2                |               |                   |                                                   |  
| #3                |               |                   |                                                   |  

## Procedura:
1. Scaricare l'app (filename: app-debug-release.apk) dall'indirizzo https://github.com/noiapp/noi-app-android/releases/tag/0.3.0  
2. Installare l'app seguendo la procedura abilitando i permessi richiesti su almeno due device  
3. Iniziare il test. Puoi fare un test libero o seguire una delle indicazioni nel paragrafo '**Tipi di test effettuabili**'  
4. Indicare il risultato del test sulle [Issue](https://github.com/noiapp/noi-app-android/issues) del repository GitHub


## Tipi di test effettuabili:
- Ricezione handshake
- Ricezione segnalazione dell'incontro con il contagiato

### Test di Ricezione handshake
1. Abilitare bluetooth e tracciazione sui device
2. Visualizzazione dalle statistiche di Debug
    + Dalla schermata principale premere il bottone "DEBUG" per visualizzare le statistiche di debug
    + Verificare che la voce "Numero di Handshake" si incrementi
    + Verificare che la voce "Ultima sincronizzazione" non riporti "n/a"

Per rieseguire il test, Resettare l'SDK (vedi procedura: Ripristina SDK)

### Test di Ricezione segnalazione dell'incontro con il contagiato
1. Lasciare attivare i device per farli entrare in contatto (vedi il punto precedente: Ricezione handshake)
2. Attivare il Wi-fi
3. Dalla schermata principale del dispositivo INFORMANTE premere il bottone "INFORMA DELLA MALATTIA"
4. Inserire un numero qualsiasi di 6 cifre e premere il bottone "INVIA"
5. Ora nella schermata principale si visualizza il messaggio "INFEZIONE SEGNALATA"
6. Visualizzazione dalle statistiche di Debug
    + Dalla schermata principale premere il bottone "DEBUG" per visualizzare le statistiche di debug
    + Verificare che la voce "Certificato positivo" sia "sì"
    + Verificare che la voce "Ultima sincronizzazione" non riporti "n/a"
7. Sull'altro dispositivo RICEVENTE abilitare il Wi-fi, se non è già abilitato
8. Attendere la notifica dell'Incontro Positivo - Notifica "Nuova informazione disponibile"
9. Visualizzazione dalle statistiche di Debug
    + Dalla schermata principale premere il bottone "DEBUG" per visualizzare le statistiche di debug
    + Verificare che la voce "Incontro positivo" sia "sì"
    + Verificare che la voce "Ultima sincronizzazione" non riporti "n/a"

Per rieseguire il test, Resettare l'SDK (vedi procedura: Ripristina SDK)

#### Varianti del test:
- Dopo un reset, invertire il dispositivo INFORMANTE e RICEVENTE
- Più dispositivi INFORMANTI e RICEVENTI nello stesso momento
- Installare un terzo dispositivo dopo la procedura INFORMANTE e RICEVENTE, per verificare che l'INFORMANTE continui a segnalare la sua "infettività"


### Ripristina SDK
1. Visualizzazione dalle statistiche di Debug
    + Dalla schermata principale premere il bottone "DEBUG" per visualizzare le statistiche di debug
    + Premere il bottone "RIPRISTINA SDK"
2. Verificare che le statistiche di Debug si azzerino e operino correttamente
    + Verificare che la voce "Ultima sincronizzazione" non riporti "n/a"
    + Verificare che la voce "Certificato positivo" sia "no"
    + Verificare che la voce "Incontro positivo" sia "no"
    + Verificare che la voce "Numero di Handshake" sia 0

Se il reset non è avvenuto correttamente, riavviare il dispositivo.  




