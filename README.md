### Explicação dos passos do notebook

1. Carregar Dados  
   - Lê os arquivos principais (`results.csv`, `drivers.csv`, `races.csv`, `qualifying.csv`, `pit_stops.csv`).  
   - Mostra a dimensão dos dados carregados.

2. Label top 10
   - Cria a variável `top10`:  
     - `1` se a posição final do piloto for entre 1º e 10º.  
     - `0` caso contrário.

3. Features  
   - Gera variáveis, como:  
     - Posição de largada (`grid`)  
     - Ano da corrida (`year`)  
     - Idade do piloto na corrida (`driver_age`)  
     - Melhor posição no qualifying (`best_quali_pos`)  
     - Número de pit stops (`pit_stop_count`)  
     - Construtor (one-hot encoding dos 15 mais frequentes).  

4. Divisão
   - Divide os dados em treino (80%) e teste (20%), de forma estratificada.  
   - Escalona os atributos numéricos com `StandardScaler`.

5. Modelo  
   - Define uma rede neural Sequencial:  
   - Treina por 50 épocas com `batch_size=10`.

6. Avaliação  
   - Gera predições no conjunto de teste.  
   - Calcula:  
   - Accuracy  
   - F1-score  
   - Relatório de classificação (`precision`, `recall`, `f1`)  
   - Matriz de confusão (visualização).  