tipos 
    PNo = ponteiro para TNo
    TNo = registro
            dado: string
            prox: PNo   
     fim registro

função StringNaPosiçãoP (p: inteiro; lista: PNo): string
início
    se lista = NULO então
        retorne ""
    fim se
    se p <= 0 então
        retorne ""
    fim se
    se p = 1 então
        retorne lista^.dado
    fim se
    retorne StringNaPosiçãoP(p-1, lista^.prox)
fim função
