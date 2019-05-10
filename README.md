#Calculadora, grupo E-100
#Integrantes: Daniel Picon Martinez, Ignacio Perez Trueba, Marcos Perez Eusebio
#include <stdio.h>
#include <math.h>



		float Sumar(float x,float y);
		float Restar(float x,float y);
		float Multiplicar(float x,float y);
		float Dividir(float x,float y);
		float potencia(float x,float y);

int main()
{
	float  x,y;
	float rep;
	int operador,eleccion,valor;

    printf("-----------------------------\n");
    printf("-------- Calculadora --------" );
    printf("\n-----------------------------");
		
		
		do
		{
		FILE *pf;
	pf = fopen("datoscalculadora.txt", "a");	
 	printf("\n\nElija entre calculadora de vectores o calculadora clasica: \n");
    printf("\ncalculadora vectores-1");
    printf("\ncalculadora clasica-2\n");
    scanf("%i",&eleccion);
    
    if(eleccion==1){
    		printf("\nelija entre las dos opciones:\n");
    		printf("\nsuma-1");
    		printf("\nresta-2\n");
			scanf("%i",&valor);
			
				if(valor==1){
			int vec [67];
			int vec2 [67];
			int suma[67];
			int a;
			int n;
			n=0;
			printf ("dame el tamano de los vectores: ");
			scanf ("%i", &n);
			for (a=1;a<=n;a++)
			{
			printf ("inserte posicion [%d%]: ", a);
			scanf ("%i", &vec[a]);
			
			}
			printf("\nSegundo vector\n");
			for (a=1;a<=n;a++)
			{
				
				
			printf ("inserte posicion [%d%]: ", a);
			scanf ("%i", &vec2[a]);
			
			}
			for(a= 1;a<=n;a++){
				
				suma[a]=vec[a]+vec2[a];
			
			}
			for(a= 1;a<=n;a++){
			
				printf("%i ",suma[a]);
			
			} 	
			}
			else if(valor==2){
				int vec [67];
			int vec2 [67];
			int resta[67];
			int a;
			int n;
			n=0;
			printf ("dame el tamano de los vectores: ");
			scanf ("%i", &n);
			for (a=1;a<=n;a++)
			{
			printf ("inserte posicion [%d%]: ", a);
			scanf ("%i", &vec[a]);
			
			}
			printf("\nSegundo vector\n");
			for (a=1;a<=n;a++)
			{
				
				
			printf ("inserte posicion [%d%]: ", a);
			scanf ("%i", &vec2[a]);
			
			}
			for(a= 1;a<=n;a++){
				
				resta[a]=vec[a]-vec2[a];
			
			}
			for(a= 1;a<=n;a++){
			
				printf("%i ",resta[a]);
			
			} 	
			}
			
	}
	else if(eleccion==2){
	printf("\nHa elegido la opcion calculadora clasica");
   
    printf("\nsumar--1");
    printf("\nresta--2");
    printf("\nmultiplicacion--3");
    printf("\ndivision--4");
    printf("\npotencia--5\n");

	scanf("%i",&operador);
    
	printf("---------------------------------");
   
    printf("\n\nIntroduce el primer valor: ");
    scanf("%g",&x);
    printf("Introduce el segundo valor:");
    scanf("%g",&y);
    
		
	if(operador==1){
		
		double suma1;
		suma1=  Sumar(x,y);
		printf("\nEl valor es %g ", suma1);
		fprintf(pf,"El resultado de la suma de %g + %g = %g\n ",x,y,suma1);
		
	}	
	else if(operador==2){
		
		double resta1;
		resta1=  Restar(x,y);
		printf("\nEl valor es %g", resta1);
		fprintf(pf,"El resultado de la resta de %g - %g es: %g\n",x,y,resta1);
		
	}		
	else if(operador==3){
		
		double multi;
		multi= Multiplicar(x,y);
		printf("\nEl valor es %g", multi);
		fprintf(pf,"El resultado de la multiplicacion de %g y %g es: %g\n",x,y,multi);
		
	}	
	
		else if(operador==4){
		
		double div;
		div= Dividir(x,y);
		printf("\nEl valor es %g ", div);
		fprintf(pf,"El resultado de la division de %g y %g es: %g\n",x,y,div);	
}
	else if(operador==5){
		double pot;
		pot=potencia(x,y);
		printf("\nEl valor es %g ", pot);
		fprintf(pf,"El resultado de %g elevado a %g es: %g\n",x,y,pot);	
		
	}	
	}
 		
 		printf("\n\n¿Desea realizar otra operacion? \n ");
 		printf(" Repetir->1\n  Cerrar->2\n");
		scanf("%f",&rep);
		fflush(stdin); 
		
	
	fclose(pf);
	}
	while(rep == 1);
  	printf("\nEsperemos le haya servido la calculadora, gracias");
	
	
  return 666;  
}

float Sumar(float x,float y)
{
    return x+y;
}
float Restar(float x,float y){
	   return x-y;
}

float Multiplicar(float x,float y)

{
    return x*y;
}
float Dividir(float x,float y)

{
    return x/y;
}
float potencia(float x,float y)
{
	float potencia;
	potencia=pow(x,y);
	return potencia;
}













