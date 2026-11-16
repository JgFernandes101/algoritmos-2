
tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        ant, prox: PNo
    fim registro

função merge(lista1, lista2: PNo): PNo
var
    cabeca, ultimo: PNo
    ok: lógico

    função juntar(a, b: PNo; ref cabeca, ultimo: PNo): lógico
    var
        novo: PNo
    início
        se a = NULO e b = NULO então
            retorne VERDADEIRO
        fim se
        novo <- aloca(TNo)
        se novo = NULO então
            retorne FALSO
        fim se
        novo^.ant <- ultimo
        novo^.prox <- NULO
        se a = NULO então
            novo^.dado <- b^.dado
            b <- b^.prox
        senão
            se b = NULO então
                novo^.dado <- a^.dado
                a <- a^.prox
            senão
                se a^.dado <= b^.dado então
                    novo^.dado <- a^.dado
                    a <- a^.prox
                senão
                    novo^.dado <- b^.dado
                    b <- b^.prox
                fim se
            fim se
        fim se
        se cabeca = NULO então
            cabeca <- novo
        senão
            ultimo^.prox <- novo
        fim se
        ultimo <- novo
        retorne juntar(a, b, cabeca, ultimo)
    fim função

    procedimento limpar(p: PNo)
    var
        seguinte: PNo
    início
        se p != NULO então
            seguinte <- p^.prox
            desaloca(p)
            limpar(seguinte)
        fim se
    fim procedimento

início
    cabeca <- NULO
    ultimo <- NULO
    ok <- juntar(lista1, lista2, cabeca, ultimo)
    se não ok então
        limpar(cabeca)
        retorne NULO
    fim se
    retorne cabeca
fim função
