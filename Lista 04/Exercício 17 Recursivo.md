tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função InserirOrdenadoSeNãoExiste (x: string; ref lista: PNo): lógico
var
    novo: PNo
    função auxiliar(x: string; ref lista: PNo): lógico
    início
        novo^.prox <- NULO
        se lista = NULO então
            lista <- novo
            retorne VERDADEIRO
        fim se
        se lista^.dado = x então
            desaloca(novo)
            retorne FALSO
        fim se
        se lista^.dado > x então
            novo^.prox <- lista
            lista <- novo
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
    retorne auxiliar(x, lista)
fim função
