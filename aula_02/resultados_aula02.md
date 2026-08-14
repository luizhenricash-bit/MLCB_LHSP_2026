--- RESULTADOS DO LAB 01 ---
Mensagem: 'Quero consultar quanto dinheiro tenho' ==> Intenção Predita: [fazer_pix]
Mensagem: 'Pode me ajudar a fazer um pix?' ==> Intenção Predita: [fazer_pix]
Mensagem: 'Gostaria de cancelar meu cartão de crédito' ==> Intenção Predita: [cancelar_conta]

#========== PRODUÇÃO DO RELATÓRIO:==============
# Para a entrega completa deste LAB01 você precisa copiar a saída do código (output) e adicionar as repostas das perguntas abaixo:
# 1 - Avaliem os resultados e verifiquem se os resultados foram corretos ou incorretos. Coloque a resposta no arquivo do relatório do laboratório - R= foi parcialmente correto.
# 2 - Detectado algum erro, qual seria a maneira mais correta de melhorar o resultado do algoritmo? - R=  aumentar o dataset, e criar mais intenções e mais exemplos pra intenção
# 3 - Detalhe a função do LogisticRegression no algorítmo. R=  ele aprende a relação das palavras e intenções 


--- RESULTADOS DO LAB 02 ---
--- RESULTADOS DO LAB 02 ---
Mensagem de Teste: 'Gostaria de devolver o produto que comprei'
Intenção Predita: troca_devolucao

--- Distribuição de Probabilidades por Classe ---
Classe [duvida_frete]: 27.99%
Classe [rastrear_pedido]: 24.54%
Classe [troca_devolucao]: 47.46%

 Para a entrega completa deste LAB02 você precisa copiar a saída do código (output) e adicionar as repostas das perguntas abaixo:
# 1 - Avaliem os resultados e verifiquem se os resultados foram corretos ou incorretos. Coloque a resposta no arquivo do relatório do laboratório R= Corretos
# 2 - Detectado algum erro, qual seria a maneira mais correta de melhorar o resultado do algoritmo? R= não teve erros
# 3 - Detalhe a função do Naive Bayes no algorítmo. R= aprender com os exemplos do dataset


--- RESULTADOS DO LAB 03 ---
Acurácia do Modelo: 33.33%
========== PRODUÇÃO DO RELATÓRIO:==============
# Para a entrega completa deste LAB03 você precisa colar o código corrigido com os TODOs preenchidos, a acurácia obtida e responder:
# 1 - Qual foi a acurácia obtida pelo modelo no conjunto de teste e por que, em um dataset tão pequeno (9 exemplos), essa métrica pode ser enganosa? R= 33.33%, pode sim porque possui 9 exemplos no dataset e só três foram usadas
# 2 - Como o modelo de Árvore de Decisão (DecisionTreeClassifier) toma a decisão de separar as intenções do usuário? R= cria divisões para separar as inteções
# 3 - Qual é o risco de utilizar uma Árvore de Decisão sem limite de profundidade (max_depth) em datasets de texto maiores? R= porque ela iria criar multiplas  divisões muitas sem necessidade, deixando o modelo completo podendo gerar overfitting




