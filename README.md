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
IsLetter
bool isletter(char c)
	{
        if (c >= 'a' && c <= 'z')
        {
			return true;
        }else if(c >= 'A' && c <= "Z") 
        {
            return true;
        }
		return false;
    }
   IsDigit
    bool isdigit(char c)
    {
        if (c >= '0' && c <= '9')
        {
            return true;
        }
        return false;
    }
 Maiuscolo 
 string Maiuscolo(string s)
{
	int len = Lunghezza(s);
	char[] caratteri = s.ToCharArray();
	for (int idx = 0;idx<len;idx++)
	{
		if (c >= 'a' || c <= 'z')
		{
			int a= (int)caratteri[idx] & 0x5f;
			caratteri[idx] = (char)a;
		}
	}
	return new String(caratteri);
}
Minuscolo
 string Minuscolo(string s)
    {
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
        for (int idx = 0; idx < len; idx++)
        {
            if (c >= 'a' || c <= 'z')
            {
                int a = (int)caratteri[idx] | 0x20;
                caratteri[idx] = (char)a;
            }
        }
        return new String(caratteri);
    }
Alfabetica
 bool alfabetico(string s)
    {
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
        for (int idx = 0; idx < len; idx++)
        {
            if (isletter(caratteri[idx])
            {

            }
            else
            {
                return false;
            }
        }
        return true;
    }
Numero di lettere
int nlettere(string s)
	{
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
		int n;
        for (int idx = 0; idx < len; idx++)
        {
            if (isletter(caratteri[idx])
            {
				n = n + 1;
            }
        }
        return n;
    }
  Alfanumerica
  bool alfanumerico( string s )
	{
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
        for (int idx = 0; idx < len; idx++)
        {
            if (isletter(caratteri[idx] || isdigit(caratteri[idx])
            {
                
            }
			else
			{
				return false;
			}
        }
		return true;
    }
  Reverse
  string Reverse(string s) 
    {
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
        char[] tmp;
        for (int idx = 0; idx < len; idx++)
        {
           tmp = caratteri[idx];
            caratteri[idx]= caratteri[len];
            caratteri[len]= tmp;
            len--;
        }
        return new String(caratteri);
    }
  Numero di parole
  int numparole(string s) 
    {
        int len = Lunghezza(s);
        int n;
        char[] caratteri = s.ToCharArray();
        for (int idx = 0; idx < len; idx++)
        {
            if (caratteri[idx] == ' ' && alfabetico(caratteri[idx+1]))
            {
                n++;
            }
        }
        return n;
    }
  Capitalizzata
  string Capitalizzata(string s)
    {
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
        for (int idx = 0; idx < len; idx++)
        {
            caratteri[idx] = Minuscolo(caratteri[idx]);
        }
        caratteri[0]= Maiuscolo(caratteri[0]);
        for (int idx = 1;idx < len; idx++)
        {
            if (caratteri[idx] == ' ')
            {
                caratteri[idx+1] = Maiuscolo(caratteri[idx+1]);
            }
        }
        return new string(caratteri);
    }
  Palindroma
  bool palindromo(string s)
    {
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
        if (alfabetico(caratteri)==false)
        {
            return false;
        }
        for (int idx = 0; idx < len; idx++)
        {
            caratteri[idx] = Minuscolo(caratteri[idx]);
            caratteri[idx]= nospace(caratteri[idx]);
        }
        if (caratteri== Reverse(caratteri))
        {
            return true;
        }
        return false;
    }
    Poi ho creato un metodo che restituisce un array in cui non ci sono gli spazi:
    char nospace(string s)
    {
        int len = Lunghezza(s);
        char[] caratteri = s.ToCharArray();
        for (int idx = 0; idx < len; idx++)
        {
            if (caratteri[idx] == ' ')
            {
                for (int j = idx; j < len; j++)
                {
                    caratteri[j] = caratteri[j + 1];
                }
            }
        }
        return caratteri;
    }
