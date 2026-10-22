tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função XYNaLista (x, y: real; lista: PNo): lógico
início
    enquanto lista != NULO faça
        se lista^.dado = x então
            lista <- lista^.prox
            enquanto lista != NULO faça
                se lista^.dado = y então
                    retorne VERDADEIRO
                fim se
                lista <- lista^.prox
            fim enquanto
            retorne FALSO
        fim se
        lista <- lista^.prox
    fim enquanto
    retorne FALSO
fim função
