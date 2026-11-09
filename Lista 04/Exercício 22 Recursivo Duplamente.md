tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
        prev: PNo
    fim registro

função Remover1x (ref lista: PNo; x: string): lógico
var
    aux: PNo
início
    se lista = NULO então
        retorne FALSO
    fim se
    se lista^.dado = x então
        se lista^.prox = NULO então
            se lista^.prev = NULO então
                aux <- lista
                desaloca(aux)
                lista <- NULO
                retorne VERDADEIRO
            senão
                aux <- lista
                lista <- lista^.prev
                lista^.prox <- aux^.prox
                desaloca(aux)
                retorne VERDADEIRO
            fim se
        fim se
        aux <- lista
        se lista^.prev != NULO então
            lista <- lista^.prev
            lista^.prox <- aux^.prox
            aux^.prox^.prev <- lista
            desaloca(aux)
            retorne VERDADEIRO
        senão
            lista <- lista^.prox
            lista^.prev <- NULO
            desaloca(aux)
            retorne VERDADEIRO
        fim se
    fim se
    retorne Remover1x(lista^.prox, x)
fim função
