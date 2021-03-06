---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installazione del client Backup in Windows

L'installazione del client {{site.data.keyword.backup_full}} in Windows viene completata attraverso una serie di interazioni sul server designato per il servizio {{site.data.keyword.backup_notm}}.

Per informazioni sui backup per i server Windows 2016, vedi [Configurazione di {{site.data.keyword.backup_notm}} su Windows 2016](install-backup-client-windows2016.html).
{:tip}

## Accesso al server del dispositivo di destinazione

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} e fai clic sul'icona **Menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**. <br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Seleziona **Devices** > **Device List** dal menu principale per visualizzare l'elenco di server disponibili.
3. Trova il dispositivo per cui hai acquistato il servizio {{site.data.keyword.backup_notm}} e prendi nota del suo indirizzo IP pubblico.
4. Fai clic sulla freccia rivolta verso destra per espandere ulteriori informazioni sul dispositivo, incluso il nome utente e la password. Se la password non viene visualizzata, fai clic su **Show Password**.
5. Accedi al dispositivo di destinazione utilizzando la connessione al desktop remoto.

## Download del client Backup

1. Sul server di destinazione, apri una sessione del browser e immetti il seguente l'URL per scaricare il file eseguibile per il client {{site.data.keyword.backup_notm}}. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. Fai doppio clic sul file scaricato.
3. Fai clic su **Run**.


## Installazione e registrazione dell'agent Backup

1. Immetti l'indirizzo di rete: <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. Immetti il nome utente nel campo **user name**.
3. Immetti la password nel campo **password**.
6. Fai clic su **Next**
7. Fai clic su **Install** per completare l'installazione.

## Configurazione degli agent Backup

Accedi al portale {{site.data.keyword.backup_notm}} per configurare e gestire i tuoi agent backup. Per ulteriori informazioni, vedi l'[Esercitazione introduttiva](index.html#configuring-the-backup-agent-and-the-backup-schedule).
