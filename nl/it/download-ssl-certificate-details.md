---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-22"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Dettagli sullo scaricamento del certificato SSL

Dopo che un certificato SSL viene aggiunto a {{site.data.keyword.slportal_full}}, i suoi dettagli possono essere scaricati in ogni momento. Gli scaricamenti possono includere il certificato, chiave o PEM, che include tutti i dettagli disponibili associati al certificato SSL. I dettagli del certificato SSL sono scaricati in sicurezza, quindi non ci sono rischi associati al recupero dei dettagli con questo metodo.

Per scaricare i dettagli per il certificato SSL, completa la seguente procedura.

1. Accedi alla [{{site.data.keyword.slportal_full}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){: new_window} utilizzando credenziali univoche.
2. Dal menu **Sicurezza** seleziona **SSL > Certificati**.
3. Dal menu **Azioni** seleziona le **Opzioni di scaricamento** preferite per il certificato. Consulta la seguente tabella per ulteriori informazioni:<br /> <br /><table border="1"><tr><th>Opzioni di scaricamento</th><th>Informazioni sullo scaricamento</th></tr><tr><td>Scarica certificato</td><td>Scarica solo la parte del certificato e non include la chiave privata, il certificato intermedio, la richiesta firma certificato o i dettagli delle note.</td></tr><tr><td>Scarica chiave</td><td>Scarica solo la chiave privata e non include il certificato, il certificato intermedio, la richiesta firma certificato (CSR) o i dettagli delle note.</td></tr><tr><td>Scarica PEM</td><td>Scarica tutti i dettagli che sono associati al certificato SSL, incluso il certificato, la chiave privata, il certificato intermedio, la richiesta firma certificato (CSR) e le note.</td></tr></table>

## Passi successivi

Dopo la richiesta di scaricare i dettagli del certificato SSL, essi vengono automaticamente scaricati nel browser web. Seleziona lo scaricamento per aprire il file. Il file può anche essere salvato nella tua postazione di lavoro per il futuro; tuttavia, i dati di ogni certificato SSL presente nella schermata dei certificati SSL possono essere scaricati automaticamente in qualsiasi momento ripetendo i passi precedenti.
