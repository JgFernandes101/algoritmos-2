tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função XemListaOrdenada (x: real; lista: PNo): lógico
início
    enquanto lista != NULO faça
        se lista^.dado = x então
            retorne VERDADEIRO
        fim se
        se x < lista^.dado então
            retorne FALSO
        fim se
        lista <- lista^.prox
    fim enquanto
    retorne FALSO
fim função
