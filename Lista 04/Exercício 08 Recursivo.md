tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função QualMaiorString(lista: PNo): string
var
    maiorDoResto: string
início
    se lista = NULO então
        retorne ""
    fim se
    maiorDoResto <- QualMaiorString(lista^.prox)
    se lista^.dado > maiorDoResto então
        maiorDoResto <- lista^.dado
    fim se
    retorne maiorDoResto
fim função
