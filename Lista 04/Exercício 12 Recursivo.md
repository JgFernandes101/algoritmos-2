tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função ListasIguais(lista, lista2: PNo): lógico
início
    se lista = NULO e lista2 = NULO então
        retorne VERDADEIRO
    fim se
    se (lista != NULO e lista2 = NULO) ou (lista = NULO e lista2 != NULO) então
        retorne FALSO
    fim se
    se lista^.dado = lista2^.dado então
        retorne ListasIguais(lista^.prox, lista2^.prox)
    fim se
    retorne FALSO
fim função
