# Password Checker

This project is a password checker program that evaluates the strength of a user's password based on a set of seven rules.

## Evaluation Criteria

1. **Minimum Length:**  
   The password must be at least 8 characters long.
2. **Uppercase Letter:**  
   It must contain at least one uppercase letter.
3. **Lowercase Letter:**  
   It must contain at least one lowercase letter.
4. **Digit:**  
   It must contain at least one numeric digit.
5. **Special Character:**  
   It must include at least one of these characters: `@`, `!`, `#`, `^`, `&`, `*`, or `$`.
6. **Not Leaked:**  
   The password is checked against a list of previously leaked passwords (case-insensitive).  
   _Note: The leaked file is large and sorted based on only alphabetical and numerical characters, so a custom compare function is used in binary search._
7. **Not an English Word:**  
   The password should not be a common English word (using a provided dictionary with words of size 5 or more, checked in a case-insensitive manner).

## Program Flow

- **Sequential Checks:**  
  The program first verifies rules 1-5.  
  If these are satisfied, it checks against rule 6 (leaked passwords).  
  Finally, if rule 6 passes, rule 7 (English word check) is evaluated.
- **Binary Search:**  
  For efficiently searching through the leaked password file, a custom binary search is implemented that considers only alphabetical and numerical characters.

## Notes

- The program strictly outputs the violation messages in the order specified.
- If the password fails any of the initial five rules, rules 6 and 7 are not checked.
- Similarly, if the password fails the leaked check (rule 6), rule 7 is skipped.
- Make sure to follow the output format exactly as required for autograding.

Happy coding!
