tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
        prev: PNo
    fim registro

função inserir (ref lista: PNo; x: real; p: inteiro): lógico
var
    novo, aux: PNo
início
    se p < 1 então
        retorne FALSO
    fim se
    novo <- aloca(TNo)
    se novo = NULO então
        retorne FALSO
    fim se
    novo^.dado <- x
    se p = 1 então
        novo^.prox <- lista
        se lista != NULO então
            novo^.prev <- lista^.prev
            lista^.prev <- novo
        senão
            novo^.prev <- NULO
        fim se
        lista <- novo
        retorne VERDADEIRO
    fim se
    aux <- lista
    enquanto p > 1 faça
        se aux = NULO então
            desaloca(novo)
            retorne FALSO
        fim se
        se p = 2 então
            novo^.prox <- aux^.prox
            novo^.prev <- aux
            se aux^.prox != NULO então
                aux^.prox^.prev <- novo
            fim se
            aux^.prox <- novo
            retorne VERDADEIRO
        fim se
        p <- p - 1
        aux <- aux^.prox
    fim enquanto
fim função
