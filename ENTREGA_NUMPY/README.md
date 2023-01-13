---
editor_options: 
  markdown: 
    wrap: 72
---

INFORME PRÀCTICA.

En aquest treball hem treballat amb 3 bases de dates diferents:
*"municipios.csv*", "*USAhousing.csv*" i "*eurostat.csv*" per tal de
respondre a tres preguntes.

Hem separat el treball en 3 notebooks, un per cada base de dades.

- NOTEBOOK A.

La base de dades utilitzada "municipis.csv" conté dades demogràfiques del
2020 de les illes Balears. Està separat per municipis i per fenomen
demogràfic.

La pregunta que volem resoldre és: com està distribuït el creixement
vegetatiu dels municipis de les Illes Balears? Quina és la mitjana,
mediana, mínim i màxim?

Per poder realitzar-ho, en primer lloc, hem carregat les dades a través
la funció genfromtxt de numpy.

Hem aconseguit una array dels valors de totes les diferents funcions:
"nasquts vius per residència materna", "morts fetals per residència
materna", "matrimonis per lloc fitxat com a residència","defuncions per
lloc de residència" i "creixement vegetatiu".


Per tal d'operar amb les dades que necessitem, hem utilitzat la fòrmula
arrange. Volem la posició (5-1=4 en numpy), cada 5 valors. Així, hem
obtingut les dades. Per poder operar amb més facilitat, hem convertit
les dades amb un array.

Més endavant, ho hem ordenat amb la funció sort, i hem pogut veure que
el primer valor, coincideix amb el valor més baix (el min). D'igual
forma, l'últim valor de l'array coincideix amb el valor màxim.

També es calcula la mitjana i la mediana.

En aquest cas, es pot veure que les dades són molt disperses. El valor
mínim és -42 i el màxim 119.

La mitjana del creixement vegetatiu és de 13,37, mentre que la mediana
és igual a 3.

En el box plot es pot veure que la mostra es concentra entre -22 i 40,
observant que la mediana és 3. També hi ha molts de valors atípics com
és el cas del mínim i màxim.


- NOTEBOOK B.

La segona base de dades conté dades sobre els preus de les viviendes en
la ciutat de New York. La base de dades está clasificada segons el
block, el carrer en que está ubicat, les taxes del block, el tipus,
l'any de taxació, el tipus de vivenda.... A n'aquest cas, utilizarem les
variables districte i preu.

De fet, l'objectiu de l'anàlisi és determinar quin és la mitjana,
mediana, minim i maxim del district 20 i, després, comparar-lo amb la
mitjana total.

Hem carregat cada columna de forma independent, per poder assegurar que
les dades que utilitzam són les correctes. (a través de genfromtxt)

Posteriorment, hem creat una matriu amb la funció de numpy "np.column_stack()"
per tal de poder incloure la primera columna com els districtes i la
segona els preus.

Més endavant, hem percebut que existeixen observacions no determinades.
Per tant, per facilitar l'estudi, s'han eliminat les files que tenien
alguna observació nan). A més a més, hem ordenat els valors dels
districtes de major a menor. Hem creat un gràfic que mostra la mitjana
dels preus de les cases de Nova York en funció dels districtes.

A partir d'aquí, ens centram a determinar els valors del districte 20. A
través de la funció np.where, hem creat un "filtre" que mostren tots els
valors del districte 20.

Una vegada tenim realitzat el filtre calculam la mitjana, el màxim, mínim i
mediana del districte 20 i el total.

El preu més alt del total (90000000) és significativament major que el
del districte 20, 42500000. El preu més baix del total és 500000,
mentre que el del districte 20 és 3175000. Observam que el rang del
total és més gran que el del 20. També veim que el preu mig del
districte 20, 16208333,33, és quasi el doble del total 9052040,75.
Finalment, el punt mitjà del districte 20 (5450000) és relativament
menor al total (6525000).

-   NOTEBOOK C.

Finalment, a partir del fitxer "eurostat.csv" es recull les despeses
generals del govern per funcions dels països d'Europa, així com una
mitjana dels que pertanyen a la UE i l'Euro Zona des de l'any 2012 fins al
2021. Alguns dels valors del 2021 estan sense contestar. Per aquesta raó
no els tindrem en compte per l'anàlisi.

L'objectiu final: comparar Bèlgica, Bulgària i Croàcia. Saber la
mitjana, mediana, mínim i màxim. En especial, ens centrarem en Bèlgica i
comprarem els resultats amb la mitjana dels tres països.

Com amb els apartats anteriors carregam la columna despeses del govern.
Notam que les observacions estan ordenades segons els països
i per anys. Les 10 primeres observacions pertanyen a Àustria. 
Cada una de les observacions correspon a un any desde 2012 fins 2021. 
Com ja hem explicat abans, nosaltres ens interessa 
analitzar els països, Bélgica, Bulgària i Croàcia.
Doncs, cream una array nova a partir d'obs_value, incloent
des de l'observació 11 fins a la 36, que en numpy és la llista [10:37]. 
A partir de la fórmula np.array_split podem dividir la mostra de forma equitativa,
per la qual cosa, la primera columna de cada array serà l'any 2012 i la
darrera 2020, coincidint amb els nou anys que s'utilitzen per a l'estudi. Per
comprovar que els valors són els que toquen, hem fet ús la funció tipo bolean 
per determinar que els valors creats són iguals als seleccionats de forma més manual.
La funció determina que l'array creat funciona. 

El valor mínim de Croàcia és 7,0 mentre que el màxim és 10,1 El valor
mínim de Bèlgica és 6,9 mentre que el màxim és 8,8 El valor mínim de
Bulgària és 2,8 mentre que el màxim és 3,9.

Centrant-nos en Bèlgica observam que la posició, que coincideix amb el
seu valor min (6,9) que pertany a l'any 2019 mentre que la posició màxima, que
coincideix amb el valor màxim (8,8) que pertany a l'any 2012. 
Observam que s'han anat disminuintles despeses del govern.

Finalment, comparant la mitjana amb el total, observam que la mitjana de
Bèlgica és 7,81 és més elevada que la mitjana dels 3 països és 6,52.