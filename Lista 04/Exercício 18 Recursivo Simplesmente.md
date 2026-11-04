tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função InserirEmP (ref lista: PNo; x: real; p: inteiro): lógico
var
    novo: PNo
início
    se p < 1 então
        retorne FALSO
    fim se
    se p > 1 e lista = NULO então
        retorne FALSO
    fim se
    se p = 1 então
        novo <- aloca(TNo)
        se novo = NULO então
            retorne FALSO
        fim se
        novo^.dado <- x
        novo^.prox <- lista
        lista <- novo
        retorne VERDADEIRO
    fim se
    retorne InserirEmP(lista^.prox, x, p-1)
fim função
