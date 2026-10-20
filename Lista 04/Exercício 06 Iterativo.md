tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função StringNaPosiçãoP (p: inteiro; lista: PNo): string
var
    i, tam: inteiro
    aux: PNo
início
    aux <- lista
    tam <- 0
    se lista = NULO então
        retorne ""
    fim se
    enquanto aux != NULO faça
        tam <- tam + 1
        aux <- aux^.prox
    fim enquanto
    se p > tam ou p <= 0 então
        retorne ""
    fim se
    i <- 1
    enquanto i < p faça
        lista <- lista^.prox
        i <- i + 1
    fim enquanto
    retorne lista^.dado
fim função    
