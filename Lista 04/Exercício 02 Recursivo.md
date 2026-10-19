tipos
    TNo = registro
            dado: real
            prox: ponteiro para TNo
        fim registro
    PNo = ponteiro para TNo

função TamanhoLista (lista: PNo): inteiro
início
    se lista = NULO então
        retorne 0
    fim se
    retorne 1 + TamanhoLista(lista^.prox)
fim função
        
