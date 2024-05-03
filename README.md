#  1  Is it a Duck Number?


# def is_duck_number(n):
#     n_str = str(n)
#     has_zero = False
#     for i in range(1, len(n_str)):
#         if n_str[i] == '0':
#             has_zero = True
#             break

#     if has_zero and n_str[0] != '0':
#         return "DN"
#     else:
#         return "NDN"

# # Test cases345
# a=int(input(''))
# print(is_duck_number(a))
# # print(is_duck_number(123))   # NDN
# # print(is_duck_number(707069)) # DN


#  2  Sum of Digits Squared
# def sum_of_squares_of_digits(n):
#     sum_squared = 0
#     n_str = str(n)

#     for digit in n_str:
#         sum_squared += int(digit) ** 2

#     return sum_squared

# # Test cases
# print("Sum of squares of digits of 123 is: ", sum_of_squares_of_digits(123))
# print("Sum of squares of digits of 456 is: ", sum_of_squares_of_digits(456))
# print("Sum of squares of digits of 789 is: ", sum_of_squares_of_digits(789))



# 3  Remove Duplicates from String
# def remove_duplicates(s):
#     result = ""
#     for char in s:
#         if char not in result:
#             result += char
#     return result

# # Test cases
# a=input("")
# print("String with duplicates removed: ", remove_duplicates(a))
# print("String with duplicates removed: ", remove_duplicates("programming"))
# print("String with duplicates removed: ", remove_duplicates("mississippi"))


#  4 Largest Number in a List
# def largest_number_in_list(numbers_str):
#     numbers = [int(num) for num in numbers_str.split()]
#     largest_number = float('-inf')

#     for num in numbers:
#         if num > largest_number:
#             largest_number = num

#     return largest_number

# # Test cases
# a=input('')
# print("Largest number in the list: ", largest_number_in_list(a))
# print("Largest number in the list: ", largest_number_in_list("20 30 40 10 25"))
# print("Largest number in the list: ", largest_number_in_list("1 2 3 4 5"))

#  5  Identify Twisted Primes
# num = int(input("Enter a number: "))

# # Check if the number is prime
# def is_prime(n):
#     if n < 2:
#         return False
#     for i in range(2, int(n**0.5) + 1):
#         if n % i == 0:
#             return False
#     return True

# # Check if the number is a twisted prime
# def is_twisted_prime(n):
#     if is_prime(n) and is_prime(int(str(n)[::-1])):
#         return True
#     return False

# # Print the result
# if is_twisted_prime(num):
#     print(f"{num} is a twisted prime")
# else:
#     print(f"{num} is not a twisted prime")




# 6  Mersenne Number Check
# num = int(input("Enter a number: "))
# power_of_two = 1
# while num > 0:
#     if power_of_two == num:
#         print("The number is a Mersenne number")
#         break
#     power_of_two *= 2
#     num -= 1
# if num > 0:
#     print("The number is not a Mersenne number")


# Mersenne Number Check
# def is_mersenne_number(n):
#     # Start from the power of two (2^1)
#     power_of_two = 2

#     # Keep doubling until it is greater than the given number
#     while power_of_two <= n:
#         power_of_two *= 2

#     # Subtract one from this power of two to check if it matches the given number
#     if power_of_two - 1 == n:
#         return True
#     else:
#         return False

# # Get an integer from the user
# n = int(input("Enter an integer: "))

# # Check if the number is a Mersenne number
# if is_mersenne_number(n):
#     print("The number is a Mersenne number")
# else:
#     print("The number is not a Mersenne number")


# 7 Evil number
# def is_evil_number(num):
#     # Convert the number to binary and remove the '0b' prefix
#     binary_representation = bin(num).replace('0b', '')
    
#     # Initialize the count of 1s
#     count_of_ones = 0
    
#     # Loop through each digit in the binary representation
#     for digit in binary_representation:
#         # Increment the count when a '1' is encountered
#         if digit == '1':
#             count_of_ones += 1
    
