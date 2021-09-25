# Lab-4-Ejercicio
#include <iostream>
#include <stdlib.h>
#include <time.h>
#include <string.h>
#include <Windows.h>

void clear()
{
    std::cout<< "\x1B[2J\x1B[H";
}

int movimientosTor()
{
    int num; 
    srand(time(NULL));
    num = rand(); 
    for (int c = 1; c <= 10; c++)
    {
        num = 1 + rand() % (11 - 1); 
    }
        return num; 
}
int movimientosLie()
{
    int num2; 
    srand(time(NULL)); 
    num2 = rand(); 
    for (int u = 1; u<=10; u++)
    {
        num2 = 1 + rand() % (12 - 1); 
    }
    return num2; 

}

int main()
{
    int var2; 
    int var3; 
    int Mov = 0; 
    int segundos = 0, minutos =0,horas=0;
    int resultadoTor;
    int resultadoLie; 
    resultadoTor = movimientosTor();
    resultadoLie = movimientosLie(); 
    std::cout << "Presionar para iniciar la carrera\n";
    std::cout << "\nEl movimiento es\n";
    int* pointer = &resultadoTor; 
    int* pointerLie = &resultadoLie; 

    do
    {
        var2 = rand() % (10 - 1);
        var3 = rand() % (12 - 1);
        resultadoTor = var2;
        resultadoLie = var3; 

        if (resultadoTor <= 5)
        {
            std::cout << *pointer << "// paso veloz Tortuga 3 cuadros derecha \n";
        }
        else if (6 <= resultadoTor <= 7)
        {
            std::cout << *pointer << "// resbalon Tortuga 6 cuadros a la izquierda\n";
        }
        else if (8 <= resultadoTor <= 10)
        {
            std::cout << *pointer << "// paso lento Tortuga 1 cuadro derecha \n";
        }

        if (1 <= resultadoLie <= 3)
        {
            std::cout << *pointerLie << " // duerme liebre no se mueve\n";
        }
        else if (4 <= resultadoLie <= 5)
        {
            std::cout << *pointerLie << " // gran salto liebre 9 cuadros derecha \n";
        }
        else if (resultadoLie == 6)
        {
            std::cout << *pointerLie << "// gran resbalon liebre 12 cuadros izquierda  \n";
        }
        else if (7 <= resultadoLie <= 9)
        {
            std::cout << *pointerLie << " //salto pequeño liebre 1 cuadro derecha\n";
        }
        else if (10 <= resultadoLie <= 11)
        {
            std::cout << *pointerLie << " // resbalón pequeño liebre 2 cuadros izquierda \n";
        }
        /*resultadoTor = var2; 
        var2 =  rand() % (10 - 1);
        resultadoLie = var3;
        var3 = rand() % (10 - 1);*/

        Mov++; 
    } while (Mov <= 50);
   
    /*while (1)
    {

        segundos++; 
        if (segundos == 60)
        {
            segundos = 0; 
            minutos++; 
            if (minutos == 60)
            {
                minutos = 0; 
                horas++;
            }
        } 
        clear();
        std::cout <<( "\n\n\n\t\t\t[ % .2d: % .2d: % .2d ]", horas,  minutos, segundos);
        Sleep(2000);

    }*/
}
