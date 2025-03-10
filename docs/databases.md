Indeksy w bazach danych to struktury danych używane do przyspieszenia wyszukiwania i odwoływania się do danych w bazie. Indeksy działają na podobnej zasadzie jak indeksy w książce, umożliwiając szybkie odnajdywanie konkretnych rekordów na podstawie wartości w określonych kolumnach.

Indeksy w bazach danych wykorzystują różne algorytmy, z których najpopularniejsze to:

1.  B-drzewa (B-trees): B-drzewa są szeroko stosowanymi strukturami indeksującymi. Pozwalają na skuteczne wyszukiwanie, wstawianie i usuwanie danych. B-drzewa są zbalansowanymi drzewami, co oznacza, że wysokość drzewa jest utrzymywana na stałym poziomie, co zapewnia efektywne operacje na danych.

2.  Drzewa AVL: Drzewa AVL są samobalansującymi drzewami binarnymi. Utrzymują równowagę poprzez automatyczne wykonywanie operacji rotacji w przypadku wystąpienia niezrównoważenia. Dzięki temu operacje na drzewie AVL są efektywne, zapewniając złożoność czasową O(log n).

3.  Drzewa B+ (B+-trees): Drzewa B+ są podobne do B-drzew, ale różnią się w pewnych aspektach. W drzewach B+ wszystkie rekordy są przechowywane w liściach, które są połączone listą. Ma to korzystny wpływ na operacje przeglądania danych sekwencyjnie.

4.  Haszowanie (Hashing): Algorytm haszowania przekształca klucz (wartość) na indeks za pomocą funkcji haszującej. To pozwala na bezpośrednie odwoływanie się do rekordu na podstawie wartości klucza. Haszowanie może być szybkie i skuteczne, ale może prowadzić do kolizji, gdy dwa różne klucze mają ten sam indeks haszujący.


Wybór konkretnego algorytmu zależy od wielu czynników, takich jak rozmiar bazy danych, rodzaj operacji wykonywanych na danych (wyszukiwanie, wstawianie, aktualizacja, usuwanie) oraz specyficzne wymagania dotyczące wydajności i optymalizacji systemu bazodanowego. Różne bazy danych i systemy zarządzania bazami danych (DBMS) mogą preferować różne algorytmy indeksowania w zależności od swoich cech i funkcji.
