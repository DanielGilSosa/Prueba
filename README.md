#buscaminas
package buscaminas;

import java.util.Scanner;

/**
 *
 * @author Lenovo
 */
public class pruebatwo {

    public static void main(String[] args) {

        int opcion;
        int tablero[][] = new int[10][10];
        int i, j;
        int minas;
        int vida = 100;
        int minax, minay;
        int personajex = 9, personajey = 0;
        int Botiquin;
        int Muro, Murox, Muroy;
        int Botiquinx;
        int Botiquiny;

        Scanner leer = new Scanner(System.in);

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10; j++) {
                tablero[i][j] = 0;
            }
        }

        System.out.print("Tablero inicial\n\n");

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10; j++) {
                if (tablero[i][j] == 0) {
                    System.out.print("- ");
                }
                if (tablero[i][j] == 1) {
                    System.out.print("P ");
                }
                if (tablero[i][j] == 2) {
                    System.out.print("M");
                }
                if (tablero[i][j] == 5) {
                    System.out.print("G ");
                }
                if (tablero[i][j] == 4) {
                    System.out.print("E ");
                }
                if (tablero[i][j] == 3) {
                    System.out.print("S ");
                }

                if (tablero[i][j] == 6) {
                    System.out.print("X ");
                }
            }
            System.out.print("\n");
        }
        System.out.print("\n");

        tablero[personajex][personajey] = 1;
        tablero[9][9] = 3;

        System.out.print("Tablero con Personaje y Salida\n\n");

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10; j++) {
                if (tablero[i][j] == 0) {
                    System.out.print("- ");
                }
                if (tablero[i][j] == 1) {
                    System.out.print("P ");
                }
                if (tablero[i][j] == 2) {
                    System.out.print("M ");
                }
                if (tablero[i][j] == 5) {
                    System.out.print("G ");
                }
                if (tablero[i][j] == 4) {
                    System.out.print("E ");
                }
                if (tablero[i][j] == 3) {
                    System.out.print("S ");
                }
                if (tablero[i][j] == 6) {
                    System.out.print("X ");
                }
            }
            System.out.print("\n");
        }
        System.out.print("\n");

    

        for (minas = 1; minas <= 5; minas++) {

            minax = (int) (Math.random() * 10);
            minay = (int) (Math.random() * 10);

            if (tablero[minax][minay] == 0) {
                tablero[minax][minay] = 4;
            } else {
                minas--;
            }
        }

        for (Botiquin = 1; Botiquin <= 5; Botiquin++) {

            Botiquinx = (int) (Math.random() * 10);
            Botiquiny = (int) (Math.random() * 10);

            if (tablero[Botiquinx][Botiquiny] == 0) {
                tablero[Botiquinx][Botiquiny] = 5;
            } else {
                Botiquin--;
            }
        }

        for (Muro = 1; Muro <= 3; Muro++) {

            System.out.print("Digite en cual fila desea poner el Muro " + Muro + ": ");
            Murox = leer.nextInt();
            System.out.print("Digite en cual columna desea poner el Muro " + Muro + ": ");
            Muroy = leer.nextInt();

            if (Murox < 0 || Murox > 10 || Muroy < 0 || Muroy > 10) {
                System.out.print("\nSolo se pueden digitar numeros entre 0 y 9\n\n");
                Muro--;
            } else {
                if (tablero[Murox][Muroy] == 0) {
                    tablero[Murox][Muroy] = 6;
                } else {
                    System.out.print("\nLa posición está ocupada\n\n");
                    Muro--;
                }
            }
        }

    }
}
