- Da dove viene il termine machine learning? [ML su Wikipedia](https://en.wikipedia.org/wiki/Machine_learning#History_and_relationships_to_other_fields)
- Perché la metafora utilizzata è quella dell'apprendimento? 
- Quale legittimità ha il machine learning (in particolare il deep learning) come strumento conoscitivo, capace di simulare fenomeni complessi che esibiscono comportamenti emergenziali?

---

La locuzione "apprendimento automatico" o "apprendimento nelle macchine" (*machine learning*) evoca un immaginario preciso, facendo riferimento alla capacità umana e animale di imparare. Da un'entità che *impara* ci si attende una variazione di *comportamento* a seguito di esperienza o riflessione. Il termine, usato nella sua accezione comune, nasconde già una complessità notevolmente maggiore di quanta non sia implementata nei più comuni algoritmi di apprendimento automatico.

La locuzione inglese *machine learning* fu usata per la prima volta nel 1959[^samuel], ad indicare algoritmi che erano in grado di trovare i valori di alcuni parametri di un secondo algoritmo tali che esso potesse essere usato per giocare a scacchi. In seguito, negli anni 1960', la ricerca in questo ambito si è occupata principalmente del problema di classificare *pattern*, una linea di investigazione che è giunta fino ad oggi.

Rispetto al modo tradizionale di concepire il calcolo, ossia formulandolo come una successione di istruzioni ([paradigma imperativo](https://en.wikipedia.org/wiki/Imperative_programming)) o al più come una successiva applicazione di funzioni a una sorgente di dati ([lambda calcolo](https://en.wikipedia.org/wiki/Lambda_calculus)), l'idea dietro l'apprendimento automatico è di evitare di specificare a priori quale sarà il comportamento di un programma, ma far sì che esso "si adatti" alla sorgente di informazioni che riceve, rispetto allo specifico compito che deve assolvere. Sotto quest'ottica, si intuisce perché sia stato usato il termine *apprendimento*, che fa riferimento alla capacità di adattamento del programma.

Questo approccio alla creazione di algoritmi ha però pesantemente bisogno di prendere in prestito saperi e metodi da altre discipline, come la matematica e la statistica. In qualsiasi tipologia di apprendimento automatico, infatti, la ricerca dei valori ottimali dei parametri che definiranno il funzionamento finale dell'algoritmo avviene attraverso l'applicazione di un ulteriore algoritmo, detto di ottimizzazione. Questa classe di algoritmi sono oggetto di intenso studio da parte dei matematici, e servono a risolvere una classe di problemi molto generale: trovare il valore dei parametri di una funzione tale che il valore della funzione stessa sia il minimo (o massimo) possibile. La funzione che viene "ottimizzata" viene chiamata comunemente *loss function*, e rappresenta una descrizione dell'abilità dell'algoritmo nel compito finale per il quale sarà utilizzato (ad es. giocare a scacchi).

Avevo identificato la simulazione dell'apprendimento come uno dei modi in cui il computer può essere usato come strumento sperimentale[^strumento]. Tuttavia, mi sembra sia più appropriato considerare i modelli di apprendimento automatico come un diverso tipo di strumento conoscitivo, non completamente assimilabile agli strumenti di simulazione. Come (indirettamente) suggerito da Arthur[^arthur], gli algoritmi sono uno strumento conoscitivo proprio dei fenomeni complessi[^complessità]. 

L'assunto alla base dell'utilizzo degli algoritmi di deep learning nelle neuroscienze cognitive (come promosso da McClelland) è che essi possano essere considerati *modelli della complessità* delle reti neuronali animali e umane. L'emergenza di alcuni comportamenti o caratteristiche nel modello (algoritmo) di cui si ottimizzano i parametri è confrontata con il processo di emergenza di caratteristiche cognitive negli animali o nell'uomo. Quali sono le basi teoriche su cui si fonda questo assunto, e quanto sono solide?

---

Due riferimenti utili sono
- [@negrotti_making_1991](@negrotti_making_1991.md)
- [@cichy_deep_2019](@cichy_deep_2019.md)

 [^strumento]: [35_computer_strumento_sperimentale](35_computer_strumento_sperimentale.md)
 [^arthur]: [@arthur_algorithms_2020](@arthur_algorithms_2020.md)
 [^complessità]: [67_complessità](67_complessità.md)
 [^samuel]: [@samuel_studies_1959](@samuel_studies_1959.md)