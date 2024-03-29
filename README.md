# 20-Chr-Passwords-Generator
Take a dictionary word list and create a unique 20chr Password
import itertools

def generate_passwords(words):
    # Generate all combinations of words
    all_combinations = []
    for r in range(1, len(words) + 1):
        for p in itertools.product(words, repeat=r):
            combination = ''.join(p)
            if 20 <= len(combination) <= 21:
                all_combinations.append(combination)
            if len(all_combinations) >= 100:
                return all_combinations
    return all_combinations

# wordlist.txt file
with open('C:/Users/TC/AppData/Local/Programs/Python/Python310/wordlist.txt', 'r') as f:
    words = [line.strip() for line in f]

# with open('wordlist.txt', 'r') as f:
#    words = [line.strip() for line in f]

# passwords = generate_passwords(words)

# Only keep the first 1000 passwords
passwords = passwords[:1000]

# Print the first 1000 passwords
for password in passwords:
    print(password)

# Print the passwords to a file
 with open('passwords.txt', 'w') as f:
    for password in passwords:
       f.write(password + '\n')

# Debugging
# Check the Word List
# print("First 10 words:", words[:10])

passwords = generate_passwords(words)

# Check the Password Generation
# print("First 10 combinations:", passwords[:10])

# Check the Length Filtering
# print("First 10 valid passwords:", valid_combinations[:10])

# print("The first 100 passwords have been written to passwords.txt")

