tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função Somar2Nós (ref lista: PNo; p: inteiro): lógico
var
    aux, aux2: PNo
início
    se lista = NULO ou lista^.prox = NULO então
        retorne FALSO
    fim se
    aux <- lista^.prox
    aux2 <- lista
    enquanto aux^.prox != NULO e p > 1 faça
        aux <- aux^.prox
        aux2 <- aux2^.prox
        p <- p - 1
    fim enquanto
    se p = 1 então
        aux2^.dado <- aux2^.dado + aux^.dado
        aux2^.prox <- aux^.prox
        desaloca(aux)
        retorne VERDADEIRO
    senão
        retorne FALSO
    fim se
fim função
