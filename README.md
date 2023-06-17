import csv
import matplotlib.pyplot as plt
import pandas as pd

df = pd.read_csv("data.CSV", encoding='cp949')
ml = df['승률'].values.tolist()
print(ml)
import csv
import matplotlib.pyplot as plt

player_stats = {}  

with open('data.csv') as f:
    data = csv.reader(f)
    next(data)  #

    for row in data:
        player = row[0]  
        kills = int(row[1])  
        assists = int(row[2])  
        deaths = int(row[3])  
       

        
        player_stats[player] = {'kills': kills, 'assists': assists, 'deaths': deaths}


players = list(player_stats.keys())  
kills = [player_stats[player]['K'] for player in players]  
assists = [player_stats[player]['A'] for player in players]  
deaths = [player_stats[player]['D'] for player in players]  


plt.bar(players, kills)
plt.xlabel('선수')
plt.ylabel('K')
plt.title('Player Kill Comparison')
plt.show()


plt.bar(players, assists)
plt.xlabel('선수')
plt.ylabel('A')
plt.title('Player Assist Comparison')
plt.show()


plt.bar(players, deaths)
plt.xlabel('선수')
plt.ylabel('Deaths')
plt.title('Player Death Comparison')
plt.show()
