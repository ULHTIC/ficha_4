# Vectores

1.	Preencher um vetor de 8 elementos inteiros. Solicite um número do teclado. Pesquisar se esse número existe no vetor. Se existir,imprimir em qual posição do vetor. Se não existir,imprimir uma mensagem que não existe.

*Resolução:*

   ```C
void ex1(void){
    printf("************ Exercicio 1 ****************\n");
    int i, vet[8], num, achei=0;
    for(i=0;i<8;i++){
        printf("\n[%d] Insira um numero:\n",i);
        scanf("%d",&vet[i]);
    }
    printf("\n\n");
    printf("Digite um valor a ser pesquisado:\n");
    scanf("%d",&num);
    for(i=0;i<8;i++)
        if(vet[i]==num){
            printf("O numero %d esta na posicao %d\n",num,i);
            printf("O numero %d foi o numero %d a ser digitado\n",num,(i+1));
            achei=1;
        }
    if(!achei)
        printf("Este numero nao existe\n");
}
   ```
2.	Preencher um vetor com 5 elementos inteiros pares entre número 2 a 20. Preencher um vetor com 5 elementos inteiros ímpares de 10 a 19.  Somar os números que pertençam a mesma posição ou seja: [0]+[0],[1]+[1].

*Resolução:*

   ```C

void ex2(void){
    printf("\n************ Exercicio 2 ****************\n");
    int vetP[5], vetI[5], num, cont=0, i;
    printf("\n");
    // vetor com valores inteiros pares entre 2 e 20
    for(i=0;i<=4;i++) {
            printf("[%d] Digite um valor inteiro par entre 2 a 20: ",i+1);
            scanf("%d",&num);
            if (num >=2 && num <= 20 && num%2==0)
                vetP[i]=num;
            else{
				printf("Valor Inválido\n");
				i--;
			}
        }
    }
    // vetor com valores inteiros impares entre 10 e 19
    for(i=0;i<=4;i++) {
        int incorreto = 1;
        do{
            printf("[%d] Digite um valor inteiro impar entre 10 a 19: ",i+1);
            scanf("%d",&num);
            if (num >=10 && num <= 19 && num%2!=0) {
                vetI[i]=num;
                incorreto = 0;
            } else {
                printf("Valor Inválido\n");
            }
        } while (incorreto);
    }
    for(i=0;i<=4;i++) {
        printf("O valor da soma da posição [%d] é: %d\n",i,vetP[i] + vetI[i]);
    }
}
   ```
3.	Preencher um vetor de 8 elementos inteiros. Mostrar o vetor e informar quantos números são maiores que 30. Somar esses números. Somar todos os números.

*Resolução:*

   ```C
void ex3(){
    printf("\n************ Exercicio 3 ****************\n");
    int i, vet[8], soma=0, countM30=0, somaM30=0;
    for(i=0;i<8;i++){
        printf("[%d] Insira um numero:\n",i+1);
        scanf("%d",&vet[i]);
    }
    for(i=0;i<8;i++){
        if (vet[i] > 30){
            countM30++;
            somaM30+= vet[i];
        }
        soma+=vet[i];
        printf("%d ",vet[i]);
    }

    printf("\nNumeros maiores que 30: %d\n",countM30);
    printf("Soma dos numeros maiores que 30: %d\n",somaM30);
    printf("Soma de todos os numeros: %d\n",soma);
}
   ```
4.	Preencher um vetor de 8 elementos inteiros. Mostrar o vetor na horizontal com \t. Calcular a média do vetor. Mostrar quantos números são múltiplos de 5. Quantos números são maiores que 10 e menores que 30. Qual o maior número do vetor.

