tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função removeDuplicata (ref lista: PNo): inteiro
var
    aux, aux2: PNo
    cont: inteiro
início
    se lista = NULO então
        retorne 0
    fim se
    cont <- 0
    aux <- lista
    aux2 <- aux^.prox
    se aux2 = NULO então
        retorne 0
    fim se
    enquanto aux2 != NULO faça
        se aux^.dado = aux2^.dado então
            cont <- cont + 1
            aux^.prox <- aux2^.prox
            desaloca(aux2)
            aux2 <- aux^.prox
        senão
            aux <- aux^.prox
            aux2 <- aux2^.prox
        fim se
    fim enquanto
    retorne cont
fim função
