# Java_Algo
![immm](./karim_algo.jpg)
## Tri à bulles(Bubble Sort)
L'algorithme parcourt le tableau et compare les éléments consécutifs. Lorsque deux éléments consécutifs ne sont pas dans l'ordre, ils sont permutés.

Après un premier parcours complet du tableau, le plus grand élément est forcément en fin de tableau, à sa position définitive. En effet, aussitôt que le plus grand élément est rencontré durant le parcours, il est mal trié par rapport à tous les éléments suivants, donc permuté avec le suivant jusqu'à arriver à la fin du parcours.

Après le premier parcours, le plus grand élément étant à sa position définitive, il n'a plus à être traité. Le reste du tableau est en revanche encore en désordre. Il faut donc le parcourir à nouveau, en s'arrêtant à l'avant-dernier élément. Après ce deuxième parcours, les deux plus grands éléments sont à leur position définitive. Il faut donc répéter les parcours du tableau, jusqu'à ce que les deux plus petits éléments soient placés à leur position définitive.

C'est le plus lent des algorithmes de tri communément enseignés, et il n'est donc guère utilisé en pratique.
```java
public class Main {
    public static void main(String[] args) {
    
        int[] intArray = {20, 35, -15, 7, 55, 1, -22};
        
        for (int lastUnsortedIndex = intArray.length - 1; lastUnsortedIndex > 0; lastUnsortedIndex--) {
            for (int i = 0; i < lastUnsortedIndex; i++) {
                if (intArray[i] > intArray[i + 1]) {
                    swap(intArray, i, i + 1);
                }
            }
        }
// Affichage du tableau
        for (int i = 0; i < intArray.length; i++) {
            System.out.println(intArray[i]);
        }
    }
// Echange
            public static void swap (int[] array, int i, int j ){
            if (i == j) {
                return;
            }
            int temp = array[i];
            array[i] = array[j];
            array[j] = temp;
        }
    }

```

## Tri par sélection 

```java
public class Main {

    public static void main(String[] args) {


        int[] intArray = { 20, 35, -15, 7, 55, 1, -22 };

        for (int lastUnsortedIndex = intArray.length - 1; lastUnsortedIndex > 0;
                lastUnsortedIndex--) {

            int largest = 0;

            for (int i = 1; i <= lastUnsortedIndex; i++) {
                if (intArray[i] > intArray[largest]) {
                    largest = i;
                }
            }

            swap(intArray, largest, lastUnsortedIndex);

        }

// Affichage du tableau
        for (int i = 0; i < intArray.length; i++) {
            System.out.println(intArray[i]);
        }


    }
// Echange
    public static void swap(int[] array, int i, int j) {

        if (i == j) {
            return;
        }

        int temp = array[i];
        array[i] = array[j];
        array[j] = temp;

    }

```

## Tri par insertion
