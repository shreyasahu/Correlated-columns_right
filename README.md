# Correlated-columns_right
function for finding correlated columns

    def correlation(dataset, threshold):
      col_corr = set()
      corr_matrix = dataset.corr()
      for i in range(len(corr_matrix.columns)):
          for j in range(i):
              if abs(corr_matrix.iloc[i, j]) > threshold: 
                  colname = corr_matrix.columns[i]  
                  col_corr.add(colname)
      return col_corr

  corr_features = correlation(df, 0.8)
  print('correlated features: ', len(set(corr_features)) )