*Resolução:*

   ```C
void ex4(void){
    printf("\n************ Exercicio 4 ****************\n");
    int vet1[8], i, cont=0, m5=0, maior=0, NF=0;
    float soma=0;
    for(i=0;i<=7;i++){
        printf("[%d] Insira um numero:\n", i+1);
        scanf("%d",&vet1[i]);
    }
    printf("\n");
    for(i=0;i<=7;i++)
        printf("\t%d",vet1[i]);
    printf("\n\n");
    for(i=0;i<=7;i++){
        soma=soma+vet1[i];
        //multiplos de 5
        if(vet1[i]%5==0)
            m5++;
        //Maior que 10 e maior que 30
        if(vet1[i]>10 && vet1[i]<30)
            NF++;
        //maior valor
        if(vet1[i]>maior)
            maior=vet1[i];
    }
    printf(" _______________________________");
    printf("\n| A media do vetor é: %3.2f \t|",soma/8);
    printf("\n| Multiplos de 5: %d \t\t|",m5);
    printf("\n| Entre 10 e 30: %d \t\t|",NF);
    printf("\n| Maior numero: %d \t\t|",maior);
    printf("\n|_______________________________|");
    printf("\n\n");
}

   ```
5.	Preencher uma matriz com 3 nomes e mostrar quantas letras A e E tem nos 3 nomes.

*Resolução:*

   ```C
void ex5(void){
    printf("\n************ Exercicio 5 ****************\n");
    int linha, coluna, contaA=0, contaE=0, tam=0;
    char nome[3][30];
    for(linha=0;linha<3;linha++){
        printf("Digite um nome: ");
        scanf("%s", nome[linha]);
    }
    for(linha=0;linha<3;linha++){
        tam=strlen(nome[linha]);
        for(coluna=0;coluna<=tam-1;coluna++) {
            if(nome[linha][coluna]=='A'||nome[linha][coluna]=='a')
                contaA++;
            if(nome[linha][coluna]=='E' || nome[linha][coluna]=='e')
                contaE++;
        }
    }
    printf("Nos nomes inseridos têm %d letras A",contaA);
    printf("\nNos nomes inseridos  têm %d letras E",contaE);
    printf("\n\n");
}

   ```
6.	Criar um algoritmo que lê um conjunto de 30 valores e os coloca em 2 vetores conforme estes valores forem pares ou ímpares. O tamanho do vetor é de 5 posições. Se algum vetor estiver cheio, escrevê-lo. Terminada a leitura escrever o conteúdo dos dois vetores. Cada vetor pode ser preenchido tantas vezes quantas for necessário.

*Resolução:*

   ```C
void imprimeVetor(int size,int vet[]){
    // Função auxiliar para o exercicio 6
    int j;
    for (j=0;j<size;j++)
        printf("%d ",vet[j]);
    printf("\n");

}

void ex6(void){
    printf("\n************ Exercicio 6 ****************\n");
    int vetPares[5], vetImpares[5], num, i,j, countPares = 0, countImpares = 0;
    for (i=0;i<30;i++){
        printf("[%d] Introduza um número:\n",i+1);
        scanf("%d",&num);
        if (num%2==0){
            if (countPares <5){
                vetPares[countPares] = num;
                countPares++;
            } else {
                printf("Vetor dos pares cheio:\n");
                imprimeVetor(5,vetPares);
            }
        } else{
            if (countImpares <5){
                vetImpares[countImpares] = num;
                countImpares++;
            } else {
                printf("Vetor dos impares cheio:\n");
                imprimeVetor(5,vetImpares);
            }
        }
    }
    printf("Vetores:\n");
    imprimeVetor(5,vetImpares);
    imprimeVetor(5,vetPares);
}

   ```
7.	Armazenar em Vetores, Nomes e Notas PR1 e PR2 de 6 alunos. Calcular a média de cada aluno e imprimir aprovado se a média for maior que 5 e reprovado se média for menor ou igual a 5. OBS.: 2 vetores para as notas tipo float. 1 vetor para os nomes. 1 vetor para a média. 1 vetor para situação.

