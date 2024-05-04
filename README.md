# atm-machine#mini project on ATM
'''1)check_bal
2)deposite
3)withdraw
4)set_pin
variables: bal=0
           og_pin=none'''

#create set_pin function

bal=0
og_pin=None

def set_pin():
    global og_pin
    while True:
            print('*'*50)
            if og_pin==None:
                pin1=int(input('enter a 4 digit pin:'))
                pin2=int(input('confirm your pin:'))
                if pin1==pin2:
                    print('pin set successfull:')
                    og_pin=pin1
                    break
                else: 
                    print("incorrect pin or pin doesn't match")
            else:
                print('pin is already se:')
def check_bal():
    pin=int(input('enter a 4 digit pin:'))
    if pin==og_pin:
        print('available balace in your a/c is',bal,'rs')
    else:
        print('incorrect pin or pin not set')

def deposite():
    global bal
    pin=int(input('enter a 4 digit pin:'))
    if pin==og_pin:
        amt=int(input('enter your amt to deposite'))
        bal+=amt
        print('amount of',amt,'rs.deposited successfully')
    else:
        print("incorrect pin or pin doesn't match")
def withdraw():
    global bal
    pin=int(input('enter 4 digit pin:'))
    if pin==og_pin:
        amt=int(input('enter a amount to withdraw:'))
        if amt<=bal:
        	bal-=amt
        	print('amount of',amt,'rs.withdrawed successfully')
          else:
		print('insuffient funds')
    else:
        print('incorrect pin or pin is not matched')
   
def services():
    while True:
        print('----------welcome to this atm-----------')
        print('enter 1:deposite')
        print('enter 2:withdraw')
        print('enter 3:check balance')
        print('enter 4:set pin')
        print('enter 5:exit')
        choice=int(input('enter your choice:'))
        if choice==1:
            deposite()
        elif choice==2:
            withdraw()
        elif choice==3:
            check_bal()
        elif choice==4:
            set_pin()
        elif choice==5:
            print('----------thank you-------')
            break
        a=input('do you want to continue (y/n)?:')
        if a.lower()=='y':
            continue
        else:
            print('thank you for using our atm:')
            

services()

