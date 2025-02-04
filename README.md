import string
lowers = string.ascii_lowercase
user_input = "Mr.Baez"
upper_indexes = []
for letter in range(len(user_input)):
    if user_input[letter] == user_input[letter].upper():
        upper_indexes.append(letter)
new = ""
rot = 13
for letter in user_input:
    if letter.lower() in string.ascii_lowercase:
        index = lowers.index(letter.lower())
        print(letter, index)
        new_letter = lowers[(index+rot-1)%26]
        new +=new_letter
    else:
        new+=letter
for letter in range(len(new)):
    if letter in upper_indexes:
        new = new[:letter] + new[letter].upper() + new[letter+1:]
        
print(new)
