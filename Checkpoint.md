
  **#C1:**
  
El 50 entra primero y se convierte en la Raíz.
El 30 es menor que 50, se va a la izquierda.
El 70 es mayor que 50, se va a la derecha.
El 20 es menor que 50 y menor que 30, se va a la extrema izquierda.
El 40 es menor que 50 pero mayor que 30, se va a la derecha del 30.

        [50] (Raíz)
       /    \
    [30]    [70]
   /    \
 [20]  [40]  

---

 **#C2:**
 
 El recorrido in-order sigue la regla estricta: Izquierda $\rightarrow$ Raíz $\rightarrow$ Derecha.
  Aplicándolo al árbol anterior, visitamos: 20, 30, 40, 50, 70. coincide perfectamente con el orden ascendente 

 ---

 **#C3:**

 Al insertar 10, 20, 30, 40, 50 de forma ordenada en un $BST$ común, cada elemento nuevo es consecutivamente mayor que el anterior, por lo que siempre se acomodará a la derecha de la última hoja

 
    [10]
       \                  
       [20]
          \               
          [30]
             \            
             [40]
                \
                [50]
              

    El árbol pierde por completo su estructura piramidal y se convierte en una línea recta inclinada hacia la derecha.
    La complejidad se degrada a $\mathcal{O}(n)$ (tiempo lineal)
    Se le conoce técnicamente como Árbol Degenerado (o también Árbol Asimétrico / Sesgado a la derecha)

---

**#C4:**

La búsqueda por rango en un $BST$ eficiente toma un tiempo de $\mathcal{O}(\log n + k)$ (donde $\log n$ es el tiempo que toma bajar por el árbol y $k$ es el número de elementos que sí caen dentro del rango)
Cuando el algoritmo desciende desde la raíz buscando un rango, por ejemplo [8.0 a 9.0], evalúa el valor del nodo actual:
  Descarte de la rama izquierda: Si el algoritmo se topa con un nodo que vale 7.0, como 7.0 es menor que el mínimo buscado (8.0), la invariante del árbol le garantiza que absolutamente todo lo que esté a la izquierda de ese 7.0 va a ser todavía más pequeño.
  Por lo tanto, el algoritmo ignora y "poda" por completo esa rama izquierda sin visitarla.
    Descarte de la rama derecha: Si se topa con un nodo que vale 9.5, como ya superó el máximo del rango (9.0), descarta automáticamente toda la rama derecha de ese nodo, porque sabe que todo lo que esté ahí será mayor a 9.5




