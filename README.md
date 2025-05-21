/***************************************************************************************************
Vetores: uma váriavel que guarda VÁRIOS valores.
Variável composta, Unidimensional e Homogênea(Todos os valores que ela guarda são do mesmo tipo).
Problema: Contar a quantidade de valores acima da média de alturas.
1º: Ler os valores e calcular a média.
2º: Ler os valores e contar quantos estão acima da média.
vetores = altura []
dentro da [ ]pode ser colocado: Constantes, Variaveis, ou expressões numéricas, DESDE QUE sejam valores INTEIROS.


----------------------------------------------------------------------------------------------------
#include <cstdlib>
#include <iostream>

int main() {
    float a0, a1, a2, a3, a4, a5, a6, a7, a8, a9
    cout<<"digite a 1º altura"<<endl;
    cin>>a0;

    cout<<"digite a 2º altura"<<endl;
    cin>>a1;

    cout<<"digite a 3º altura"<<endl;
    cin>>a2;

    cout<<"digite a 4º altura"<<endl;
    cin>>a3;

    cout<<"digite a 5º altura"<<endl;
    cin>>a4;

    cout<<"digite a 6º altura"<<endl;
    cin>>a5;

    cout<<"digite a 7º altura"<<endl;
    cin>>a6;

    cout<<"digite a 8º altura"<<endl;
    cin>>a7;

    cout<<"digite a 9º altura"<<endl;
    cin>>a8;

    cout<<"digite a 10º altura"<<endl;
    cin>>a9;
    return 0;
}
***************************************************************************************************/

/***************************************************************************************************
Calcular a média e quantidade de valores acima da média.


#include <cstdlib>
#include <iostream>

using namespace std;

int main(int argc, char** argv) {
    //Declaração da váriavel.
    float altura[10], media, tt;
    //Declaração de váriaveis auxiliar.
    int i;
    //Leitura do vetor.
    media = 0;
    i = 0;
    tt = 0;
    while (i < 10){
        cout <<"Digite o "<< i + 1 << "º valor: ";
        cin >> altura[i];
        media = media + altura[i];
        i++;
    }
    cout <<"A média é " << media / i <<endl;     //calcular a média
    i = 0;
    while (i < 10){
        i = i + 1;
        if(altura[i] > media){
            tt = tt + 1;
        }

    }
    cout<<"A quantidade de valores acima da média é: "<< tt <<endl;

    //Escrita do vetor
    i = 0;
    while(i < 10){
        cout << "O " << i+1 << "º valor é: " << altura[i]<< endl;
        i++;
    }

    return 0;
}
***************************************************************************************************/
/***************************************************************************************************
//Buscar um valor passado pelo usuário e informar quantos foram encontrados.
#include <cstdlib>
#include <iostream>

using namespace std;

int main(int argc, char** argv) {

    float altura[10], media, val, j;
    int i;

    media = 0;
    i = 0;

    while (i < 10){
        cout <<"Digite o "<< i + 1 << "º valor: ";
        cin >> altura[i];
        i++;
    }
    cout << "Digite o valor que deseja: ";
    cin >>val;
    i = 0;
    j = 0;
    while(i < 10){
        if(val == altura[i]){
            j = j+1;
        }
        i++;
    }
    cout << j <<endl;
    return 0;
}
***************************************************************************************************/
//Buscar quantos valores estão em um intervalo (defina um limite inferior e um limite superior).
/***************************************************************************************************
#include <cstdlib>
#include <iostream>

using namespace std;

int main(int argc, char** argv) {

    float altura[10], media, max, min, j;
    int i;

    media = 0;
    i = 0;

    while (i < 10){
        cout <<"Digite o "<< i + 1 << "º valor: ";
        cin >> altura[i];
        i++;
    }
    cout << "Digite o valor maximo: ";
    cin >>max;
    cout << "Digite o valor minimo: ";
    cin >>min;
    i = 0;
    j = 0;
    while(i < 10){
        if(altura[i]>= min and altura[i]<= max){
            j = j+1;
        }
        i++;
    }
    cout << j <<endl;
    return 0;
}

***************************************************************************************************/

//Criar uma menu de opções. Sendo o 0 para sair. Arquivo de entrada com números inteiros.

