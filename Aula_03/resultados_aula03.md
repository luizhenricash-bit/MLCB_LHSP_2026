--- RESULTADOS DO LAB 01 (AULA 03) ---
Mensagem: 'Preciso urgente da segunda via da fatura'
Intenção Predita: [segunda_via]
Vocabulário Filtrado (sem stopwords): ['2a', '2a via', 'aberto', 'acordo', 'acordo pagar', 'alterar', 'alterar endereço', 'app', 'atrasada', 'atualizo', 'atualizo dados', 'boleto', 'cadastramento', 'dados', 'dados residenciais', 'débito', 'débito aberto', 'dívida', 'emitir', 'emitir segunda', 'endereço', 'endereço cadastramento', 'fatura', 'fatura atrasada', 'fazer', 'fazer um', 'gostaria', 'gostaria alterar', 'negociar', 'negociar pagamento', 'no', 'no app', 'onde', 'onde atualizo', 'pagamento', 'pagamento dívida', 'pagar', 'pagar débito', 'posso', 'posso emitir', 'residenciais', 'residenciais no', 'segunda', 'segunda via', 'um', 'um acordo', 'via', 'via boleto', 'via fatura']

#========== PRODUÇÃO DO RELATÓRIO:==============
# 1 - Qual o impacto da remoção de stopwords no tamanho do vocabulário do modelo? R= Que a máquina terá um vocabulário menor, porém mais direto
# 2 - O que significa a configuração ngram_range=(1, 2) no TfidfVectorizer? R= define o tamanho da sequência de palavras que serão consideradas
# 3 - Como a remoção de palavras genéricas ajuda a evitar classificações incorretas? R= pois pode ter palavras com mais sentidos oque pode confundir a máquina com palavras genéricas que tem diferentes intenções.


--- RESULTADOS DO LAB 02 (AULA 03) ---

--- Relatório de Classificação ---
                     precision    recall  f1-score   support

horario_atendimento       0.50      1.00      0.67         1
        localizacao       0.00      0.00      0.00         1
    troca_devolucao       0.00      0.00      0.00         1

           accuracy                           0.33         3
          macro avg       0.17      0.33      0.22         3
       weighted avg       0.17      0.33      0.22         3

--- Matriz de Confusão ---
[[1 0 0]
 [1 0 0]
 [0 1 0]]

 #========== PRODUÇÃO DO RELATÓRIO:==============
# 1 - O que representam as métricas Precision, Recall e F1-Score no relatório? R= Medir a precisão das previsões positivas
# 2 - Como interpretar a diagonal principal da Matriz de Confusão? R=  da esquerda para direita que ficaria 1,0,0 
# 3 - Por que a acurácia isolada pode ser enganosa quando temos classes desbalanceadas? R= pois algumas classes podem ter mais exemplos, gerando confusão para a máquina

--- RESULTADOS DO LAB 03 (AULA 03) ---

Acuracia via Pipeline: 0.00%

import pandas as pd
from sklearn.pipeline import Pipeline
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

dados_rh = {
    'mensagem': [
        'Como solicitar minhas ferias?',
        'Quero agendar meu periodo de ferias',
        'Onde baixo meu holerite do mes?',
        'Preciso do comprovante de rendimentos',
        'Como cadastrar meu atestado medico?',
        'Onde envio o atestado de consulta?'
    ],
    'intencao': [
        'solicitar_ferias',
        'solicitar_ferias',
        'obter_holerite',
        'obter_holerite',
        'enviar_atestado',
        'enviar_atestado'
    ]
}

df3 = pd.DataFrame(dados_rh)

# TODO 1
X = df3['mensagem']
y = df3['intencao']

# TODO 2
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.33,
    random_state=42
)

# TODO 3
pipeline = Pipeline([
    ('vectorizer', TfidfVectorizer(
        stop_words=['de', 'o', 'meu', 'minhas']
    )),
    ('classifier', LogisticRegression())
])

# TODO 4
pipeline.fit(X_train, y_train)

# TODO 5
predicoes = pipeline.predict(X_test)

print(
    f"Acuracia via Pipeline: "
    f"{accuracy_score(y_test, predicoes) * 100:.2f}%"
)

# 1 - Cole o código corrigido e a acurácia obtida.
# 2 - Qual é a grande vantagem de utilizar o objeto Pipeline no Scikit-Learn? - R= para organizar e automatizar todas as etapas do processo Machine Learning em uma sequência.
# 3 - Por que o Pipeline evita que erros de pré-processamento ocorram entre treino e teste? R= O Pipeline garante que o mesmo pré-processamento aprendido durante o treinamento seja utilizado corretamente nos dados de teste.
# Todos os resultados devem ser inseridos no arquivo resultados_aula03.md

