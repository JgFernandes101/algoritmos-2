tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função QuantasVezesXEmLista (x: real; lista: PNo): inteiro
início
    se lista = NULO então
        retorne 0
    fim se
    se lista^.dado = x então
        retorne 1 + QuantasVezesXEmLista(x, lista^.prox)
    fim se
    retorne QuantasVezesXEmLista(x, lista^.prox)
fim função
