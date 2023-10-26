#include <stdio.h>
#include <stdlib.h>

void merge(int vetor[], int comeco, int meio, int fim){
    int i = comeco;
    int j = meio + 1;
    int comAux = 0;
    int tam = fim - comeco + 1;
    int *vetAux;
    vetAux = (int*)malloc(tam * sizeof(int));

    while(i <= meio && j <= fim){
        if(vetor[i] < vetor[j]){
            vetAux[comAux] = vetor[i];
            i++;
        } else{
            vetAux[comAux] = vetor[j];
            j++;
        }
        comAux++;
    }

    while(i <= meio){ //Caso ainda haja elementos na primeira metade
        vetAux[comAux] = vetor[i];
        comAux++;
        i++;
    }
    
    while(j <= fim){ //Caso ainda haja elementos na segunda metade
        vetAux[comAux] = vetor[j];
        comAux++;
        j++;
    }

    for(comAux = comeco; comAux <= fim; comAux++){ //Move os elementos de volta para o vetor original
        vetor[comAux] = vetAux[comAux-comeco];
    }
}

void mergesort(int vetor[], int comeco, int fim){
    if(comeco < fim) {
        int meio = (fim+comeco)/2;

        mergesort(vetor, comeco, meio); //juntando a primeira metade
        mergesort(vetor, meio+1, fim); //juntando a segunda metade
        merge(vetor, comeco, meio, fim); //juntando tudo
    }
}


void exibir(int vetor[], int tam){
    int i = 0;

    for(i = 0; i < tam; i++)
        printf("%s%d", (i>0)?", ":"", vetor[i] );

    printf("\n");
}

int main()
{
    int i;
    int vetor[10];
    
    printf("vetor original: \n");
    for(i=0;i<10;i++){
        vetor[i] = rand() % 100;
        printf("%d ", vetor[i]);
    }
    //exibir(vetor, 10);
    
    mergesort(vetor, 0, 9);
    
    printf("\nvetor ordenado:\n");
    exibir(vetor, 10);
}
