tipos
    PNo = ponteiro para TNo
    TNo = registro
        dado: real
        prox: PNo
    fim registro

função inverter(ref lista: PNo): lógico
var
    ant, atual, post: PNo
início
   se lista = NULO ou lista^.prox = NULO então
        retorne FALSO
    fim se
    ant <- NULO
    atual <- lista
    enquanto atual != NULO faça
        post <- atual^.prox
        atual^.prox <- ant
        ant <- atual
        atual <- post
    fim enquanto
    lista <- ant
    retorne VERDADEIRO
fim função
