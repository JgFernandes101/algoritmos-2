tipos
    TNo = registro
            dado: real
            prox: ponteiro para TNo
        fim registro
    PNo = ponteiro para TNo

função EstáEmLista (x: real; lista: PNo): lógico
início
    se lista = NULO então
        retorne FALSO
    senão
        se lista^.dado = x então
            retorne VERDADEIRO
        fim se
    fim se
    retorne EstáEmLista(x, lista^.prox)
fim função
