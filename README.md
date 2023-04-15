# Strings
###Programma c# per lo studio delle stringhe:
Programma che manipola le stringhe senza usare i metodi convenzionale elaborarando una stringa in ingresso e visualizzare:
- la sua versione Maiuscola
- la sua versione Minuscola
- se contiene solo caratteri Alfabetici
- di quante lettere è formata
- se contiene solo caratteri alfanumerici 
- La sua versione rovesciata 
- di quante parole è formata
- la versione Capitalized 
- Se è palindroma 
Per realizzarlo non ho usato seguenti metodi, ma li ho costruiti personalmete:
-Lenght()
-ToUpper()
-ToLower()
-StringBuilder()
-Count()
-Replace()
-IsLetter()
-IsNumber()
Lenght
Per creare il metodo .Lenght() ho convertito la stringa in un array, poi ho dichiarato una variabile intera che aumenteraà di 1 ogni volta che si scorre il vettore.
Qui c'è un esempio:
```
int Lunghezza(string comecavolomipare)
	{
		char[] caratteri = comecavolomipare.ToCharArray();
		int retVal =0;
		foreach(var carattere in caratteri) 
		{ 
			retVal++;
		}
		return retVal;
	}
  ```
Maiuscolo
