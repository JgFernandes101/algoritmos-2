tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função QualMaiorString (lista: PNo): string
var
    maior: string
início
    se lista = NULO então
        retorne ""
    fim se
    maior <- lista^.dado
    enquanto lista != NULO faça
        se lista^.dado > maior então
            maior <- lista^.dado
        fim se
        lista <- lista^.prox
    fim enquanto
    retorne maior
fim função
