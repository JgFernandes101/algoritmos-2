tipos
    TNo = registro
            dado: real
            prox: ponteiro para TNo
    fim registro
    PNo = ponteiro para TNo

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
