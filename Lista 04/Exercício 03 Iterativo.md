tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: reais
            prox: PNo
    fim registro

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
