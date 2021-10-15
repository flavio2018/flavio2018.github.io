[36_writing_better_code](36_writing_better_code.md)

# Principio di separazione funzionale
<p style= "text-align: right"><i>Created 27/09/2021</i></p>

Pensare a ogni operazione, processo, pezzo di codice da scrivere come una funzione che ha un input e produce un output.
Questo può aiutare a individuare i meccanismi più generali che compongono il processo che si sta implementando, e anche le parti minime del sistema che possono essere sostituite da altre implementazioni.
Come scomporre i processi in parti indipendenti? 
Si può considerare il Single Responsibility Principle; ma anche la probabilità che quella determinata funzionalità sia implementata diversamente in futuro.
C'è sempre infatti un compromesso tra lo sforzo da mettere nella progettazione del sistema e la velocità di implementazione.
Un sistema ben progettato è più lungo da realizzare ma sarà più facile da gestire (in senso lato) in futuro.
Un sistema implementato nel primo modo che ci viene in mente non reggerà probabilmente più di qualche iterazione.