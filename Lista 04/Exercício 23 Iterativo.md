tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função RemoverMaiorOuIgual (ref lista: PNo; x: string): lógico
var
    aux, aux2: PNo
    removido: lógico
início
    se lista = NULO então
        retorne FALSO
    fim se
    se lista^.dado >= x e lista^.prox = NULO então
        aux <- lista
        lista <- lista^.prox
        desaloca(aux)
        retorne VERDADEIRO
     fim se
    removido <- FALSO
    enquanto lista != NULO faça
        se lista^.dado < x então
            pare
        fim se
        aux2 <- lista
        lista <- lista^.prox
        desaloca(aux2)
        removido <- VERDADEIRO
    fim enquanto
    aux <- lista
    se lista = NULO então
        retorne removido
    fim se
    enquanto aux^.prox != NULO então
        aux2 <- aux^.prox
        se aux2^.dado >= x então
            aux^.prox <- aux2^.prox
            desaloca(aux2)
            removido <- VERDADEIRO
        senão
            aux <- aux^.prox
        fim se
    fim enquanto
    retorne removido
fim função
