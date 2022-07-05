# Goldman-Sachs The Forage Virtual Engineering
## Password controls and Security Policies
### Overview
One of your responsibilities as a governance analyst  is  to assess the level of protection of the controls implemented  and minimize the chances of a successful breach. Often, you need to know the techniques that hackers use to bypass the implemented controls and suggest enhancements to increase the overall level of security in your organization. Obtaining valid credentials gives an attacker access to your organization's IT systems, bypassing most  perimeter controls.

## Project Objective
What type of hashing algorithm was used to protect passwords?

What level of protection does the mechanism offer for passwords?

What controls could be implemented to make cracking much harder for the hacker in the event of a password database leaking again?

Here is a sample data file containing hashes dumped together:

https://github.com/ne3lakolkar/Goldman-Sachs-Crack-Leaked-Passsword-Database/blob/main/passwd_dump.txt

After the conducted analysis it was determined that organization uses an outdated password hashing algorithm (MD5) which offers very little protection in the event of a password database leaking. It was also determined that the current password policy is not aligned with industry best practices allowing users to have short passwords (6 characters) and reuse usernames as part of passwords.

As a result of the analysis the following uplifts are proposed to increase the overall level of password protection:

• Use a dedicated password hashing algorithm bcrypt, scrypt or PBKDF2 as this will greatly increase the time needed to crack individual passwords,

• Implement salting to prevent usage of rainbow tables to speed up cracking,

• Increase the minimum password length requirement to 10 characters – this will increase the computational effort required to crack password and will give additional time to change all passwords in the event of the password database being leaked,

• Prevent passwords to be the same as usernames or reused as part of the password – such password combination is easy to check without gaining access to the password database itself.

• It is advised to educate users on creating safe and easy to remember passwords. Having a password policy requiring long passwords with a number of special characters results in user writing passwords down or constantly resetting them. The best way to create a strong and user-friendly password is using passphrases (e.g. mygrannyschairhadstaples). The best way to create such passwords is to combine a couple of completely random word. It’s also advised to use some special characters and numbers as easy to remember substitutions to expand the key space (e.g. mYgranny$cha1rhadstaples)

• Educate users on the benefits of passwords managers. Having a password manager allows having very long and completely random passwords (e.g. M>?{tk6Cfep6BrZ4J)KZWQ8j) without the need to remember/write down. A strong passphrase is still required as a master key for to access the password manager.

# Project Report and Observations 
Completing this task assigned by Goldman Sachs, MD5 and SHA were the two algorithms that I came across. Analysing the passwords and their respective security algorithms used, I narrowed down my observations into this report.

## Project Report
Respected Sir/Madam, 
I was able to decipher 13 passwords from the 19 hash codes specified in the password dump file very easily using https://crackstation.net/ 

e10adc3949ba59abbe56e057f20f883e	md5	123456
25f9e794323b453885f5181f1b624d0b	md5	123456789
d8578edf8458ce06fbc5bb76a58c5ca4	md5	qwerty
5f4dcc3b5aa765d61d8327deb882cf99	md5	password
96e79218965eb72c92a549dd5a330112	md5	111111
25d55ad283aa400af464c76d713c07ad	md5	12345678
e99a18c428cb38d5f260853678922e03	md5	abc123
fcea920f7412b5da7be0cf42b8c93759	md5	1234567
7c6a180b36896a0a8c02787eeafb0e4c	md5	password1
6c569aabbf7775ef8fc570e228c16b98	md5	password!
3f230640b78d7e71ac5514e57935eb69	md5	qazxsw
917eb5e9d6d6bca820922a0c6f7cc28b	md5	Pa$$word1
f6a0cb102c62879d397b12b62c092c06	md5	bluered


Observations:

1)What type of hashing algorithm was used to protect passwords?
Ans: Md5 (Message-Digest algorithm)

2)What level of protection does the mechanism offer for passwords?
Ans:  MD5 is insecure and provides a very low level of protection and should not be used in any application.

3)What controls could be implemented to make cracking much harder for the hacker in the event of a password database leaking again?
Ans: Controls to be implemented to make cracking harder:
i) A min-length password rule should be implemented.
ii)Passwords must contain some special characters,numbers,lowercase alphabets as well as upper case alphabets. 
iii)Using a hashing algorithm which provides a high level of protection. Example:SHA-256 and SHA-3.
iv)Concept of password salting must be used.



4)What can you tell about the organization’s password policy (e.g. password length, key space, etc.)?
Ans: i)There is no rule regarding the minimum length of the password.
          ii)There is no rule regarding use of special characters in the password.
 
5)What would you change in the password policy to make breaking the passwords harder?
Ans: i) The password must be of minimum 8 characters.
ii) Minimum 2 special characters (/, #,*,... etc.)  must be used in the    password.
iii) An external api based tool which checks for password strength should show that the used password is strong.

Complete report is available at:
asasa

### Resources
https://arstechnica.com/information-technology/2013/05/how-crackers-make-minced-meat-out-of-your-passwords/

https://howsecureismypassword.net/

https://en.wikipedia.org/wiki/Password_cracking#Software

https://en.wikipedia.org/wiki/Salt_(cryptography)

https://hashcat.com
