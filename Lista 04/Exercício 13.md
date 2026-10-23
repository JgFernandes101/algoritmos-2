tipos
    PNo = ponteiro para TNo
    TNo = registro
            dado: real
            prox: PNo
    fim registro

função BContémA (listaA, listaB: PNo): lógico
var
    contem: lógico
    p: PNo
início
    contem <- VERDADEIRO
    p <- listaB
    enquanto listaA != NULO faça
        contem <- FALSO
        listaB <- p
        enquanto listaB != NULO e não contem faça
            se listaA^.dado = listaB^.dado então
                contem <- VERDADEIRO
            fim se
            listaB <- listaB^.prox
        fim enquanto
        se não contem então
            retorne FALSO
        fim se
        listaA <- listaA^.prox
    fim enquanto
    retorne contem
fim função             
