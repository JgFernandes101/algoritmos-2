tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função InserirXNoInício (x: string; ref lista: PNo): lógico
var
    novo: PNo
início
    novo <- aloca(TNo)
    se novo = NULO então
        retorne FALSO
    fim se
    novo^.dado <- x
    novo^.prox <- lista
    lista <- novo
    retorne VERDADEIRO
fim função
