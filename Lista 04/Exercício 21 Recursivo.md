tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função remover(ref lista: PNo; p: inteiro): lógico
var
    aux: PNo
início
    se p < 1 ou lista = NULO então
        retorne FALSO
    fim se
    se p = 1 então
        aux <- lista
        lista <- lista^.prox
        desaloca(aux)
        retorne VERDADEIRO
    fim se
    retorne remover(lista^.prox, p-1)
fim função
