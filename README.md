# password-check-function
A python script using function for password checking.
This is a password check of https://github.com/j4jewel/password-strength-check using a function.

---
Function
---

```sh
def check(*,password=None,digit=3,alpha=3,special=2,length=8):
    
    if not password == None:
        
        alpha_count = 0
        digit_count = 0
        special_count = 0
        
        if len(password) >= length:
            
            for char in password:
                
                if char.isalpha():
                    
                    alpha_count += 1
                
                elif char.isdigit():
                    
                    digit_count += 1
                    
                else:
                    
                    special_count += 1
                    
            if alpha_count >= alpha and digit_count >= digit and special_count >= special:
                
                return "Valid"
            
            else:
                
                return "Check failed"
        
        else:
            
            return "Error length"
    
    else:
        
        return "Error empty"
```
---
Examples
---
```sh
check(password="qwerty")
'Error length'
check(password="qwerty1234")
'Check failed'
check(password="qwerty1234!@#")
'Valid'
```
If we change the code to the below format it can be used in many situations
Set the return value to True or False

```sh
def check(*,password=None,digit=3,alpha=3,special=2,length=8):
    
    if not password == None:
        
        alpha_count = 0
        digit_count = 0
        special_count = 0
        
        if len(password) >= length:
            
            for char in password:
                
                if char.isalpha():
                    
                    alpha_count += 1
                
                elif char.isdigit():
                    
                    digit_count += 1
                    
                else:
                    
                    special_count += 1
                    
            if alpha_count >= alpha and digit_count >= digit and special_count >= special:
                
                return True
            
            else:
                
                return False
        
        else:
            
            return False
        
    else:
        
        return False
```
Then this can be used in following ways
```sh
users = ['mysqlroot123@#$','shared@123#','mypassword123','12345@#$']

for user in users:
    
    if check(password=user):
        
        print('{} : Valid'.format(user))
    
    else:
        
        print('{} : Not Vaild'.format(user))
```
Output
```sh
mysqlroot123@#$ : Valid
shared@123# : Valid
mypassword123 : Not Valid
12345@#$ : Not Valid
```
We can even change the parameters
```sh
users = ['mysqlroot123@#$','shared@123#','mypassword123','12345@#$']

for user in users:
    
    if check(password=user,length=12):
        
        print('{} : Valid'.format(user))
    
    else:
        
        print('{} : Not Vaild'.format(user))
```
Output
```sh
mysqlroot123@#$ : Valid
shared@123# : Not Vaild
mypassword123 : Not Vaild
12345@#$ : Not Vaild
```

---

