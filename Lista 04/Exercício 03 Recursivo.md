tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro
    
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
