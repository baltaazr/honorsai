### [Home](index.html)

# Language Guesser: 
In this project, I made a program that detects the language of a certain text file by analyzing it's letter frequency and comparing it to the letter frequency of other languages.
For the letter frequency of other languages, I used this:
https://github.com/akleemans/letter-frequency/blob/master/letter_frequency.csv

## How I approached the project: 
I used Python for this project to practice the programming language. I used python dictionaries, arrays and loops to get this project done. I first stored the letter frequency of all the languages into a dictionary, then I stored the letter frequency of the text into another dictionary, I compared the letter frequency of the text with the letter frequency of the other languages and which ever language had the least difference, I outputted as the guess for the language that the text was written in.
 
## Reflection on the challenges I faced: 
My biggest challenge was being able to read the csv file containing the letter frequency of all the languages. For this, I used this website to help me read csv files in python.
https://realpython.com/python-csv/
```python
with open('letter-frequency.txt', encoding="utf-8") as csv_file:
    csv_reader = csv.DictReader(csv_file, delimiter=';')
    line_count = 0
    for row in csv_reader:
        if line_count == 0:
            for language in row:
                letterFrequency[language] = {}
        for language in row:
            letterFrequency[language][row['Letter']] = row[language]
```
