tipos
    TNo = registro
            dado: real
            prox: ponteiro para TNo
    fim registro
    PNo = ponteiro para TNo

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
