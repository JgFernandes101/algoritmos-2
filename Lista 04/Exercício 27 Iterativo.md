tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função duplicar (lista: PNo): PNo
var
    novo, ultimo, copia, aux: PNo
início
    se lista = NULO então
        retorne NULO
    fim se
    copia <- NULO
    enquanto lista != NULO faça
        novo <- aloca(TNo)
        se novo = NULO então
            se copia != NULO então
                enquanto copia != NULO faça
                    aux <- copia
                    copia <- copia^.prox
                    desaloca(aux)
                fim enquanto
            fim se
        retorne NULO         
        senão
            novo^.dado <- lista^.dado
            novo^.prox <- NULO
            se copia = NULO então
                copia <- novo
                ultimo <- novo
            senão
                ultimo^.prox <- novo
                ultimo <- novo
            fim se
        fim se
        lista <- lista^.prox
    fim enquanto
    retorne copia
fim função          
