tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função inverter(ref lista: PNo): lógico
var

    procedimento inverterAux(atual: PNo; ref lista: PNo)
    início
        se atual^.prox = NULO então
            lista <- atual
        senão
            inverterAux(atual^.prox, lista)
            atual^.prox^.prox <- atual
            atual^.prox <- NULO
        fim se
    fim procedimento
        
início
    se lista = NULO então
        retorne FALSO
    fim se
    inverterAux(lista, lista)
    retorne VERDADEIRO
fim função