#     # Check if the count of 1s is even
#     if count_of_ones % 2 == 0:
#         return f"{num} is an evil number."
#     else:
#         return f"{num} is not an evil number."

# # Sample test cases
# print(is_evil_number(3))  # Output: "3 is not an evil number."
# print(is_evil_number(4))  # Output: "4 is an evil number."
# print(is_evil_number(7))  # Output: "7 is not an evil number."



# 8 Celebrity Name Scrambler
# import random

# def scramble_name(name):
#     # Check if the name is at least 4 characters long
#     if len(name) < 4:
#         return "Name must be at least 4 characters long."
    
#     # Extract the first and last letters
#     first_letter = name[0]
#     last_letter = name[-1]
    
#     # Scramble the middle letters
#     middle_letters = list(name[1:-1])
#     random.shuffle(middle_letters)
    
#     # Concatenate the first letter, shuffled middle letters, and last letter
#     scrambled_name = first_letter + ''.join(middle_letters) + last_letter
    
#     return f"Original: {name} - Scrambled: {scrambled_name}"

# # Sample test cases
# print(scramble_name("Leonardo DiCaprio"))  # Output: Original: Leonardo DiCaprio - Scrambled: Ledraioacn Pooi
# print(scramble_name("Scarlett Johansson")) # Output: Original: Scarlett Johansson - Scrambled: Scraslehtt Jhoaonn
# print(scramble_name("Tom Hanks"))          # Output: Name must be at least 4 characters long.


# import re

# def create_markdown_link(display_text, url):
#     # Regular expression to validate the URL
#     regex = re.compile(
#         r'^(?:http|https)://'  # protocol
#         r'(?:(?:A-Z0-9?\.)+'  # domain
#         r'(?:[A-Z]{2,6}\.?|[A-Z0-9-]{2,}\.?)|'  # extension
#         r'localhost|'  # localhost
#         r'\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3})'  # or IP
#         r'(?::\d+)?'  # optional port
#         r'(?:/?|[/?]\S+)$', re.IGNORECASE)  # path

#     # Check if the URL is valid
#     if re.match(regex, url):
#         # Return the formatted Markdown link
#         return f"{display_text}"
#     else:
#         # Return an error message if the URL is invalid
#         return "Invalid URL format. Please enter a valid URL."

# # Sample test cases
# print(create_markdown_link("Search the Web", "https://www.google.com"))  # Output: Search the Web
# print(create_markdown_link("Free Online Encyclopedia", "http://www.wikipedia.org"))  # Output: Free Online Encyclopedia
# print(create_markdown_link("This won't work", "invalidURL"))  # Output: Invalid URL format. Please enter a valid URL.

#  10  Pig Latin Translator

# def translate_to_pig_latin(word):
#     # Convert the word to lowercase for case-insensitive translation
#     word = word.lower()

#     # Check if the word starts with a vowel ("aeiou")
#     if word[0] in "aeiou":
#         # Add "way" to the end of the word
#         pig_latin_word = word + "way"
#     else:
#         # Identify the first vowel index
#         vowel_index = next((i for i, char in enumerate(word) if char in "aeiou"), None)

#         # Extract the consonants before the first vowel (using slicing)
#         consonants = word[:vowel_index]

#         # Move the consonants to the end of the word (using concatenation)
#         # and add "ay" to the end of the translated word
#         pig_latin_word = word[vowel_index:] + consonants + "ay"

#     return pig_latin_word

# # Get a word as input from the user
# word = input("Enter a word: ")

# # Display the original word and its Pig Latin translation
# print(f"Original: {word}\nPig Latin: {translate_to_pig_latin(word)}")


#   11   Rhyme Detector
# def get_rhyme_substring(word):
#     # Convert the word to lowercase for case-insensitive matching
#     word = word.lower()

#     # Iterate backwards from the end of the word, skipping consonants
#     for i in range(len(word) - 2, -1, -1):
#         if word[i] in "aeiou":
#             # Extract a maximum of the last 3 characters (including any consonants following the vowel)
#             rhyme_substring = word[i:].lower()[:3]
#             return rhyme_substring

