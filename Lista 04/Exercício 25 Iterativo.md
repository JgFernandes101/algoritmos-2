tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

procedimento ulti2prim (ref lista: PNo)
var
    aux, aux2: PNo
início
    aux <- lista
    se lista != NULO então
        se aux^.prox != NULO então
            enquanto aux^.prox != NULO faça
                se aux^.prox^.prox = NULO então
                    aux2 <- aux
                fim se
                aux <- aux^.prox
            fim enquanto
            aux^.prox <- lista
            aux2^.prox <- NULO
            lista <- aux
        fim se
    fim se
fim procedimento
