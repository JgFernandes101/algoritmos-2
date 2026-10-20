tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: inteiro
            prox: PNo
    fim registro

função MediaLista (lista: PNo): real
var
    i, soma: inteiro
início
    se lista = NULO então
        retorne 0
    fim se
    soma <- 0
    i <- 0
    enquanto lista != NULO faça
        soma <- soma + lista^.dado
        i <- i + 1
        lista <- lista^.prox
    fim enquanto
    retorne soma/i
fim função