#     return ""

# def is_rhyme(word1, word2):
#     # Get the rhyme substrings for both words
#     rhyme_substring1 = get_rhyme_substring(word1)
#     rhyme_substring2 = get_rhyme_substring(word2)

#     # Compare the rhyme substrings (case-insensitive)
#     if rhyme_substring1 and rhyme_substring2 and rhyme_substring1 == rhyme_substring2:
#         return True
#     else:
#         return False

# # Get two words as input from the user
# word1 = input("Enter the first word: ")
# word2 = input("Enter the second word: ")

# # Display if the words likely rhyme
# if is_rhyme(word1, word2):
#     print("The words likely rhyme.")
# else:
#     print("The words do not likely rhyme.")
   
# 12  Caesar Cipher

# def caesar_cipher(message, key):
#     encrypted_message = ""

#     for char in message:
#         if char not in "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ":
#             encrypted_message += char
#         else:
#             # Convert the character to lowercase for easier handling
#             char = char.lower()

#             # Calculate the new position by adding the key to the lowercase letter's ASCII value
#             new_position = (ord(char) - ord("a") + key) % 26 + ord("a")

#             # Convert the new ASCII value back to a character
#             encrypted_char = chr(new_position)

#             # Append the encrypted character to the message string
#             encrypted_message += encrypted_char

#     return encrypted_message

# # Get the message and key as input from the user
# message = input("Enter the message: ")
# key = int(input("Enter the key (positive integer): "))

# # Display the encrypted message
# print("Encrypted message:", caesar_cipher(message, key))


# 13   Balanced Parentheses
# def is_balanced(expression):
#     opening_to_closing = {'(': ')', '[': ']', '{': '}'}
#     stack = []

#     for char in expression:
#         if char in opening_to_closing:
#             stack.append(char)
#         elif char in opening_to_closing.values():
#             if not stack or opening_to_closing[stack.pop()] != char:
#                 return False

#     return not stack

# # Get the expression as input from the user
# expression = input("Enter the expression: ")

# # Display if the parentheses are balanced
# print("Balanced:", is_balanced(expression))


# 14 Typo Detector
# def find_typos(word, dictionary):
#     # Function to generate all one-edit-away variations of the word
#     def generate_variations(word):
#         letters = 'abcdefghijklmnopqrstuvwxyz'
#         splits = [(word[:i], word[i:]) for i in range(len(word) + 1)]
#         deletes = [L + R[1:] for L, R in splits if R]
#         inserts = [L + c + R for L, R in splits for c in letters]
#         replaces = [L + c + R[1:] for L, R in splits if R for c in letters]
#         return set(deletes + inserts + replaces)

#     # Convert the word to lowercase
#     word = word.lower()
#     # Generate all one-edit-away variations
#     variations = generate_variations(word)
#     # Find all variations that are in the dictionary
#     typos = [variation for variation in variations if variation in dictionary]

#     return typos

# # Example usage:
# dictionary = {'the', 'writing', 'correct'}
# print(find_typos('teh', dictionary))    # Output: ['the']
# print(find_typos('writng', dictionary)) # Output: ['writing']
# print(find_typos('correct', dictionary)) # Output: []

#  15   Price Formatter

# import re

# def format_price(price):
#     # Check if the input is a number (can use try-except or isinstance)
#     if isinstance(price, (int, float)) or re.match(r"^-?\d+(\.\d{1,2})?$", price):
#         price = float(price)

#         # Format the price string using f-strings or string formatting methods
#         formatted_price = f"${price:.2f}"

#         return formatted_price

# # Get the price as input from the user
# price = input("Enter the price: ")

# # Display the formatted price
# print("Formatted price:", format_price(price))

#  16  SMS Acronym Decoder
# import re

