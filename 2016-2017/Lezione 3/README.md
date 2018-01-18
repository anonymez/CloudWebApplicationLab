# Lezione 3

La pagina homeBTstart.html contiene tutti gli esercizi visti nella seconda lezione di laboratorio

## Getting Started

homeBTstart.html è una pagina statica, per caricarla basta fare doppio click.



### BOOTSTRAP LAYOUT

homeBTStart.html è la stessa pagina creata nella lezione 2, ma utilizzando il framework [bootstrap](https://getbootsrap.com)

Il layout system di bootstrap è basato su una griglia composta da righe.
Ogni riga può contenere al massimo una serie di colonne la cui dimensione totale è 12.

![alt gridsysmte](https://raw.githubusercontent.com/anonymez/CloudWebApplicationLab/master/Lezione%203/static/img/grid.png "bootstrap grid system") 

In questo modo il template viene diviso in una navbar contente l'header, una row divisa in due colonne (una per la sidebar e una per i movie) e un tag footer.
la colonna per i movie viene di conseguenza divisa in tante row quante sono i film da mostrare. Ogni singola row viene dinuovo suddivisa in colonne e riga in base all'esigenza di impaginazione del singolo film. Di seguito un esempio del div row che contiene un singolo film.

```
<div class="row marg"><!-- riga per ogni film -->
            <!-- colonna immagine film -->
              <div class="col-md-2 col-sm-4">
                
                <img height="150px" style="padding:5px;" src="static/img/doctorstrange.jpg">
              </div>
            <!-- colonna informazioni film -->  
              <div class="col-md-10 col-sm-8">
              <!--riga info lunghezza etc -->
                <div class="row">
                  <div class="col-md-8">
                  <h3>Doctor Strange (2016)</h3>
                    <ul>
                      <li>1h 55m</li>
                      <li>Action, Fantasy</li>
                      <li>26 Ottobre 2016</li>
                    </ul>   
                    
                  </div>
                  <div class="class-md-4">
                    
                  </div>
                </div>
              <!--riga info  spettacoli-->  
                <div class="row"></div>

              </div>
            </div>
```


Bootstrap ci permette di avere un sistema dinamico di layout in quanto offre diverse tipologie di colonne sfrottando le potenzialità del mediaquery: col-xs (extra small), col-sm (small), col-md (medium), col-lg (large)...

![alt mediaquery](https://raw.githubusercontent.com/anonymez/CloudWebApplicationLab/master/Lezione%203/static/img/mediaquery.png "bootstrap mediaquery") 


### LocalStorage

La pagina homeBTStart.html carica un array di movie tramite il file moviearray.json. Il local storage permette di salvare delle coppie chiave valore. In questo esercizio vogliamo salvare nel localstorage tutti i film contenuti in moviearray.js e successivamente utilizzarli per caricare i singoli film nella pagina.
I film devono essere salvati come documenti json, quindi prima di salvarli bisogna trasformali da oggetti javascript a json, e quando vengono riletti dallo storage da documenti json a oggetti javascript.

```
<script src="static/js/moviearray.js"></script> 
     
     <script>
     	console.log("salvo movies nel localstorage");
        localStorage.setItem("movies", JSON.stringify(movieDat));
        console.log("leggo movies dal localstorage");
        var result=JSON.parse(localStorage.getItem("movies"));
        console.log(result);
        for(i=0;i<result.length;i++){
          movieDiv='<div class="col-md-12">QUI VA INSERITO IL FILM '+result[i].name+'</div>';
          elem=document.getElementById("movies");
          newElem=document.createElement('div');
          newElem.className="row marg";
          newElem.innerHTML=movieDiv;
          elem.appendChild(newElem);
        }
     </script>
```


Resta allo studente ricostruire esattamente il div di ogni movie correttamente. Ogni valore può essere letto attraverso result[i].valore. I possibili attributi sono disponibili in [moviearray.js](https://github.com/anonymez/CloudWebApplicationLab/blob/master/Lezione%203/static/js/moviearray.js)





