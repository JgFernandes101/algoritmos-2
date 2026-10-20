tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função StringDoMeio (lista: PNo): string
var
    i, j: inteiro
    aux: PNo
início
    i <- 0
    aux <- lista
    se aux = NULO então
        retorne ""
    fim se
    enquanto aux != NULO faça
        i <- i + 1
        aux <- aux^.prox
    fim enquanto
    j <- 0
    enquanto j < (i-1) div 2 faça
        j <- j + 1
        lista <- lista^.prox
    fim enquanto
    retorne lista^.dado
fim função
