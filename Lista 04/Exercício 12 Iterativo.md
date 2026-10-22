tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função ListasIguais (lista, lista2: PNo): lógico
início
    enquanto lista != NULO e lista2 != NULO faça
        se lista^.dado != lista2^.dado então
            retorne FALSO
        fim se
        lista <- lista^.prox
        lista2 <- lista2^.prox
    fim enquanto
    se (lista = NULO e lista2 != NULO) ou (lista != NULO e lista2 = NULO) então
        retorne FALSO
    fim se
    retorne VERDADEIRO
fim função
