Sebastian Cojocariu 321CB UPB ACS					


				                          	Java Labirinth

package cellTypes:
-O clasa Cell de baza care contine campurile: 
	(x,y) = coordonatele in matrice(labirint)
	prioritaty = prioritatea la un moment dat a celulii(in raport cu o lista de vecini)
	noVisits = numarul de vizite in celula de a lungul algoritmului de la task 1,
	distance = reprezinta distanta minima de la celula la celula FinishCell ce va fi calculata la task2.
Clasele FinishCell,FreeCell,ObstacleCell.OutCell,StartCell care extind Cell,cu mentiunea ca constructorul OutCell initializeaza x=-1,y=-1
pentru a nu se confunda cu coord elementului matrix[0][0].

package exceptions:
	CannotMoveIntoWallsException
	HeroOutOfGroundException

default:
	CellFactory = fabrica de Cell
	Comparator1 = comparator crescator dupa prioritate
	Comparator2 : Colectia va arata astfel astfel:
	  -La inceput vor fi sortate crescator dupa prioritate toate celule de tip ObstacleCell si OutCell(nu se va face distinctie intre ele).
	  -Dupa acestea vor fi sortate toate elem. ramase(de celelalte tipuri) descrescator dupa noVisits.
	  -In caz ca exista o celula de tip FinishCell,ea va fi plasata in capatul colectiei. 
	
	Maze: clasa care contine informatiile pentru labirint.Are campurile:
		matrix = matricea ce reprezinta labirintul.
    		height = numarul de linii.
    		width = numarul de coloane.
    		currentCell = adresa celulei curente(ea va reprezenta pozitia in matrix[][]).
     		startCell = adresa celulei de intrare.
    		finishCell = adresa celulei de iesire.
    		orientation=0 = orientarea eroului e 0.(se va detalia ulterior).

    //cei 2 vectori sunt vectorii de directie pentru a verifica vecinii din matrix[][]
    //in ordinea E,N,V,S in matrice(mereu la fel,nu depinde de orientarea eroului).
    		int x[] = {0,-1,0,1}; 
    		int y[] = {1,0,-1,0};
	        PrintWriter out = adresa unde scriem rezultatele
 	 Metode: getNeighbours(),getOrientation,eroare(),getNextPosition(),isValid(),getDistances(),RoadConfigurations,task1(),task2();
	 Idee:
		task1:se aplica algoritmul din enunt
		task2:se aplica Djikstra avand drept nod de referinta finishCell.Se incepe afisarea de la startCell catre finishCell.
