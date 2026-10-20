tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro
    
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
        
