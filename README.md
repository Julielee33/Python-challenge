# Python-challenge
#Homework
import csv
import statistics
PyPollpath = r"C:Desktop\UCDSAC201902DATA4\03-Python\Homework\Instruction\PyPoll\Resources\election_data.csv"

with open(PyPollpath, newline='') as PypollCSV:
    Pypoll = csv.reader(PypollCSV, delimiter = ",")
    PyPheader = next(Pypoll, None)
    
    voteIDs=[]
    candidates=[]
    for row in Pypoll:
        candidates.append(row[2])
    
    canlist = list(dict.fromkeys(candidates))
        
    old_winner = 0
    winner = str()
    for i in canlist:
        if candidates.count(i) > old_winner:
            winner = i
            old_winner = candidates.count(i)
    
    print(f'Election  Results')
    print(f'Total Votes: {len(candidates)}')
    print(f'{canlist[0]}: {round(candidates.count(canlist[0])/len(candidates)*100,2)}% ({candidates.count(canlist[0])})')
    print(f'{canlist[1]}: {round(candidates.count(canlist[1])/len(candidates)*100,2)}% ({candidates.count(canlist[1])})')
    print(f'{canlist[2]}: {round(candidates.count(canlist[2])/len(candidates)*100,2)}% ({candidates.count(canlist[2])})')
    print(f'{canlist[3]}: {round(candidates.count(canlist[3])/len(candidates)*100,2)}% ({candidates.count(canlist[3])})')
    print(f'Winner: {winner}')