*Resolução:*

   ```C
void ex7(void){
    printf("\n************ Exercicio 7 ****************\n");
    float PR1[6], PR2[6], media[6];
    char nome[6][30], situacao[6][50];
    int x,y;
    for(x=0;x<6;x++){
        y=1;
        printf("Qual o nome %d: ",x+1);
        scanf("%s",nome[x]);
        printf("Indique a nota %d do aluno %s: ",y,nome[x]);
        y++;
        scanf("%f",&PR1[x]);
        printf("Indique a nota %d do aluno %s: ",y,nome[x]);
        scanf("%f",&PR2[x]);
    }
    for(x=0;x<6;x++){
        media[x]=(PR1[x]+PR2[x])/2;
        if(media[x]>5)
            strcpy(situacao[x],"Aprovado Parabens");
        else
            strcpy(situacao[x],"Reprovado");
    }
    printf("__________________________________________________________________");
    printf("\n\nNome\tNota1\t\tNota2\tMedia\tSituacao");
    printf("\n________________________________________________________________");
    for(x=0;x<6;x++){
        printf("\n%s\t%3.2f\t\t%3.2f\t%3.2f\t%s",nome[x],PR1[x],PR2[x],media[x],situacao[x]);
    }
    printf("\n________________________________________________________________\n");
}
   ```
8.	Preencher um vetor com 5 números e guardar o cubo dos números em outro vetor. Mostrar os dois vetores.

*Resolução:*

   ```C
void ex8(void){
    printf("\n************ Exercicio 8 ****************\n");
    int vet[5], vetCubo[5];
    int i;
    for(i=0; i<5; i++){
        printf ("Digite um numero:\n");
        scanf("%d",&vet[i]);
        vetCubo[i]=pow(vet[i],3);
    }
    imprimeVetor(5,vet);
    imprimeVetor(5,vetCubo);
}

   ```
9.	Preencher um vetor com os numeros 10 a 20, e depois mostrar os elementos pares do vetor de trás prá frente.

*Resolução:*

   ```C
void ex9(void){
    printf("\n************ Exercicio 9 ****************\n");
    int i,t=10,vet[11];
    for(i=0; i<11; i++){
        vet[i]= t;
        t++;
    }
    for(i=10; i>=0; i=i-2)
        printf("%d\t",vet[i]);
    printf ("\n");
}
   ```
10.	Criar um algoritmo que leia os elementos de uma matriz inteira de 4 x 4 e imprima os elementos da diagonal principal.

*Resolução:*

   ```C
void ex10(void){
    printf("\n************ Exercicio 10 ****************\n");
    int lin,col, tab;
    int mat[4][4];
    for (lin=0; lin<=3; lin++){
        for (col=0; col<=3;col++){
            printf("Digite o numero inteiro da linha %d, coluna %d da matriz: ",lin+1,col+1);
            scanf("%d", &mat[lin][col]);
        }
    }
    //Imprimir a matriz
    printf("Matriz\n");
    for (lin=0;lin<=3;lin++){
        for (col=0;col<=3;col++)
            printf("%d\t",mat[lin][col]);
        printf("\n\n");
    }
    // Imprimir a diagonal principal da matriz
    printf("\n\nDiagonal principal\n\n");
    for (lin=0; lin<=3;lin++){
        printf("%d\n",mat[lin][lin]);
        for (tab=1;tab<=lin+1;tab++)
            printf("\t");
    }
}
   ```
11.	Criar um algoritmo que leia os elementos de uma matriz inteira de 3 x 3 e imprima todos os elementos, exceto os elementos da diagonal principal.

*Resolução:*

   ```C

void ex11(void){
    printf("\n************ Exercicio 11 ****************\n");
    int lin,col;
    int mat[3][3];
    for (lin=0; lin<3; lin++){
        for (col=0; col<3;col++){
            printf("Digite o numero inteiro da linha %d, coluna %d da matriz: ",lin+1,col+1);
            // aqui no scanf preenchemos a matriz
            scanf("%d", &mat[lin][col]);
        }
    }
    //Imprimir a matriz
    printf("Matriz\n");
    for (lin=0;lin<=2;lin++){
        for (col=0;col<3;col++)
                printf("%d\t",mat[lin][col]);
        printf("\n\n");
    }
    // Imprimir a matriz menos a diagonal principal
    printf("\n\nMatriz menos a diagonal principal\n\n");
    for (lin=0; lin<3;lin++){
        for (col=0;col<3;col++){
            if (lin != col)
                printf("%d",mat[lin][col]);
            printf("\t");
    }
    printf("\n");
    }
}
   ```
