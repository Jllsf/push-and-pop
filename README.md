//bibliotecas
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

// constantes
#define tamanho 5

//Estrutura da Pilha
struct tpilha{
int dados[tamanho];
int ini;
int fim;
};

// Variaveis globais
struct tpilha pilha;
int op;

//Prototipação
void pilha_entrar();
void pilha_sair();
void pilha_mostrar();
void menu_mostrar();

//Função principal
int main(){
    setlocale(LC_ALL, "Portuguese");
    op = 1;
    pilha.ini = 0;
    pilha.fim = 0;
    while (op != 0){
        system("cls");
        pilha_mostrar();
        menu_mostrar();
        scanf("%d", &op);
        switch (op) {
    case 1:
        pilha_entrar();
        break;

    case 2:
        pilha_sair();
        break;
    }
}
return(0);
}

//Função para adicionar um elemento no final da pilha

void pilha_entrar(){

    if(pilha.fim == tamanho){
        printf("A pilha está cheia, impossivel empilhar um novo elemento!");
        system("pause");
    }else{
    printf("Digite o valor para ser empilhado:\n");
    scanf("%d", &pilha.dados[pilha.fim]);
    pilha.fim++;
    }
}

//Função para retirar elementos da pilha

void pilha_sair(){

    if(pilha.ini == pilha.fim){
        printf("A pilha está vazia, não há elementos para desempilhar!\n\n");
        system("pause");
    }else{
    pilha.dados[pilha.fim-1]=0;
    pilha.fim--;
    }
}

//Função para mostrar o conteúdo da pilha

void pilha_mostrar(){
    int i;
    printf("[  ");
    for (i = 0; i < tamanho; i++){
            printf("%d  ", pilha.dados[i]);
    }
    printf("\n\n");
}

//Mostrar o menu de opções
void menu_mostrar(){
    printf("\nEscolha uma opção:\n");
    printf("1 - Empilhar\n");
    printf("2 - Desempilhar\n");
    printf("0 - Sair\n");
}