/***************************************************************************************************

#include <cstdlib>
#include <iostream>

using namespace std;

int main(int argc, char** argv) {
    const int tamanho = 10;
    int vet[tamanho], val, i, menu, j;
    
    i = 0;
    
    while(i < tamanho){ //Receber os valores do vetor
        cout <<"Digite o "<< i + 1 << "º valor: ";
        cin >> vet[i];
        i++;
    }    


    while(menu != 0){ //Menu / loop
        cout <<"Digite 1 para encontrar a posição da primeira ocorrência de um valor."<<endl;
        cout <<"Digite 2 para indicar todas as posições de um valor."<<endl;
        cout <<"Digite 3 para indicar  as posições onde os valores se repetem com a posição seguinte."<<endl;
        cout <<"Digite 4 para inverter o vetor."<<endl;
        cout <<"Digite 5 pra definir todos os valores com um unico elemento."<<endl;
        cout <<"Digite 6 para adicionar um valor a todos os elementos não divisiveis por três."<<endl;
        cout <<"Digite 7 para remover a primeira ocorrência de um valor."<<endl;
        cout <<"Digite 8 para remover todas as ocorrências de um valor."<<endl;
        cout <<"Digite 9 para inserir um valor no vetor, caso ele não esteja cheio."<<endl;
        cout <<"Digite 10 para inserir um valor em uma posição especifica no vetor."<<endl;
        cout <<"Digite 11 para remover todos os valores repetidos no vetor."<<endl;
        cout <<"Digite 0 para interromper."<<endl;
        cin>>menu;

        val = 0;
        i = 0;
        j = tamanho;
        if(menu == 1){ // Encontrar a posição da primeira ocorrencia de um valor.
            cout << "Digite um valor para encontrar a posição da primeira ocorrencia: "<<endl;
            cin >>val;
            while (vet[i] != val){
                i++;
            }
            cout <<"Está na posição: "<< i <<endl;
        }

        else if (menu == 2){ //Indicar todas as posições de um valor
            cout<<"Digite um valor para saber suas posições"<<endl;
            cin>>val;
            while(i < tamanho){
                if (vet[i] == val){
                    cout <<"está na posição: "<<i<<endl;
                }
                i++;

            }
        }
        else if (menu == 3){ //Indicar as posições em que os valores se repetem com a posição seguinte.
            while(i < tamanho){
                if(vet[i] == vet[i+1]){
                    cout<<"O valor da posição: "<< i <<", Se repete na posição: "<< i+1 <<endl;
                }
            i++;
            }
        }
        else if (menu == 4){ //Inverter os valores do vetor: primeiro com o ultimo, ultimo com o penultimo bla bla bla
            while(j >= 0){
                vet[i] = vet[j-1];
                j = j-1;
                i++;
                cout<<"O vetor invertido é: " << vet[i] <<endl;
            }
        }
        else if(menu == 5){ // Defina TODOS os elementos com apenas um valor
            cout << "Digite um valor para atribuir a todo o vetor: "<<endl;
            cin >>val;
            while(i < tamanho){
                vet[i] = val;
                cout<<"Resultado do vetor: " << vet[i] <<endl;
                i++;
                
            }
        }
        else if (menu == 6){// Adicione um valor a todos os elementos não divisiveis por três
            cout << "Digite um valor para atribuir a todo o vetor: "<<endl;
            cin >>val;
            while(i < tamanho){
                if( vet[i] % 3 != 0){
                    vet[i] = val;
                }            
                cout<<"Resultado do vetor: " << vet[i] <<endl;                    

                i++;
            }
        }
        else if (menu == 7){ // remova a primeira ocorrencia de um valor.

        }
        else if (menu == 8){ // Remova todas as ocorrencias de um valor.

        }
        else if (menu == 9){ // Inserir um valor no vetor, caso ele não estiver cheio
            //if vetor não cheio se não ja quebra aqui
        }

        else if (menu == 10){ // Inserir um valor numa posição especifica.

        }
        else if (menu == 11){ // Remover todos os valores repetidos

        }
    }
    return 0;
}
***************************************************************************************************/
#include <cstdlib>
#include <iostream>

using namespace std;

int main(int argc, char** argv) {
    const int tamnome = 30, nomcompleto = 60;
    char nome [tamnome], nomedomeio[tamnome], sobrenome[tamnome],nomecompleto[nomcompleto];
    int i,j,k;
    i = 0;
    j =0;
    k = 0;
    nome[0] = 'L';
    nome[1] = 'u';
    nome[2] = 'i';
    nome[3] = 'z';
    nome[4] = '\0';
    printf("\n Nome: %s.\n", nome);
    nomedomeio[0] = 'G';
    nomedomeio[1] = 'a';
    nomedomeio[2] = 'b';
    nomedomeio[3] = 'r';
    nomedomeio[4] = 'i';
    nomedomeio[5] = 'e';
    nomedomeio[6] = 'l';
    nomedomeio[7] = '\0';
    printf("\n Nome: %s.\n", nomedomeio);
    sobrenome[0] = 'C';
    sobrenome[1] = 'a';
    sobrenome[2] = 'b';
    sobrenome[3] = 'r';
    sobrenome[4] = 'e';
    sobrenome[5] = 'r';
    sobrenome[6] = 'a';
    sobrenome[7] = '\0';
    printf("\n Sobrenome:  %s.\n", sobrenome);
   while(nome[i] != '\0'){
    nomecompleto[j] = nome[i];
    i++;
    j++;
   }
   i= 0;
   while(nomedomeio[i] != '\0'){
    nomecompleto[j] = nomedomeio[i];
    i++;
    j++;
   }
   i=0;
   while(sobrenome[i] != '\0'){
    nomecompleto[j] = sobrenome[i];
    i++;
    j++;
   }
   nomecompleto[j]= '\0';
   
    printf("\n Nome completo:  %s.\n", nomecompleto);
















    return 0;
}
