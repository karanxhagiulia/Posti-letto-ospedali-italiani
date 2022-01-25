
L'origine del dataset è [questa](https://www.dati.salute.gov.it/dati/dettaglioDataset.jsp?menu=dati&idPag=18).

Il dataset caricato su Jupyter Notebook presenta la colonna Anno (dal 2010 al 2019) come indice (index_col='Anno'), e diverse colonne in cui le regioni italiane sono suddivise nei vari comuni ed ospedali.

![Immagine 2022-01-24 125140](https://user-images.githubusercontent.com/96819403/150778159-5fdaa630-c3a3-4cf0-914f-f01bdc9ddae5.png)


Il mio obiettivo è conoscere il **totale dei posti letto in Italia**,  **per ogni anno**, per poi crearne la visualizzazione.

Creo un nuovo dataframe:
```
Totale_posti_letto = letti_data.groupby('Anno')['Totale posti letto'].sum()
```
Il risulato sarà un dataframe con due colonne: 
- L'anno
- Il totale dei posti letto della somma di tutti i posti letto per regione

![Immagine 2022-01-24 125726](https://user-images.githubusercontent.com/96819403/150785321-db7e4b65-94f5-41f5-a589-25b1a51a5a01.png)

Ho creato velocemente un grafico utilizzando le librerie Python per la visualizzazione dei dati.
```
plt.figure(figsize=(10,6))
sns.lineplot(data=Totale_posti_letto)
plt.title("Totale posti letto in ospedale in Italia dal 2010 al 2019")
```
![Total](https://user-images.githubusercontent.com/96819403/150987980-e5ddc63e-39ad-4937-ab8d-2603294508e5.jpeg)

[Qui la versione interattiva della Dashboard su Tableau.](https://public.tableau.com/app/profile/karanxhagiulia/viz/TotalepostilettoinospedaleinItalia2010-2018/Dashboard2)


![Dashboard 2](https://user-images.githubusercontent.com/96819403/150989069-68e81657-030d-456b-b1bf-d72cfb747718.png)


Tabella modificabile creata con Excel.
![Immagine 2022-01-25 125908](https://user-images.githubusercontent.com/96819403/150989603-f20cca14-4c12-409d-aa01-30961b15fdf0.png)


