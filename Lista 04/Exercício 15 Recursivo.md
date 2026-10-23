tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

  função InserirXNoFinal (x: string; ref lista: PNo): lógico
    var
        novo: PNo
  início
    se lista = NULO então
        novo <- aloca(TNo)
        se novo = NULO então
            retorne FALSO
        fim se
        novo^.dado <- x
        novo^.prox <- NULO
        lista <- novo
        retorne VERDADEIRO
    fim se
    retorne InserirXNoFinal(x, lista^.prox)
fim função
