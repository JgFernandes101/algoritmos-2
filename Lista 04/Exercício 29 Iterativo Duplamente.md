tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: inteiro
        ant: PNo
        prox: PNo
    fim registro

procedimento separar(lista: PNo; ref pares, impares: PNo)
var
    ultP, ultI, novo, aux: PNo
    erro: lógico
início
    pares <- NULO
    impares <- NULO
    ultP <- NULO
    ultI <- NULO
    erro <- FALSO
    enquanto lista != NULO e não erro faça
        novo <- aloca(TNo)
        se novo = NULO então
            erro <- VERDADEIRO
        senão
            novo^.dado <- lista^.dado
            novo^.prox <- NULO
            se lista^.dado mod 2 = 0 então
                novo^.ant <- ultP
                se pares = NULO então
                    pares <- novo
                senão
                    ultP^.prox <- novo
                fim se
                ultP <- novo
            senão
                novo^.ant <- ultI
                se impares = NULO então
                    impares <- novo
                senão
                    ultI^.prox <- novo
                fim se
                ultI <- novo
            fim se
            lista <- lista^.prox
        fim se
    fim enquanto
    se erro então
        enquanto pares != NULO faça
            aux <- pares
            pares <- pares^.prox
            desaloca(aux)
        fim enquanto
        enquanto impares != NULO faça
            aux <- impares
            impares <- impares^.prox
            desaloca(aux)
        fim enquanto
    fim se
fim procedimento
