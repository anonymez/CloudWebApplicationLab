# Corso Cloud e Programmazione Web

La pagina home.html contiene tutti gli esercizi visti nella seconda lezione di laboratorio

## Getting Started

home.html è una pagina statica, per caricarla basta fare doppio click.



### Funzioni

home.html contiene le tre funzioni viste a lezione:

* Hidden/show di un div a piacimento. Potete cercare in home.html la funzione hide(div)

```
function hide(div){
	elem=document.getElementById(div);
	if(elem.style.display=='none'){
		elem.style.display='block';
	}else{
	elem.style.display = 'none';}
}
```

* Caricamento dinamico di un div, funzione loadMovie()

```
function loadMovie(){
	elem=document.getElementById("movies");
	newElem=document.createElement('div');
	newElem.className="movie";
	var movieDiv='<div class="image"> 					 <span class="center-img"></span>					<img height="150px" src="static/img/doctorstrange.jpg">				</div>				<div class="description" id="movie_1">					<div class="dispose-right">						<h2>8.5/<span style="color:grey">10<span></span><img src="static/img/star.png" height="30px" style="align: middle;margin-left: 10px"></h2>					</div>					<h3>'+movieDat.name+' ('+movieDat.year+')</h3>					<ul>						<li>1h 55m</li>						<li>Action, Fantasy</li>						<li>26 Ottobre 2016</li>					</ul>										<div style="background-color: #a7b3a5; height:50px; font-size:larger;">						Beltrade ore 	22:00 | Antheo ore 21:00 22:30 | Uci Bicocca ore 19:00 21:00					</div>				</div>					<div style="clear:both;"></div>';
	newElem.innerHTML=movieDiv;
	elem.appendChild(newElem);
}

```


* Gestione dei parametri passati tramite form e metodo GET, funzione  $_GET(param). Per vedere l'outuput della funzione in home.html controllare lo console:

```
function $_GET(param) {
	var vars = {};
	window.location.href.replace( location.hash, '' ).replace( 
		/[?&]+([^=&]+)=?([^&]*)?/gi, // regexp
		function( m, key, value ) { // callback
			if (key in vars) {
				app=[];
				app.push(vars[key]);
				vars[key]=app;
				vars[key].push(value)
			}else{
			//variable = (comparison) ? if True return this : else return this
				vars[key] = value !== undefined ? value : '';
			}
		
			
		}
	);

	if ( param ) {
		return vars[param] ? vars[param] : null;	
	}
	return vars;
}
```