tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função InserirEmP (ref lista: PNo; x: real; p: inteiro): lógico
var
    ant, aux, novo: PNo
início
    ant <- NULO
    aux <- lista
    enquanto p > 1 e aux != NULO faça
        p <- p - 1
        ant <- aux
        aux <- aux^.prox
    fim enquanto
    se p = 1 então
        novo <- aloca(TNo)
        se novo = NULO então
            retorne FALSO
        fim se
        novo^.dado <- x
        novo^.prox <- aux
        se ant = NULO então
            lista <- novo
        senão
            ant^.prox <- novo
        fim se
        retorne VERDADEIRO
    fim se
    retorne FALSO
fim função