12.	Criar um algoritmo que leia os elementos de uma matriz inteira de 3 x 3 e adicione a outra matriz o resultado da multiplicação por 2 de cada elemento da primeira matriz.

*Resolução:*

   ```C
void ex12(void){
    printf("\n************ Exercicio 12 ****************\n");
    int lin,col;
    int mat[3][3], mat1[3][3];
    for (lin=0; lin<3; lin++){
        for (col=0; col<3;col++){
            printf("Digite o numero inteiro da linha %d, coluna %d da matriz: ",lin+1,col+1);
            // aqui no scanf preenchemos a matriz
            scanf("%d", &mat[lin][col]);
        }
    }
    //Imprimir a matriz original
    printf("Matriz original\n");
    for (lin=0;lin<=2;lin++){
        for (col=0;col<3;col++)
            printf("%d\t",mat[lin][col]);
        printf("\n\n");
    }
    // Preenche outra matriz (mat1) com os elementos multiplicados por 2
    for (lin=0;lin<=2;lin++)
        for (col=0;col<3;col++)
            mat1[lin][col] = (mat[lin][col])*2;

    // imprime a matriz mat1
    printf("\n\nMatriz com elementos multiplicados por 2\n\n");
    for (lin=0;lin<=2;lin++){
        for (col=0;col<3;col++)
            printf("%d\t",mat1[lin][col]);
        printf("\n\n");
    }
}
   ```
13.	Criar um algoritmo que lê duas matrizes M(4,6) e N(4,6) e cria uma matriz que seja o produto de M por N.

*Resolução:*

   ```C
void ex13(void){
    printf("\n************ Exercicio 13 ****************\n");
    int lin,col;
    int M[4][6], N[4][6],P[4][6];
    for (lin=0; lin<4; lin++){
        for (col=0; col<6;col++){
            printf("Digite o numero inteiro da linha %d, coluna %d da matriz M: ",lin+1,col+1);
            // aqui no scanf preenchemos a matriz
            scanf("%d", &M[lin][col]);
        }
    }
    for (lin=0; lin<4; lin++){
        for (col=0; col<6;col++){
            printf("Digite o numero inteiro da linha %d, coluna %d da matriz N: ",lin+1,col+1);
            // aqui no scanf preenchemos a matriz
            scanf("%d", &N[lin][col]);
        }
    }

    for (lin=0; lin<4; lin++){
        for (col=0; col<6;col++){
            P[lin][col]=M[lin][col]*N[lin][col];
        }
    }
    printf("Matriz M:\n");
    for (lin=0; lin<4; lin++){
        for (col=0; col<6;col++){
            printf("%d\t",M[lin][col]);
        }
        printf("\n");
    }
    printf("Matriz N:\n");
    for (lin=0; lin<4; lin++){
        for (col=0; col<6;col++){
            printf("%d\t",N[lin][col]);
        }
        printf("\n");
    }
    printf("Produto:\n");
    for (lin=0; lin<4; lin++){
        for (col=0; col<6;col++){
            printf("%d\t",P[lin][col]);
        }
        printf("\n");
    }
}
   ```
14.	Elabore um programa que recebe um nome e imprime as 4 primeiras letras do nome.

*Resolução:*

   ```C
void ex14(void){
    printf("\n\t******** Exercicio 14 ********\n");
    char nome[50];
    int i;
    printf("Introduza um nome:\n");
    scanf("%s",nome);

    for (i = 0; nome[i]!='\0' ; i++){
        if (i<4){
            printf("%c",nome[i]);
        }
    }
    printf("\n");
}

   ```
15.	Elabore um programa que recebe um nome e imprime as letras na posição impar.

