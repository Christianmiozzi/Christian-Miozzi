# Christian-Miozzi
Compito Angular
Questo progetto è fatto in Angular e serve a gestire una lista di clienti. Puoi aggiungere, modificare e cancellare i clienti usando dei form (moduli). Il progetto usa un servizio per comunicare con il backend e ottenere i dati dei clienti.

Componenti
ListaComponent 
Questo componente mostra una lista di clienti, ti permette di modificarli o cancellarli, e ha un form per aggiungere nuovi clienti o aggiornare quelli esistenti. Si collega al servizio che gestisce i dati dei clienti.

Funzionalità

Visualizzare la lista dei clienti:
La proprietà customers: Client[] contiene i clienti presi dal servizio.
Il metodo getClient chiama il servizio ClientService per ottenere la lista dei clienti, prendendo l'ID dell'utente dalla sessione.

Aggiungere un nuovo cliente:
Il metodo onSubmit ti permette di aggiungere un cliente quando selectedClientId è null. Se il form è valido, i dati del nuovo cliente vengono inviati al servizio tramite addClient().
Il form usa delle regole (Validators.required) per assicurarsi che tutti i campi siano compilati.

Modificare un cliente esistente:
Il metodo onEdit carica i dati di un cliente nel form per permetterti di modificarli.
userForm.patchValue inserisce i dati del cliente selezionato nel form.
onSubmit gestisce anche l'aggiornamento del cliente se selectedClientId non è null, e usa updateClient() per salvare le modifiche.

Cancellare un cliente:
Il metodo onDelete chiede di confermare prima di cancellare un cliente. Se si conferma, chiama onDeleteClient() nel servizio per rimuovere il cliente.

Mostrare o nascondere il form:
Il metodo mostra gestisce se il form di aggiunta/modifica deve essere visibile o no, grazie alla proprietà isvisible
