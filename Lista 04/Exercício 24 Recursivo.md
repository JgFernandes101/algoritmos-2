tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função removeDuplicata (ref lista: PNo): inteiro
var
    aux: PNo
início
    se lista = NULO ou lista^.prox = NULO então
        retorne 0
    fim se
   se lista^.dado = lista^.prox^.dado então
        aux <- lista^.prox
        lista^.prox <- aux^.prox
        desaloca(aux)
        aux <- lista^.prox
        retorne 1 + removeDuplicata(lista)
    senão
        retorne 0 + removeDuplicata(lista^.prox)
    fim se
fim função