*Resolução:*

   ```C
void ex15(){
    printf("\n\t******** Exercicio 15 ********\n");
    char nome[50];
    int i;
    printf("Introduza um nome:\n");
    scanf("%s",nome);

    for (i = 0; nome[i]!='\0' ; i++){
        if (i%2!=0){
            printf("%c",nome[i]);
        }
    }
    printf("\n");
}
   ```
16.	Elabore um programa que recebe do teclado um nome e imprime tantas vezes quantos forem seus caracteres.

*Resolução:*

   ```C
void ex16(void){
    printf("\n\t******** Exercicio 16 ********\n");
    char nome[50];
    int i;
    printf("Introduza um nome:\n");
    scanf("%s",nome);

    for (i = 0; nome[i]!='\0' ; i++){
        printf("%s\n",nome);
    }
    printf("\n");
}
   ```
17.	Elabore um programa que que solicite um nome e escreve-o de trás pra frente.

*Resolução:*

   ```C
void ex17(void){
    printf("\n\t******** Exercicio 17 ********\n");
    char nome[50];
    int i;
    printf("Introduza um nome:\n");
    scanf("%s",nome);
    for (i = strlen(nome)-1; i>=0 ; i--){
        printf("%c",nome[i]);
    }
    printf("\n");
}
   ```

# Funções


1.	Crie uma função que compara duas strings (fazendo o mesmo que a função strcmp).

   ```C
int ex1(char str1[], char str2[]){
    printf("************ Exercicio 1 ****************\n");
        /* Função que compara duas strings. */
    int result=1, tamanho_str1=strlen(str1), tamanho_str2=strlen(str2),i;
    // Esta função irá fazer o mesmo que a função strcmp
    //strcmp(str1, str2);
    // Mas vamos alterar o retorno.
    // Se retorna 0, as strings são diferentes, se retornar 1 as strings são iguais
    if (tamanho_str1 == tamanho_str2){
        for(i=0;i<tamanho_str1;i++){
            if(str1[i]!=str2[i]){
                result = 0;
                break;
            }
        }
    }else{
        result = 0;
    }
    return result;
}
   ```

2.	Crie uma função que transforma todos os caracteres de uma string em maiúsculas.

*Resolução:*

   ```C
void ex2(char str1[]){
    printf("\n************ Exercicio 2 ****************\n");
    int i;
    // Poderiamos usar a função toupper
    /*
    for(i=0;str1[i]!='\0';i++){
        str1[i]=toupper(str1[i]);
    }
    */
    // ou
    for(i=0;str1[i]!='\0';i++){
        if(islower(str1[i])){
            str1[i]= str1[i]-32;
        }
    }
}
   ```

3.	Crie uma função que transforma todos os caracteres de uma string em minúsculas.

*Resolução:*

   ```C

void ex3(char str1[]){
    printf("\n************ Exercicio 3 ****************\n");
    int i;
    // Poderiamos usar a função tolower
    /*
    for(i=0;str1[i]!='\0';i++){
        str1[i]=tolower(str1[i]);
    }
    */
    // ou
    for(i=0;str1[i]!='\0';i++){
        if(!islower(str1[i])){
            str1[i]= str1[i]+32;
        }
    }
}
   ```
   
4.	Crie uma função que recebe uma string e um caractere, e retorne o número de vezes que esse caractere aparece na string.

*Resolução:*

   ```C
int ex4(char str[],char c){
    printf("\n************ Exercicio 4 ****************\n");
    int i, charcount=0;
    for(i=0;str[i]!='\0';i++){
        if(str[i]==c)
            charcount++;
    }
    return charcount;
}
   ```
   
5.	Crie uma função que recebe uma string e um caractere, e apague todas as ocorrências desse caractere na string.