# def decode_sms(text):
#     # Dictionary of SMS abbreviations and their full forms
#     sms_dict = {
#         'IMHO': 'In My Humble Opinion',
#         'BRB': 'Be Right Back',
#         'IRL': 'In Real Life',
#         'LOL': 'Laughing Out Loud',
#         'FYI': 'For Your Information'
#         # Add more abbreviations and their full forms as needed
#     }
    
#     # Regular expression pattern to find abbreviations
#     pattern = r'\b(' + '|'.join(re.escape(abbreviation) for abbreviation in sms_dict.keys()) + r')\b'
    
#     # Function to replace abbreviations with their full forms
#     def replace_abbreviation(match):
#         return sms_dict[match.group(0)]
    
#     # Replace abbreviations in the text
#     decoded_text = re.sub(pattern, replace_abbreviation, text)
    
#     return decoded_text

# # Sample test cases
# print(decode_sms("This message uses some abbreviations: IMHO, BRB for lunch IRL, LOL."))
# # Output: This message uses some abbreviations: In My Humble Opinion, Be Right Back for lunch In Real Life, Laughing Out Loud.

# print(decode_sms("This message has no abbreviations."))
# # Output: This message has no abbreviations.

# print(decode_sms("Using a less common abbreviation: FYI for your information."))
# # Output: Using a less common abbreviation: For Your Information for your information.



# import re

# def parse_full_name(full_name):

#     # Split the full name based on whitespace
#     name_parts = full_name.split()

#     # Initialize name components
#     first_name = ""
#     middle_name = ""
#     last_name = ""

#     # Identify patterns and handle edge cases
#     for i, part in enumerate(name_parts):
#         if i == 0:
#             first_name = part
#         elif i == len(name_parts) - 1:
#             last_name = part
#         elif re.match(r"[A-Z]\.", part):
#             middle_name += part + " "
#         else:
#             middle_name += part + " "

#     # Remove any trailing space from middle_name
#     middle_name = middle_name.rstrip()

#     # Handle double-barreled last names
#     if " " in last_name:
#         last_name_parts = last_name.split(" ")
#         last_name = last_name_parts[0]
#         last_name += " " + " ".join(last_name_parts[1:])

#     # Handle prefixes and suffixes (optional)
#     # Add your logic here if needed

#     # Return a dictionary containing the parsed name components
#     return {"first_name": first_name, "middle_name": middle_name, "last_name": last_name}

# # Get the full name as input from the user
# full_name = input("Enter the full name: ")

# # Display the parsed name components
# print("Parsed name components:", parse_full_name(full_name))




#  18  check_password_strength
# def check_password_strength(password):
#     # Define minimum password length
#     min_length = 8

#     # Check if the password contains uppercase letters, lowercase letters, numbers, and symbols
#     has_upper = any(char.isupper() for char in password)
#     has_lower = any(char.islower() for char in password)
#     has_number = any(char.isdigit() for char in password)
#     has_symbol = any(char in "!@#$%^&*()-_=+[{]}\\|;:'\",<.>/?`~" for char in password)

#     # Evaluate password strength based on the criteria met
#     if len(password) < min_length:
#         strength = "Weak"
#     elif not (has_upper and has_lower and has_number and has_symbol):
#         strength = "Medium"
#     else:
#         strength = "Strong"

#     return strength

# # Get the user's password as input
# password = input("Enter your password: ")

# # Display the password strength
# print("Your password strength is:", check_password_strength(password))

#  19  Event Ticket Price Calculator with Family Discount

# def calculate_ticket_price(adult_tickets, child_tickets):
#     # Define separate variables for the individual ticket prices (adult and child)
#     adult_ticket_price = 32.5
#     child_ticket_price = 17.5

#     # Calculate the total price before discount
#     total_price_before_discount = adult_tickets * adult_ticket_price + child_tickets * child_ticket_price

#     # Implement a conditional statement to check if it's a family (at least one adult and one child)
#     if adult_tickets >= 1 and child_tickets >= 1:
#         # Apply a 10% discount if it's a family
#         total_price = total_price_before_discount * 0.9
#         return total_price, total_price_before_discount

