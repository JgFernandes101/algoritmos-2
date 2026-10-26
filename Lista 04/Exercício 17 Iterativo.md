tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo
    fim registro

função InserirOrdenadoNãoExiste (x: string; ref lista: PNo): lógico
var
    aux, novo: PNo
início
    novo <- aloca(TNo)
    se novo = NULO então
        retorne FALSO
    fim se
    novo^.dado <- x
    novo^.prox <- NULO
    se lista = NULO então
        lista <- novo
        retorne VERDADEIRO
    fim se
    se lista^.dado > x então
        novo^.prox <- lista
        lista <- novo
        retorne VERDADEIRO
    fim se
    aux <- lista
    enquanto aux != NULO faça
        se aux^.dado = x então
            desaloca(novo)
            retorne FALSO
        fim se
        se aux^.prox = NULO então
            aux^.prox <- novo
            retorne VERDADEIRO
        fim se
        se aux^.dado < x e aux^.prox^.dado > x então
            novo^.prox <- aux^.prox
            aux^.prox <- novo
            retorne VERDADEIRO
        fim se
        aux <- aux^.prox
    fim enquanto
fim função            
                    
    
        