*Resolução:*

   ```C
void ex5(char str[],char c){
    printf("\n************ Exercicio 5 ****************\n");
    int i,i_aux=0;
    char str_aux[strlen(str)];

    //iteramos a string que recebemos e criamos uma string auxiliar sem os caracteres a apagar
    for(i=0;str[i]!='\0';i++){
        if(str[i]!=c){
            str_aux[i_aux]=str[i];
            i_aux++;
        }
    }
    // no final, pomos o '\0' no final da nossa string e copiamos para a string que recebemos.
    str_aux[i_aux]='\0';
    strcpy(str,str_aux);

    // OU sem vetor auxiliar
    /*
    for(i=0;str[i]!='\0';i++){
        if(str[i]!=c){
            str[i_aux]=str[i];
            i_aux++;
        }
    }
    str[i_aux]='\0';
    */
}
   ```
   
6.	Crie uma função que recebe uma string e dois caracteres (C1 e C2) e troque todas as ocorrências na string do caractere C1 pelo caractere C2.

*Resolução:*

   ```C

void ex6(char str[],char c1,char c2){
    printf("\n************ Exercicio 6 ****************\n");
    int i;
    for(i=0;str[i]!='\0';i++){
        if(str[i]==c1)
           str[i]=c2;
    }
}
   ```

7.	Faça um programa que contenha um menu com as chamadas às funções dos exercícios anteriores.

*Resolução:*

   ```C

void ex7(void){
    printf("\n************ Exercicio 7 ****************\n");
    int sair=1,opcao;
    do{
        printf("Escolha uma das seguintes operações:\n");
        printf(" 1) compara duas strings. \n");
        printf(" 2) Converter string em maiusculas\n");
        printf(" 3) Converter string em minusculas\n");
        printf(" 4) Contar caracter numa string\n");
        printf(" 5) Apagar um caracter numa string\n");
        printf(" 6) Trocar a ocurrencia de um caracter numa string por outro caracter\n");
        printf(" 0) Sair\n");

        printf(">");
        scanf("%d",&opcao);
        switch(opcao){
            case 1: {
                char string1[30], string2[30];
                int iguais;
                printf("Insira a primeira string:\n");
                scanf("%s",string1);
                printf("Insira a segunda string:\n");
                scanf("%s",string2);
                iguais = ex1(string1,string2);
                if(iguais){
                    printf("As strings são iguais.\n");
                }else{
                    printf("As strings são diferentes.\n");
                }
                break;
            }
            case 2: {
                char string1[30];
                printf("Insira a string:\n");
                scanf("%s",string1);
                ex2(string1);
                printf("A string fica: \n");
                printf("%s",string1);
                break;
            }
            case 3: {
                char string1[30];
                printf("Insira a string:\n");
                scanf("%s",string1);
                ex3(string1);
                printf("A string fica: \n");
                printf("%s",string1);
                break;
            }
            case 4: {
                char string1[30],c;
                int countchar;
                printf("Insira a string:\n");
                scanf("%s",string1);
                printf("Insira o caracter a pesquisar:\n");
                scanf(" %c",&c);
                countchar = ex4(string1,c);
                printf("O caracter '%c' aparece %d vez(es)\n",c,countchar);
                break;
            }
            case 5: {
                char string1[30],c;
                printf("Insira a string:\n");
                scanf("%s",string1);
                printf("Insira o caracter a apagar:\n");
                scanf(" %c",&c);
                ex5(string1,c);
                printf("A string fica \"%s\"\n",string1);
                break;
            }
            case 6: {
                char string1[30],c1,c2;
                printf("Insira a string:\n");
                scanf("%s",string1);
                printf("Insira o primeiro caracter:\n");
                scanf(" %c",&c1);
                printf("Insira o segundo caracter:\n");
                scanf(" %c",&c2);
                ex6(string1,c1,c2);
                printf("A string fica \"%s\"\n",string1);
                break;
            }
            case 0:
                sair=0;
                break;
            default:
                printf("Escolha Inválida!!!\n");
            }
    }while(sair);
}

   ```
   
8.	Crie uma função que receba 2 números e retorne o maior valor.

*Resolução:*

   ```C
int ex8(int num1, int num2){
    printf("\n************ Exercicio 8 ****************\n");
    if(num1>num2)
        return num1;
    else
        return num2;
}

   ```
   