#     # If not a family, return the total price without discount
#     return total_price_before_discount, total_price_before_discount

# # Get the user's input for the number of adult and child tickets
# adult_tickets = int(input("Enter the number of adult tickets: "))
# child_tickets = int(input("Enter the number of child tickets: "))

# # Calculate the total price before and after discount (if applicable)
# total_price, total_price_before_discount = calculate_ticket_price(adult_tickets, child_tickets)

# # Display the number of adult and child tickets, the total price before discount (if applicable),
# # and the final price after discount (if applicable)
# print("\nFamily discount applied (10% off)!")
# print("\nYour order summary:")
# print("Number of Adult Tickets:", adult_tickets)
# print("Number of Child Tickets:", child_tickets)
# print("Total Price before Discount:", f"${total_price_before_discount:.2f}")
# print("Total Price:", f"${total_price:.2f}")



# def movie_ticket_discount(age, day_of_week):
#     # Implement a series of if statements to check the age and day of the week
#     if age >= 65:
#         # Senior discount
#         print("You qualify for a senior discount of 10%!")
#     elif day_of_week.lower() == "tuesday":
#         # Tuesday discount
#         print("It's Tuesday! You qualify for a 15% discount.")
#     else:
#         # No discount
#         print("You don't qualify for a discount today, but enjoy the movie!")

# # Get the user's input for their age and the day of the week
# age = int(input("Enter your age: "))
# day_of_week = input("Enter the day of the week (e.g., Monday, Tuesday, Wednesday, etc.): ").lower()

# # Call the movie_ticket_discount function with the user's input
# movie_ticket_discount(age, day_of_week)

# area of circle
# import math

# def circle_area(radius):
#     # Use the formula A = πr^2 to calculate the area of the circle
#     area = math.pi * (radius ** 2)
#     return area

# # Get the user's input for the radius of the circle
# radius = float(input("Enter the radius of the circle: "))

# # Call the circle_area function with the user's input
# circle_area_result = circle_area(radius)

# # Display the result with 2 decimal places
# print("The area of the circle is: {:.2f}".format(circle_area_result))




# # 1   profit loss
#def profit_or_loss(cost_price, selling_price):
#     if cost_price < 0 or selling_price < 0:
#         return "Invalid input"

#     profit_loss = selling_price - cost_price
#     percentage = (profit_loss / cost_price) * 100

#     if profit_loss > 0:
#         result = "Profit"
#     elif profit_loss < 0:
#         result = "Loss"
#     else:
#         result = "No profit or loss"

#     return result, round(percentage, 2)

# # Example usage
# cost_price =int(input(''))
# selling_price =int(input(''))
# profit_or_loss_result, percentage = profit_or_loss(cost_price, selling_price)
# print(profit_or_loss_result)
# a='%'
# print(percentage,a)





#  2   wish me 
# def wish_me(hour, minute):
#     if hour < 0 or hour > 23 or minute < 0 or minute > 59:
#         return "Invalid input"

#     if hour >= 4 and hour <= 11:
#         return "Good Morning"
#     elif hour >= 12 and hour <= 15:
#         return "Good AfterNoon"
#     elif hour >= 16 and hour <= 20:
#         return "Good Evening"
#     else:
#         return "Good Night"

# # Example usage
# hour =int(input(""))
# minute =int(input(""))
# wish = wish_me(hour, minute)
# print(wish)





# 3   trip or not 
# def trip_or_not(n, s, c, h, l, t):
#     total_time_required = s * c * h
#     available_time = (n - l) * t

#     if total_time_required > available_time:
#         return "Padhai Karenge"
#     else:
#         return "Goa Jaayenge"

# # Example usage
# n, s, c, h, l, t=map(int,input('').split())
# trip_or_not_result = trip_or_not(n, s, c, h, l, t)
# print(trip_or_not_result)
#

#4 funny or not 


# def funny_or_not(n, b, g, i, d):
#     anger_level = b * i - g * d

