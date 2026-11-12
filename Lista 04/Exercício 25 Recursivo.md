tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

procedimento ulti2prim (ref lista: PNo)
var
    aux: PNo
início
    se lista != NULO então
        se lista^.prox != NULO então
            ulti2prim(lista^.prox)
            aux <- lista^.prox
            lista^.prox <- aux^.prox
            aux^.prox <- lista
            lista <- aux
        fim se
    fim se
fim procedimento