9.	Crie uma função que receba 2 números e retorne o menor valor.

*Resolução:*

   ```C
int ex9(int num1, int num2){
    printf("\n************ Exercicio 9 ****************\n");
    if(num1<num2)
        return num1;
    else
        return num2;
}
   ```
   
10.	Crie uma função que receba 3 números e retorne o maior valor, use a função da questão 8.

*Resolução:*

   ```C
int ex10(int num1, int num2, int num3){
    printf("\n************ Exercicio 10 ****************\n");
    int num_aux = ex8(num1,num2);
    return ex8(num_aux,num3);
}
   ```
   
11.	Crie uma função que receba 3 números e retorne o menor valor, use a função da questão 9.

*Resolução:*

   ```C
int ex11(int num1, int num2, int num3){
    printf("\n************ Exercicio 11 ****************\n");
    int num_aux = ex9(num1,num2);
    return ex9(num_aux,num3);
}
   ```
   
12.	Crie uma função chamada Dado() que retorna, através de sorteio, um número de 1 até 6.

*Resolução:*

   ```C

int ex12(void){
    //printf("\n************ Exercicio 12 ****************\n");
    int r = rand() % 6 + 1;
    return r;
}

   ```
   
13.	Use a função da questão anterior e lance o dado mil vezes. Conte quantas vezes cada número saiu.
A probabilidade deu certo? Ou seja, a percentagem dos números foi parecida?

*Resolução:*

   ```C

void ex13(void){
    printf("\n************ Exercicio 13 ****************\n");
    int i, resultados[6]={0};
    double percentagem[6];

    for(i=0;i<1000;i++){
        int dado = ex12();
        resultados[dado-1] = ++resultados[dado-1];
    }
    /*for(i=0;i<6;i++){
        printf("numero %d saiu %d vezes\n",i+1,resultados[i]);
    }*/
    printf("vetor fica:\n");
    for(i=0;i<6;i++){
        printf("%d\t",resultados[i]);
        percentagem[i] = resultados[i]/(double)1000*100;
    }
    printf("\npercentagem fica:\n");
    for(i=0;i<6;i++){
        printf("O numero %d tem a percentagem de %f %%\n",i+1,percentagem[i]);
    }
    printf("A probabilidade de cada numero sair é de 16,6666...%%");
    printf("\n");
}
   ```
   
# Ficheiros

1. Implemente um programa que indique se podemos ou não abrir um determinado ficheiro.

```C
#include <stdio.h>

int main(int argc, char ** agrv){
    FILE *f_leitura, *f_escrita;
    char valorLido;
    
    // e' conveniente inicializar os ponteiros a NULL
    // podemos fazer uma atribuicao encadeada
    f_leitura = f_escrita = NULL; 

    // devemos garantir que nao tentamos aceder ao argv[1] 
    // antes de saber se ele existe.
    if (argc < 2)
    {
        fprintf(stderr, "Por favor especifique o nome do ficheiro.\n");
        return 0;
    }

    f_leitura = fopen(agrv[1], "r");
    
    if (f_leitura == NULL){
        fprintf(stderr, "O ficheiro nao pode ser lido pois nao existe.\n");
        return 0;
    }

    printf("O ficheiro pode ser lido pois existe.\n");

    fclose(f_leitura);
    return 0;
}

```

2. Implemente um utilitário que permita copiar um ficheiro para outro. O utilitário deverá receber o nome dos ficheiros por argumento.
	```bash
	.\mycopy fichOrigem.txt fichDestino.txt
	```

