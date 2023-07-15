import warnings
warnings.filterwarnings("ignore", category=FutureWarning)
warnings.filterwarnings("ignore", category=DeprecationWarning)
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('C:/Users/Knight2000/Desktop/GSM7577889_JB2_4.txt', delimiter='\t') 

sorted_data = data.sort_values(by='freq', ascending=False)

top_10_data = sorted_data.head(10)

plt.bar(top_10_data['cdr3aa'], top_10_data['freq'])
plt.xlabel('CDR3 AA Sequence')
plt.ylabel('Expression Frequency')
plt.title('Top 10 Gene Expressions')
plt.xticks(rotation=45, ha='right', fontsize=8)
plt.tight_layout()
plt.show()
