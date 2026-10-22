tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função XYNaLista (x, y: real; lista: PNo): lógico
var
    função BuscaY (y: real; lista: PNo): lógico
    início
        se lista = NULO então
            retorne FALSO
        fim se
        se lista^.dado = y então
            retorne VERDADEIRO
        fim se
        retorne BuscaY (y, lista^.prox)
    fim função
início
    se lista = NULO então
        retorne FALSO
    fim se
   se lista^.dado = x então
        retorne BuscaY (y, lista^.prox)
    fim se
    retorne XYNaLista (x, y, lista^.prox)
fim função    
