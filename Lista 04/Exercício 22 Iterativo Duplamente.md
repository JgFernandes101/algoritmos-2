tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
        prev: PNo
    fim registro

função Remover1x (ref lista: PNo; x: string): lógico
var
    aux, aux2: PNo
início
    se lista = NULO então
        retorne FALSO
    fim se
    aux <- lista
    se lista^.dado = x então
        lista <- lista^.prox
        se lista != NULO então
            lista^.prev <- NULO
        fim se
        desaloca(aux)
        retorne VERDADEIRO
    fim se
    enquanto aux^.prox != NULO então
        aux2 <- aux
        aux <- aux^.prox
        se aux^.dado = x então
            aux2^.prox <- aux^.prox
            se aux^.prox != NULO então
                aux^.prox^.prev <- aux2
            fim se
            desaloca(aux)
            retorne VERDADEIRO
        fim se
    fim enquanto
    retorne FALSO
fim função
