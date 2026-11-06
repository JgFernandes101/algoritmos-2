tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função RemoverÚltimo (ref lista: PNo): lógico
var
    aux: PNo
início
    se lista = NULO então
        retorne FALSO
    fim se
    aux <- lista
    se lista^.prox = NULO então
        desaloca(lista)
        lista <- NULO
        retorne VERDADEIRO
    fim se
    enquanto aux^.prox^.prox != NULO faça
        aux <- aux^.prox
    fim enquanto
    desaloca(aux^.prox)
    aux^.prox <- NULO
    retorne VERDADEIRO
fim função
