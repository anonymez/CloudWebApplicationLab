# Lezione 4


## Getting Started

lezione4start.html è una pagina statica, per caricarla basta fare doppio click.



### Connessione Http tramite javascript

In questa lezione si vuole mostare in maniera dinamica il contenuto ricevuto da un server rest che ci restituisce un file json.

Effettuare una chiamata http con javascript richiede l'oggetto XMLHttpRequest
 


```
<script>
var xhr = new XMLHttpRequest();
      xhr.open('GET', url, true);
    xhr.setRequestHeader('Accept', 'application/json');
    xhr.send();

    xhr.onreadystatechange = processRequest;
</script>
   
```

Questo script effettua l'operazione GET a un dato indirizzo url e il risultato viene gestiro da una funzione processRequest. La funzione processRequest deve gesitre i vari codici di risposta http, come 200,201,404,500 etc.