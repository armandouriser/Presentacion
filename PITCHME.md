## UNIVERSIDAD NACIONAL AUTONOMA DE MEXICO
## Facultad de Ingenieria
## Uribe Serralde Armando
---
# Shell sort
Es un algoritmo de ordenación interna muy sencillo pero muy ingenioso, basado en comparaciones e intercambios, y con unos resultados radicalmente mejores que los que se pueden obtener con el método de la burbuja

---

### Origen

- El Shell sort lleva este nombre en honor a su inventor, Donald Shell, que lo publicó en 1959. Algunos libros de texto y referencias antiguas le llaman ordenación "Shell-Metzner" por Marlene Metzner Norton, pero según Metzner, "No tengo nada que ver con el algoritmo de ordenamiento, y mi nombre nunca debe adjuntarse a éste."
---

---
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace PruebaVector
{
    class PruebaVector
    {
        private int[] vector;

        public void Cargar()
        {
            Console.WriteLine("Metodo de Shell Sort");
            Console.Write("Cuantos longitud del vector:");
            string linea;
            linea = Console.ReadLine();
            int cant;
            cant = int.Parse(linea);
            vector = new int[cant];
            for (int f = 0; f < vector.Length; f++)
            {
                Console.Write("Ingrese elemento "+(f+1)+": ");
                linea = Console.ReadLine();
                vector[f] = int.Parse(linea);
            }
        }

        public void Shell()
        {
            int salto = 0;
            int sw = 0;
            int auxi = 0;
            int e = 0;
            salto = vector.Length / 2;
            while (salto > 0)
            {
                sw = 1;
                while (sw != 0)
                {
                    sw = 0;
                    e = 1;
                    while (e <= (vector.Length - salto))
                    {
                        if (vector[e - 1] > vector[(e - 1) + salto])
                        {
                            auxi = vector[(e - 1) + salto];
                            vector[(e - 1) + salto] = vector[e - 1];
                            vector[(e - 1)] = auxi;
                            sw = 1;
                        }
                        e++;
                    }
                }
                salto = salto / 2;
            }
        }

        public void Imprimir()
        {
            Console.WriteLine("Vector ordenados en forma ascendente");
            for (int f = 0; f < vector.Length; f++)
            {
                Console.Write(vector[f]+"  ");
            }
            Console.ReadKey();
        }


        static void Main(string[] args)
        {
            PruebaVector pv = new PruebaVector();
            pv.Cargar();
            pv.Shell();
            pv.Imprimir();
        }
    }
}

```

![Flux Explained](http://3.bp.blogspot.com/-Bym35WE6rRI/UeYFMF7KnfI/AAAAAAAABVU/lm2hdpCvj4U/s1600/metodo+de+ordenamiento+shell+sort+en+c%23.png)
---
## Referencias
http://csharp-facilito.blogspot.com/2013/07/metodo-de-ordenamiento-shell-sort-en-c-sharp.html - automatic!
[GitHub](http://github.com)
