tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: inteiro
            prox: PNo
    fim registro

função InserirOrdenado (x: inteiro; ref lista: PNo): lógico
var
    novo: PNo
    função auxiliar (x: inteiro; ref lista: PNo): lógico
    início
        se lista^.prox != NULO e x >= lista^.dado e x <= lista^.prox^.dado então
            novo^.prox <- lista^.prox
            lista^.prox <- novo
            retorne VERDADEIRO
        fim se
        se lista^.prox = NULO e lista^.dado <= x então
            novo^.prox <- NULO
            lista^.prox <- novo
            retorne VERDADEIRO
        fim se
        retorne auxiliar(x, lista^.prox)
    fim função
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
    retorne auxiliar(x, lista)
fim função
    
