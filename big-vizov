import numpy as np
import pandas

data = pandas.read_csv('test12.csv', sep=', ')
df = pandas.read_csv('uroki.csv', sep=',')

b = data['Appraisal'].mean(axis=0)

filter_worst = data['Appraisal'] == 2
filter_bad = data['Appraisal'] == 3
filter_good = data['Appraisal'] == 4
filter_best = data['Appraisal'] == 5

best = pandas.Series(data.loc[filter_best]['Theme'])
good = pandas.Series(data.loc[filter_good]['Theme'])
bad = pandas.Series(data.loc[filter_bad]['Theme'])
worst = pandas.Series(data.loc[filter_worst]['Theme'])

if not best.empty:
    print('Темы, которые ученик знает на "отлично":', *data.loc[filter_best]['Theme'].unique(), sep="; ")
if not good.empty:
    print('Темы, которые ученик знает на "хорошо":', *data.loc[filter_good]['Theme'].unique(), sep="; ")
if not bad.empty:
    print('Темы, которые ученик знает плохо:', *data.loc[filter_bad]['Theme'].unique(), sep="; ")
if not worst.empty:
    print('Темы, которые ученик не усваивает:', *data.loc[filter_worst]['Theme'].unique(), sep="; ")

print('Наиболее вероятна следующая оценка:', round(b))

df_filter_best = data.loc[best]['Theme'].unique()
print(pandas.Series(*df.loc[df_filter_best]['Тема']))

print('Рекомендуются к изучению следующие материалы: ')
