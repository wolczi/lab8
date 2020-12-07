# lab8

(opis problemu, struktura programuw MPI, uzyskane wyniki):

Gra w życie jest grą w sensie matematycznym, a nie grą, w którą można grać. To jest gra „zero player”. Gra toczy się na dwuwymiarowej skończonej, której komórki mogą przyjmować dwa różne stany: „żywy” lub „martwy”. Na każdym etapie ewolucja komórki jest całkowicie zdeterminowana przez jej aktualny stan i stan jej ośmiu sąsiadów w następujący sposób: 
1) Martwa komórka z dokładnie trzema żyjącymi sąsiadami ożywa.
2) Żywa komórka z dwoma lub trzema żyjącymi sąsiadami pozostaje żywa.
3) We wszystkich innych przypadkach komórka staje się (lub pozostaje) martwa.

Gra jest uruchamiana przez wywołanie funkcji i określenie maksymalnej liczby iteracji. Stan początkowy reprezentują komórki zakodowane w macierzy szerokość * wysokość. Martwe komórki są reprezentowane przez zero, a żywe komórki są reprezentowane przez 1. Pozycja komórki na siatce jest określana przez jej pozycję w macierzy.

> int global_grid[256] =
>        {0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
>         0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0};