```C
#include<stdio.h>

int main(int argc, char ** agrv){
    FILE *f_leitura = NULL, *f_escrita = NULL;
    char caracter;

    if (argc < 3){
        fprintf(stderr, "Sintaxe: ./copy ficheiro_src ficheiro_dest\n");
        return 1;	    
    }
    
    f_leitura = fopen(agrv[1], "r");
    f_escrita = fopen(agrv[2], "w");

    if (f_leitura == NULL){
        fprintf(stderr, "Erro na abertura de ficheiro de leitura\n");
	// saida com codigo diferente de 0 indica que houve um erro
        return 2; 
    }
    if (f_escrita == NULL){
        fprintf(stderr, "Erro na abertura de ficheiro de escrita\n");
	// saida com codigo diferente de 0 indica que houve um erro
        return 2; 
    }    
   
    while (!feof(f_leitura)){
        fscanf(f_leitura, "%c", &caracter);
        fprintf(f_escrita, "%c", caracter);
    }
    
    fclose(f_leitura);
    fclose(f_escrita);
    
    return 0;
}
```
  

3. Suponha que possui um ficheiro que contém em cada linha o nome de um aluno (apenas uma palavra) e a sua respetiva classificação (0..20).
	|Nome	| Class.|
	|-------|-------|
	|Maria	| 14	|
	|João	| 18	|
	|Zé	| 4	|
	|Rute	| 7	|
	
   Escreva um programa que:
   
   a) mostre no ecrã do seu computador apenas os alunos que obtiveram aprovação e respetivas notas (classificação >= 10) na disciplina a que o ficheiro corresponde. 

   b) calcule a media da turma, e indique o nome da pessoa que teve a melhor nota, indicando seu nome e nota.


```C
#include <stdio.h>
#include <string.h>
#define DIM 32

int main(int argc, char ** agrv){
    FILE *f_leitura;
    char nome[DIM];
    int nota;
    int melhor_nota;
    char melhor_aluno[DIM];
    int soma, n_notas;

    if (argc < 2)
    {        
        fprintf(stderr, "Especifique o nome do ficheiro.\n");
        return 1;
    }


    f_leitura = fopen(agrv[1], "r");
    
    // tratamento de erro
    if (f_leitura == NULL){
        fprintf(stderr, "O ficheiro nao pode ser lido pois nao existe.");
        return 0;
    }

    melhor_nota = 0;
    soma = 0;
    n_notas = 0;


    while( !feof(f_leitura) ){
        if (fscanf(f_leitura, "%s %d", nome, &nota) != 2)
	{
		fprintf(stderr, "O ficheiro nao esta bem formatado.\n");
		return 3;
	}
        if(nota >= 10)
            printf("%s %i\n", nome, nota);

        if(nota > melhor_nota){
            melhor_nota = nota;
            strcpy(melhor_aluno, nome);
        }
        
        n_notas++;
        soma += nota;
    }

    printf("Media das notas da turma: %.2f", (float)soma/n_notas);
    printf("%s teve a melhor nota da turma, %d valores", melhor_aluno, melhor_nota);

    fclose(f_leitura);

    return 0;
}
```
  
4. Escreva um programa que leia um vetor com 10 inteiros a partir do teclado e guarde os seus valores no ficheiro DADOS.DAT (em binário).

```C
#include <stdio.h>
#define DIM 10

int main(void){
    FILE *fp = NULL;
    int v[DIM];
    int i;

    for(i=0; i<DIM; i++){
        printf("Insira um inteiro: ");
        scanf("%d", &v[i]);
    }

    fp = fopen("DADOS.DAT", "wb");
    if (fp == NULL){
        fprintf(stderr, "Nao tem permissoes para abrir o ficheiro.");
        return 1;
    }
    
    fwrite(v, sizeof(int), DIM, fp);
    fclose(fp);

    return 0;
}
```
  
5. Escreva um programa que abra o ficheiro DADOS.DAT (em binário) e apresente no ecrã a soma dos inteiros que contém.

```C
#include <stdio.h>
#define DIM 10

int main(void){
    FILE *fp;
    int v[DIM];
    int i, soma;

   fp = fopen("DADOS.DAT", "rb");
    if (fp == NULL){
        fprintf(stderr, "O ficheiro nao pode ser lido pois nao existe.");
        return 1;
    }
    
    fread(v, sizeof(int), DIM, fp);
    fclose(fp);

    for(i=0, soma=0; i<DIM; i++){
        soma += v[i];
        printf("%d", v[i]);
    }
 
    return 0;
}
```
