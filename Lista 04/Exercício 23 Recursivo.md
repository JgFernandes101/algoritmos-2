tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: string
        prox: PNo
    fim registro

função RemoverMaiorOuIgual (ref lista: PNo; x: string): lógico
var
    aux: PNo
    removido: lógico
início
    se lista = NULO então
        retorne FALSO
    fim se
    se lista^.dado >= x então
        aux <- lista
        lista <- lista^.prox
        desaloca(aux)
        removido <- RemoverMaiorOuIgual(lista, x)
        retorne VERDADEIRO
    senão
        retorne RemoverMaiorOuIgual(lista^.prox, x)
    fim se
fim função
