tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: inteiro
        prox: PNo
    fim registro

procedimento separar(lista: PNo; ref pares, impares: PNo)
var
    ultP, ultI: PNo
    ok: lógico

    função processar(p: PNo; ref pares, impares, ultP, ultI: PNo): lógico
    var
        novo: PNo
    início
        se p = NULO então
            retorne VERDADEIRO
        fim se
        novo <- aloca(TNo)
        se novo = NULO então
            retorne FALSO
        fim se
        novo^.dado <- p^.dado
        novo^.prox <- NULO
        se p^.dado mod 2 = 0 então
            se pares = NULO então
                pares <- novo
            senão
                ultP^.prox <- novo
            fim se
            ultP <- novo
        senão
            se impares = NULO então
                impares <- novo
            senão
                ultI^.prox <- novo
            fim se
            ultI <- novo
        fim se
        retorne processar(p^.prox, pares, impares, ultP, ultI)
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
    pares <- NULO
    impares <- NULO
    ultP <- NULO
    ultI <- NULO
    ok <- processar(lista, pares, impares, ultP, ultI)
    se não ok então
        limpar(pares)
        limpar(impares)
        pares <- NULO
        impares <- NULO
    fim se
fim procedimento
