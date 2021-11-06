[36_writing_better_code](36_writing_better_code.md)

# Problemi nello sviluppo software e come risolverli
<p style= "text-align: right"><i>Created 27/09/2021</i></p>

Ci sono diversi tipi di problemi che si possono incontrare, affrontare e risolvere nel *processo* di scrittura del codice. Qui provo a distinguerli e a proporre approcci per affrontarli.

## Riproducibilità
- usare tool appositi come Docker, [Cog](https://github.com/replicate/cog)
- tool per gestire progetti di ML nello specifico: https://www.mlflow.org/
- tool per gestire le configurazioni dei parametri negli esperimenti: https://github.com/PetrochukM/HParams (duplica funzionalità di MLflow?)

## Scrivere codice manutenibile e comprensibile
- adottare principi ingegneria del software[^principio-separazione] 
	- (quali principi ingegneria del software per software procedurale? non OO)

## Avere output presentabili e "discutibili" per avere feedback da collaboratori
(utile per codice di ricerca ma non solo)
- Usare tool per la visualizzazione online? (e.g. Tensorboard permette di pubblicare i plot su pagine web...)
	- nota: questa è la necessità a cui si risponde in modo ingenuo quando si usa Jupyter notebook per tutto; resta il fatto che si può usare *solo* come strumento di presentazione di risultati (eventualmente sfruttando la possibilità di pubblicare i notebook online, ad es. come su GitLab; edit: si può anche su GitHub 🥳)

[^principio-separazione]: [36b_principio_separazione_funzionale](36b_principio_separazione_funzionale.md)