# HackThisSite Programming mission 1
# Download wordlist.txt 
# Copy scrambled words and save as inputlist.txt, same directory
# Python 3 to unscramble
wordlist = []
scrambledlist = []
inputlist = []
finallist = []

wordlistfile = open(r'C:\Users\Sandra\kta22e\VeebirakendusteTurvalisus\wordlist.txt', 'r+')
wordlist_n = wordlistfile.readlines()
for word_n in wordlist_n:
    temp_list_word_n = [letter for letter in word_n]
    if temp_list_word_n.count('\n') != 0:
        temp_list_word_n.remove('\n')
    temp_word = ''.join(temp_list_word_n)
    wordlist.append(temp_word)

for word in wordlist:
    temp_list_word = [letter for letter in word]
    temp_list_word.sort()
    temp_word = ''.join(temp_list_word)
    scrambledlist.append(temp_word)

print("Wordlist")
print("---------------")
print(wordlist)

print("Scrambledlist")
print("---------------")
print(scrambledlist)

inputfile = open(r'C:\Users\Sandra\kta22e\VeebirakendusteTurvalisus\inputlist.txt', 'r+')
inputlist_n = inputfile.readlines()
for word_n in inputlist_n:
    temp_list_word_n = [letter for letter in word_n]
    if temp_list_word_n.count('\n') != 0:
        temp_list_word_n.remove('\n')
    if temp_list_word_n.count('\t') != 0:
        temp_list_word_n.remove('\t')
    temp_list_word_n.sort()
    temp_word = ''.join(temp_list_word_n)
    inputlist.append(temp_word)

no_of_blanks = inputlist.count("")
i = 1
while i <= no_of_blanks:
    inputlist.remove("")
    i += 1

print("Inputlist")
print("---------------")
print(inputlist)

for word in inputlist:
    final_word = wordlist[scrambledlist.index(word)]
    finallist.append(final_word)

print("Finallist")
print("---------------")
print(finallist)

answer = ', '.join(finallist)

print("Answer")
print("---------------")
print(answer)

testword = input("(Press Enter to Quit)")
