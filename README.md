//# C-
//EJERCICIO C# DE DECISIONES HISTORIA SIN FIN


using System;

public class Program
{

// FUNCIÓN

static int ManejarLinea(string texto, int numeroSalto1, int numeroSalto2, int numeroSalto3)
    {
        Console.WriteLine(texto);

        // TERMINAR PROG
        if (numeroSalto1 == 1 && numeroSalto2 == 0 && numeroSalto3 == 0)
        {
            return 1;
        }

        // SEGUIR CRONO (no es pregunta)
        if (numeroSalto1 == 0 && numeroSalto2 == 0 && numeroSalto3 == 0)
        {
            return 0;
        }

        // INPUT
        string entrada = Console.ReadLine();

        // Salto opcion 1
        if (entrada == "1")
        {
            return numeroSalto1;
        }

        // Salto opcion 2
        if (entrada == "2")
        {
            return numeroSalto2;
        }

        // Salto opcion 3
        if (entrada == "3")
        {
            return numeroSalto3;
        }

        // seguir
        return 0;
    }

    public static void Main()
    {
        // ARRAYS
        string[] textos = new string[12];
        int[] saltos1 = new int[12]; // opcion 1
        int[] saltos2 = new int[12]; // opcion 2
        int[] saltos3 = new int[12]; // opcion 3

        textos[0] = "Bogotá amanece gris. Miras el celular: 7:18 a.m.";
        saltos1[0] = 0; saltos2[0] = 0; saltos3[0] = 0;

        textos[1] = "La clase empieza a las 8:00. Sales corriendo a la calle.";
        saltos1[1] = 0;
		saltos2[1] = 0;
		saltos3[1] = 0;

        textos[2] = "Llegas a la esquina. 1) Tomar el camino conocido. 2) Tomar un atajo. 3) Ir en bici";
        saltos1[2] = 3;
        saltos2[2] = 5;
        saltos3[2] = 9;

        textos[3] = "Caminas por la ruta de siempre, pasando la panadería.";
        saltos1[3] = 0;
        saltos2[3] = 0;
        saltos3[3] = 0;

        textos[4] = "A la vuelta de la esquina ves que cerraron la Calle 26 por una obra.\n1) Meterte por la obra a ver qué tan grave está 2) Devolverte y buscar otra calle.";
        saltos1[4] = 6;
        saltos2[4] = 11;
        saltos3[4] = 0;

        textos[5] = "Entras por el atajo, que también da a la Calle 26. Al fondo ves la misma obra bloqueando el paso.";
        saltos1[5] = 0;
        saltos2[5] = 0;
        saltos3[5] = 0;

        textos[6] = "Efectivamente la Calle 26 está cerrada por la obra y no hay forma fácil de rodearla.\n1) Rodear por el andén. 2) Cruzar la calle rápidamente. 3) Volver y esperar a que pase el trancón con paciencia.";
        saltos1[6] = 0;
        saltos2[6] = 8;
        saltos3[6] = 10;

        textos[7] = "Rodeas por el andén pero a mitad de camino recibes un mensaje de que cancelaron la clase. FINAL: NO LLEGASTE";
        saltos1[7] = 1; saltos2[7] = 0; saltos3[7] = 0;

        textos[8] = "Cruzas justo cuando pasa una moto y te atropellan, pailas. FINAL: NO LLEGASTE.";
        saltos1[8] = 1; saltos2[8] = 0; saltos3[8] = 0;

        textos[9] = "Le metes turbo a la bici, llegas sudando pero a tiempo. FINAL: LLEGASTE.";
        saltos1[9] = 1;
		saltos2[9] = 0;
		saltos3[9] = 0;

        textos[10] = "Esperas con paciencia, cruzas seguro pero llegas dos minutos tarde y te toca rogar para entrar. FINAL: LLEGASTE PERO QUEDASTE MAL.";
        saltos1[10] = 1;
		saltos2[10] = 0;
		saltos3[10] = 0;

        textos[11] = "Te devuelves, pierdes tiempo buscando otra ruta que no sirve y llegas tarde. FINAL: NO LLEGASTE.";
        saltos1[11] = 1;
		saltos2[11] = 0;
		saltos3[11] = 0;

        for (int i = 0; i < textos.Length; i++)
        {
            int resultado = ManejarLinea(textos[i], saltos1[i], saltos2[i], saltos3[i]);

            // BREAK SI LLEGAMOS FIN
            if (resultado == 1)
            {
                break;
            }
            // salto
            else if (resultado != 0)
            {
                i = resultado - 1;
            }
        }
    }
}
