tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função removerPrimeiroX (ref lista: PNo; x: string): lógico
var
    aux: PNo
início
    se lista = NULO então
        retorne FALSO
    fim se
    se lista^.dado = x então
        aux <- lista
        lista <- lista^.prox
        desaloca(aux)
        retorne VERDADEIRO
    fim se
    retorne removerPrimeiroX(lista^.prox, x)
fim função
