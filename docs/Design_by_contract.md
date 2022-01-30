The notion of a contract extends down to the method/procedure level; the contract for each method will normally contain the following pieces of information:[citation needed]

 - Acceptable and unacceptable input values or types, and their meanings
 - Return values or types, and their meanings
 - Error and exception condition values or types that can occur, and their meanings
 - Side effects
 - Preconditions
 - Postconditions
 - Invariants
 - (more rarely) Performance guarantees, e.g. for time or space used

Contract conditions should never be violated during execution of a bug-free program. Contracts are therefore typically only checked in debug mode during software development. Later at release, the contract checks are disabled to maximize performance.


Supported by few languages out of the box, implemented as library in many others
 - like in javascript AspectJS, jsContract etc.




----
PL

Głównym mechanizmem programowania kontraktowego jest weryfikacja danych przesyłanych do funkcji i jej wyniku.
Sprawdzanie danych wejściowych jest bardzo powszechną praktyką, stosowaną nawet w językach nie posiadających specjalnie przygotowanych do tego konstrukcji. Znacznie rzadsza jest kontrola zwracanej wartości. 

Za szczególny przypadek kontroli danych wyjściowych można uznać również test jednostkowy.

Najczęściej funkcję sprawdzającą poprawność kontraktu nazywamy `assert`
