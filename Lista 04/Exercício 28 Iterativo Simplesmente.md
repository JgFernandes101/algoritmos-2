tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função merge(lista1, lista2: PNo): PNo
var
    copia, ultimo, novo, aux: PNo
início
    copia <- NULO
    enquanto lista1 != NULO ou lista2 != NULO faça
        novo <- aloca(TNo)
        se novo = NULO então
            enquanto copia != NULO faça
                aux <- copia
                copia <- copia^.prox
                desaloca(aux)
            fim enquanto
            retorne NULO
        fim se
        se lista2 = NULO ou
           (lista1 != NULO e lista1^.dado <= lista2^.dado) então
            novo^.dado <- lista1^.dado
            lista1 <- lista1^.prox
        senão
            novo^.dado <- lista2^.dado
            lista2 <- lista2^.prox
        fim se
        novo^.prox <- NULO
        se copia = NULO então
            copia <- novo
        senão
            ultimo^.prox <- novo
        fim se
        ultimo <- novo
    fim enquanto
    retorne copia
fim função
