tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função xSeguidoDeY (x, y: real; lista: PNo): lógico
início
    enquanto lista != NULO faça
        se lista^.prox = NULO então
            retorne FALSO
        fim se
        se lista^.dado = x então
            se lista^.prox^.dado = y então
                retorne VERDADEIRO
            fim se
        fim se
        lista <- lista^.prox
    fim enquanto
    retorne FALSO
fim função
