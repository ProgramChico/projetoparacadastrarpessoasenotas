# projetoparacadastrarpessoasenotas
Programa criado para um projeto em linguagem de programação C.
#include <stdio.h>
#include <string.h>
#include <locale.h>
float calcular_media(float n1,float n2);
float calcular_ponderada(float n1,float n2,float n3);
int main (void)
{
    setlocale(LC_ALL, "");
    int i;
    struct cadastro_do_aluno
    {
        char nome[200][200];
        char turno[200][200];
        char matricula[200][200];
        int escolhas;
        float nota1[200];
        float nota2[200];
        float nota3[200];
        char curso[200][200];
        int numero_de_alunos;
    };
    struct cadastro_do_aluno iden;
    printf("Digite (1) para cadastrar aluno(s) e obter a media aritmética. \nDigite (2) para cadastrar aluno(S) e obter sua nota ponderada.\n");
    scanf("%d",&iden.escolhas);
    printf("Digite o numero de alunos que queira cadastra ou calcular a nota: ");
    scanf("%d",&iden.numero_de_alunos);
    getchar();
    switch (iden.escolhas)
    {
        case 1:
        for (i=0;i<iden.numero_de_alunos;i++) 
        {
            printf("Digite o nome do (%d) aluno(a).....: ",i+1);
            gets(iden.nome[i]);
            printf("Digte o turno do (%d) aluno(a).....: ",i+1);
            gets(iden.turno[i]);
            printf("Digite a matricula do (%d) aluno(a): ",i+1);
            gets(iden.matricula[i]);
            printf("Digite Curso Superior do Aluno (%d): ",i+1);
            gets(iden.curso[i]);
            printf("Digite a nota da primeira unidade: ");
            scanf("%f",&iden.nota1[i]);
            printf("Digite a nota da segunda unidade: ");
            scanf("%f",&iden.nota2[i]);
            getchar();
        }
        
        for (i=0;i<iden.numero_de_alunos;i++)
        {
            printf("\n------------Aluno numero (%d)-----------------",i+1);
            printf("\n------------Media Aritmetica------------------");
            printf("\nNome do aluno(%d)........: %s",i+1,iden.nome[i]);
            printf("\nTurno do aluno(%d).......: %s",i+1,iden.turno[i]);
            printf("\nMatricula do aluno(%d)...: %s",i+1,iden.matricula[i]);
            printf("\nCurso....................: %s",iden.curso[i]);
            printf("\nNota da 1ª unidade.......: %.2f\nNota da 2ª unidade.......: %.2f",iden.nota1[i],iden.nota2[i]);
            printf("\nMedia final..............: %.2f",calcular_media(iden.nota1[i],iden.nota2[i]));
            printf("\n");
        }
        break;
        case 2:
        for (i=0;i<iden.numero_de_alunos;i++)
        {
            printf("Digite o nome do (%d) aluno(a).....: ",i+1);
            gets(iden.nome[i]);
            printf("Digte o turno do (%d) aluno(a).....: ",i+1);
            gets(iden.turno[i]);
            printf("Digite a matricula do (%d) aluno(a): ",i+1);
            gets(iden.matricula[i]);
            printf("Digite Curso Superior do Aluno (%d): ",i+1);
            gets(iden.curso[i]);
            printf("Digite a nota da primeira unidade: ");
            scanf("%f",&iden.nota1[i]);
            printf("Digite a nota da segunda unidade: ");
            scanf("%f",&iden.nota2[i]);
            printf("Digite a nota da prova final realizada: ");
            scanf("%f",&iden.nota3[i]);
            getchar();
        }
        for (i=0;i<iden.numero_de_alunos;i++)
        {
            for (i=0;i<iden.numero_de_alunos;i++)
            {
                printf("\n------------Aluno numero (%d)-------------------",i+1);
                printf("\n------------Media Ponderada---------------------");
                printf("\nNome do aluno(%d)........: %s",i+1,iden.nome[i]);
                printf("\nTurno do aluno(%d).......: %s",i+1,iden.turno[i]);
                printf("\nMatricula do aluno(%d)...: %s",i+1,iden.matricula[i]);
                printf("\nCurso....................: %s",iden.curso[i]);
                printf("\nNota da 1ª unidade.......: %.2f\nNota da 2ª unidade.......: %.2f\nNota prova Final: %.2f",iden.nota1[i],iden.nota2[i],iden.nota3[i]);
                printf("\nMedia final..............: %.2f",calcular_ponderada(iden.nota1[i],iden.nota2[i],iden.nota3[i]));
                printf("\n");
            }
        }
        break;
    }
    return 0;
}
float calcular_media(float n1,float n2){
    float result;
    result=(n1+n2)/2;
    return(result);
}

float calcular_ponderada(float n1, float n2,float n3)
{
    float result;
    result=((n1*5)+(n2*3)+(n3*2))/10;
    return(result);
}
