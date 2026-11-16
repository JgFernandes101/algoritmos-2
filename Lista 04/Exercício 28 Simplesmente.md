tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função merge(lista1, lista2: PNo): PNo
var
    resultado: PNo
    erro: lógico
    função juntar(a, b: PNo; ref erro: lógico): PNo
    var
        novo: PNo
    início
        se a = NULO e b = NULO então
            retorne NULO
        fim se
        novo <- aloca(TNo)
        se novo = NULO então
            erro <- VERDADEIRO
            retorne NULO
        fim se
        se a = NULO então
            novo^.dado <- b^.dado
            novo^.prox <- juntar(a, b^.prox, erro)
        senão
            se b = NULO então
                novo^.dado <- a^.dado
                novo^.prox <- juntar(a^.prox, b, erro)
            senão
                se a^.dado <= b^.dado então
                    novo^.dado <- a^.dado
                    novo^.prox <- juntar(a^.prox, b, erro)
                senão
                    novo^.dado <- b^.dado
                    novo^.prox <- juntar(a, b^.prox, erro)
                fim se
            fim se
        fim se
        se erro então
            desaloca(novo)
            retorne NULO
        fim se
        retorne novo
    fim função
início
    erro <- FALSO
    resultado <- juntar(lista1, lista2, erro)
    retorne resultado
fim função
