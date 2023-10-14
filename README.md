# Fidel-project-
Projects
 
include<stdio.h>
#include<stdlib.h>

int main()
{
    char mat[3][3];
    int l, c, op, a, b, opcao;
    int jogador, vencedor, vezes;


    do {

        printf("\tBEM-VINDO AO JOGO DA VELHA\n\n\n");
        printf("MENU PRINCIPAL\n");
        printf("-----------------------\n");
        printf("0. Jogar a dois\n");
        printf("2. Sair do Jogo\n");
        printf("-----------------------\n");
        scanf("%i",&op);

        system("cls");

        if(op == 0) {
            do {
                jogador = 1;
                vencedor = 0;
                vezes = 0;
                for( l = 0; l < 3; l++) {
                    for( c = 0; c < 3; c++) {
                        mat[l][c] = ' ';
                    }
                }


                do {
                    printf("\t\tJOGO DA VELHA\n\n");
                    printf("  0   1   2\n");
                    printf("-------------\n");

                    for( l = 0; l < 3; l++) {
                        for( c = 0; c < 3; c++) {
                            printf(" %c",mat[l][c]);

                            if(c < 2)
                                printf(" | ");
                            if(c == 2)
                                printf("  %d",l);

                        }

                        if(l < 2)
                            printf("\n-------------");


                        printf("\n");
                    }
                    printf("-------------");

                    do {
                        do {
                            printf("\n\nJogador %d digite a Posição que pretende Jogar: ",jogador);
                            scanf("%d",&a);
                            scanf("%d",&b);
                        } while(a > 2 || a < 0 || b > 2 || b < 0) ;
                    } while(mat[a][b] != ' ');

                    if(jogador == 1) {
                        mat[a][b] = 'X';
                        jogador++;
                    }
                    else {
                        mat[a][b] = 'O';
                        jogador = 1;
                    }
                    vezes++;
                    system("cls");
                    for(l = 0; l < 3; l++) {
                        if(mat[l][0] == 'X' && mat[l][1] == 'X' && mat[l][2] == 'X') {
                            vencedor = 1;
                        }
                    }

                    for(l = 0; l < 3; l++) {
                        if(mat[l][0] == 'O' && mat[l][1] == 'O' && mat[l][2] == 'O') {
                            vencedor = 2;
                        }
                    }

                    for(c = 0; c < 3; c++) {
                        if(mat[0][c] == 'X' && mat[1][c] == 'X' && mat[2][c] == 'X') {
                            vencedor = 1;
                        }
                    }

                    for(c = 0; c < 3; c++) {
                        if(mat[0][c] == 'O' && mat[1][c] == 'O' && mat[2][c] == 'O') {
                            vencedor = 2;
                        }
                    }

                    if(mat[0][0] == 'X' && mat[1][1] == 'X' && mat[2][2] == 'X')
                        vencedor = 1;

                    if (mat[0][0] == 'O' && mat[1][1] == 'O' && mat[2][2] == 'O')
                        vencedor = 2;

                    if(mat[0][2] == 'X' && mat[1][1] == 'X' && mat[2][0] == 'X')
                        vencedor = 1;

                    if(mat[0][2] == 'O' && mat[1][1] == 'O' && mat[2][0] == 'O')
                        vencedor = 2;
                } while(vencedor == 0 && vezes < 9);


                printf("\tJOGO DA VELHA\n\n");
                printf("  0   1   2\n");
                printf("-------------\n");

                for( l = 0; l < 3; l++) {
                    for( c = 0; c < 3; c++) {
                        printf(" %c",mat[l][c]);

                        if(c < 2)
                            printf(" | ");
                        if(c == 2)
                            printf("  %d",l);
                    }

                    if(l < 2)
                        printf("\n-------------");


                    printf("\n");
                }
                printf("-------------\n");

                if(vencedor == 1)
                    printf("\nParabéns Jogador 1, você ganhou o jogo...");

                if(vencedor == 2)
                    printf("\nParabéns Jogador 2, você ganhou o jogo...");

                if(vencedor == 0)
                    printf("\nÉ um empate, ninguém ganhou...");

                printf("\n\nDigite 1 para jogar Novamente...\nOu qualquer outro digito para  voltar  ao  MENU PRINCIPAL...\n");
                scanf("%d",&opcao);
                system("cls");
            } while(opcao == 1);


        }
        else if (op == 2) {
            printf("\t\tSAÍSTE DO JOGO");
        }

    } while(opcao == 1);


}