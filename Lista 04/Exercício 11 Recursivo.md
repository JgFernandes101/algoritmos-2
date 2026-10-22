tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função XemListaOrdenada (x: real; lista: PNo): lógico
início
    se lista = NULO então
        retorne FALSO
    fim se
    se lista^.dado = x então
        retorne VERDADEIRO
    senão
        se lista^.dado > x então
            retorne FALSO
        fim se
    fim se
    retorne XemListaOrdenada(x, lista^.prox)
fim função
