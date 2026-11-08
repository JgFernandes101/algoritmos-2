tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função removerPrimeiroX (ref lista: PNo; x: string): lógico
var
    aux, aux2: PNo
início
    se lista = NULO então
        retorne FALSO
    fim se
    aux <- lista
    se lista^.dado = x então
        lista <- lista^.prox
        desaloca(aux)
        retorne VERDADEIRO
    fim se
    enquanto aux^.prox != NULO então
        aux2 <- aux
        aux <- aux^.prox
        se aux^.dado = x então
            aux2^.prox <- aux^.prox
            desaloca(aux)
            retorne VERDADEIRO
        fim se
    fim enquanto
    retorne FALSO
fim função
