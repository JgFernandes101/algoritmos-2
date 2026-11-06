tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função remover (ref lista: PNo; p: inteiro): lógico
var
    aux, aux2: PNo
início
    se lista = NULO então
        retorne FALSO
    fim se
    se p < 1 então
        retorne FALSO
    fim se
    aux <- lista
    se p = 1 então
        lista <- lista^.prox
        desaloca(aux)
        retorne VERDADEIRO
    fim se
    se lista^.prox = NULO então
        retorne FALSO
    fim se
    enquanto p > 2 e aux^.prox^.prox != NULO faça
        p <- p - 1
        aux <- aux^.prox
    fim enquanto
    se aux^.prox^.prox = NULO então
        se p > 2 então
            retorne FALSO
        senão
            desaloca(aux^.prox)
            aux^.prox <- NULO
            retorne VERDADEIRO
        fim se
    senão
        aux2 <- aux^.prox
        aux^.prox <- aux2^.prox
        desaloca(aux2)
        retorne VERDADEIRO
    fim se
fim função      