#     if anger_level > 0:
#         return "Simple Questions"
#     elif anger_level < 0:
#         return "Funny Questions"
#     else:
#         return "God Knows!"

# # Example usage
# n, b, g, i, d=map(int,input("").split())
# funny_or_not_result = funny_or_not(n, b, g, i, d)
# print(funny_or_not_result)



#5 Find the Operator
# A, B, R = map(int, input().split())
# if R == A + B:
#     print('+')
# elif R == A - B:
#     print('-')
# elif R == A * B or R == B * A and A != 0 and B != 0:
#     print('*')
# elif R == A // B or R == B // A:
#     print('/')
# elif R % B == 0 and R // B == A:
#     print('/')
# else:
#     print('%')



#6  Probability of Buying Phone
# Getting the input
# P1 = float(input())
# P2 = float(input())
# P3 = float(input())
# A = float(input())

# # Calculating the probabilities
# P1_prob = min(1, A/P1)
# P2_prob = min(1, A/P2)
# P3_prob = min(1, A/P3)

# # Printing the probabilities
# print("Probability of buying phone 1: {:.3f}".format(P1_prob))
# print("Probability of buying phone 2: {:.3f}".format(P2_prob))
# print("Probability of buying phone 3: {:.3f}".format(P3_prob))

## 7DIVISIBILTY CHECK

# n = int(input())
# d1 = int(input())
# d2 = int(input())

# if n % d1 == 0 and n % d2 == 0:
#     print("Yes.")
# else:
#     print("No.")



# 8  8. Vowel or Consonant
# ch = input()

# if ch.isalpha():
#     if ch.lower() in 'aeiou':
#         print('Vowel.')
#     else:
#         print('Consonant.')
# else:
#     print('Not an alphabet.')


#9. Days in Month
# month = int(input())

# if 1 <= month <= 12:
#     days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
#     print(days[month - 1])
# else:
#     print('Wrong month value.')
    
# 10. Valid Triangles
# T=int(input())

# for _ in range(T):
#     A, B, C = map(int, input().split())
#     if A + B + C == 180:
#         print('YES')
#     else:
#         print('NO')



#11. Table
# n = int(input())

# for i in range(1, 11):
#     print(n * i)


#12. Odd Numbers
# n = int(input())

# number = 1
# while number <= n:
#     if number % 2 != 0:
#         print(number)
#     number += 1


# 13LEAP YEAR
# year = int(input())

# for i in range(1, year + 1):
#     if (i % 4 == 0 and i % 100 != 0) or i % 400 == 0:
#         print(i, end=" ")



# 14PERFACT NUMBER
# n = int(input())

# sum = 1
# for i in range(2, int(n/2) + 1):
#     if n % i == 0:
#         sum += i

# if sum == n and sum > 0:
#     print("Perfect.")
# else:
#     print("Not Perfect.")
#   16 6. OperaƟon Query
# def apply_operation(result, operator, num):
#     if operator == '+':
#         return result + num
#     elif operator == '-':
#         return result - num
#     elif operator == '*':
#         return result * num
#     elif operator == '/':
#         return result // num  # Integer division
#     elif operator == '%':
#         return result % num
#     elif operator == '&':
#         return result & num  # Bitwise AND
#     elif operator == '^':
#         return result ^ num  # Bitwise XOR
#     elif operator == '|':
#         return result | num  # Bitwise OR

# # Input
# N, Q = map(int, input().split())
# result = N

# # Process queries
# for _ in range(Q):
#     operator, num = input().split()
#     num = int(num)
#     result = apply_operation(result, operator, num)

# # Output
# print(result)
# musquito 
# import math

# def min_time_to_touch_ball(R, S, V):
#     h = math.sqrt(R * 2 - (R - S) * 2)
#     t = h / V
#     return "{:.3f}".format(t)

# T = int(input().strip())
# for i in range(T):
#     R, S, V = map(int, input().strip().split())
#     t = min_time_to_touch_ball(R, S, V)
#     print(t)
