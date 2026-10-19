tipos
    TNo = registro
            dado: real
            prox: ponteiro para TNo
        fim registro
    PNo = ponteiro para TNo

função TamanhoLista (lista: PNo): inteiro
var
    contador: inteiro
    aux: PNo
início
    contador <- 0
    aux <- lista
    enquanto aux != NULO faça
        contador <- contador + 1
        aux <- aux^.prox
    fim enquanto
    retorne contador
fim função
        
