tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: inteiro
        prox: PNo
    fim registro

função InserirOrdenado(x: inteiro; ref lista: PNo): lógico
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
    se x <= lista^.dado então
        novo^.prox <- lista
        lista <- novo
        retorne VERDADEIRO
    fim se
    aux <- lista
    enquanto aux^.prox != NULO faça
        se x <= aux^.prox^.dado então
            novo^.prox <- aux^.prox
            aux^.prox <- novo
            retorne VERDADEIRO
        fim se
        aux <- aux^.prox
    fim enquanto
    aux^.prox <- novo
    retorne VERDADEIRO
fim função
