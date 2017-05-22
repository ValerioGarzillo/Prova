//scriveremo i prototipi delle funzioni: scriviamo una sorta di indice della libreria. Ha l'utilità con un veloce colpo d'occhio di conoscere le informazioni di ciascuna funzioni utili per poterla utilizzare nel codice sorgente
float somma (float a, float b);
float sottr (float a, float b);
float prod (float a, float b);
float div (float a, float b);
int power (int a, int exp);
int mcd (int a, int b);
int mcm (int a, int b);
int min (int a , int b );
int max (int a, int b);
int fattoriale (int n);
bool isprime (int N);




//Da qui in avanti inserisco le dichiarazioni delle funzioni in libreria

float somma (float a, float b)
{
	float risultato = a+b;
	return risultato;  //variabile di tipo float restituita dalla funzione
}

float sottr (float a, float b)
{
	float risultato = a-b;
	return risultato;
}

float prod (float a, float b)
{
	float risultato=a*b;
	return risultato;

}
float div (float a, float b)
{
	float risultato=a/b;
	return risultato;
}


int power (int b, int exp)
{

	int potenza=1;
	if (exp==0) 
		return potenza;

	if (b==0)
	{
		potenza=0;
		return potenza;
	}
	for (int i=1; i<=exp; i++)
	{
		potenza *= b; //potenza=potenza*base;
	}
	return potenza;
}

int min (int a, int b)
{
	if (a < b)
		return a;
	else 
		return b;
}
int max (int a, int b)
{
	if (a > b)
		return a;
	else 
		return b;
}

int mcd (int a, int b)
{	
	int mcd;
	for (int i=1; i<=min (a, b); i++) // l'mcd tra due numeri al massimo può essere ricercato fino al minore tra i due (altrimenti che divisore sarebbe?)
	{
		if (a%i == 0 && b%i == 0)
			mcd=i;
	}  		
	return mcd;
}

int mcm (int a, int b)      
{
	int mcm;
	for (int i= a*b; i>= max(a,b); i--)   //l'mcm può al massimo essere pari al prodotto tra i due numeri e va ricercato non al di sotto del massimo tra i due numeri
	{
		if (i%a==0 && i%b==0)
			mcm=i;
	}

	return mcm;
}

int fattoriale (int n)
{
	if (n<0)
		std::cout <<"Inserisci un numero >=0 " << std::endl;
	if (n==0 || n==1) return 1;
	else return n*fattoriale (n-1);

}

bool isprime (int N)
{
 if (N<=1)
 	return false; 
 for (int i=2; i*i<=N; i++)
 {
 	if (N%i==0)
 	{
 		return false;
 	}

 }
return true;
}





