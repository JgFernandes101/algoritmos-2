tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
        prev: PNo
    fim registro

função Inserir (ref lista: PNo; x: real; p: inteiro): lógico
var
    novo: PNo
início
    se p < 1 ou (p > 1 e lista = NULO) então
        retorne FALSO
    fim se
    se p = 1 então
        novo <- aloca(TNo)
        se novo = NULO então
            retorne FALSO
        fim se
        novo^.dado <- x
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
    se p = 2 então
        novo <- aloca(TNo)
        se novo = NULO então
            retorne FALSO
        fim se
        novo^.dado <- x
        novo^.prox <- lista^.prox
        novo^.prev <- lista
        se lista^.prox != NULO então
            lista^.prox^.prev <- novo
        fim se
        lista^.prox <- novo
        retorne VERDADEIRO
    fim se
    retorne Inserir (lista^.prox, x, p-1)
fim função
