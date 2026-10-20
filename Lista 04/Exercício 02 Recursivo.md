tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: reais
            prox: PNo
    fim registro

função TamanhoLista (lista: PNo): inteiro
início
    se lista = NULO então
        retorne 0
    fim se
    retorne 1 + TamanhoLista(lista^.prox)
fim função
        
