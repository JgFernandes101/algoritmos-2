tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função Somar2Nós (ref lista: PNo; p: inteiro): lógico
var
    aux: PNo
início
    se lista = NULO então
        retorne FALSO
    fim se
    se p = 1 e lista^.prox != NULO então
        lista^.dado <- lista^.dado + lista^.prox^.dado
        aux <- lista^.prox
        lista^.prox <- aux^.prox
        desaloca(aux)
        retorne VERDADEIRO
    fim se
    retorne Somar2Nós(lista^.prox, p-1)
fim função
