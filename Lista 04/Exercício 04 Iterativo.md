tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função QuantasVezesXEmLista (x: real; lista: PNo): inteiro
var
    contador: inteiro
início
    contador <- 0
    enquanto lista != NULO faça
        se lista^.dado = x então
            contador <- contador + 1
        fim se
        lista <- lista^.prox
    fim enquanto
    retorne contador
fim função
