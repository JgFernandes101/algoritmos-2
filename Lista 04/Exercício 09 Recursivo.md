tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função xSeguidoDeY (x, y: real; lista: PNo): lógico
início
    se lista = NULO então
        retorne FALSO
    fim se
    se lista^.prox = NULO então
        retorne FALSO
    fim se
    se lista^.dado = x e lista^.prox^.dado = y então
        retorne VERDADEIRO
    fim se
    retorne xSeguidoDeY (x, y, lista^.prox)
fim função
