tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função InserirXNoFinal (x: string; ref lista: PNo): lógico
var
    novo, aux: PNo
início
    novo <- aloca(TNo)
    se novo = NULO então
        retorne FALSO
    fim se
    novo^.dado <- x
    novo^.prox <- NULO
    se lista = NULO então
        lista <- novo
        retorne VERDADEIRO
    fim se
    aux <- lista
    enquanto aux^.prox != NULO faça
        aux <- aux^.prox
    fim enquanto
    aux^.prox <- novo
    retorne VERDADEIRO
fim função
