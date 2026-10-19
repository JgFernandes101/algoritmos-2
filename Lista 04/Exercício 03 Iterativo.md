tipos
    TNo = registro
            dado: real
            prox: ponteiro para TNo
        fim registro
    PNo = ponteiro para TNo

função EstáEmLista (x: real; lista: PNo): lógico
início
    enquanto lista != NULO faça
        se lista^.dado = x então
            retorne VERDADEIRO
        fim se
        lista <- lista^.prox
    fim enquanto
    retorne FALSO
fim função
