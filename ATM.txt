def atm():
    print("Welcome to ATM!")
    pin = "1234"
    balance = 1500
    
    while True:
        enterd_pin = input("Please enter your 4-digit PIN or press exit to quit:")
        if enterd_pin == pin:
            print("\n1.Check Current Balance")
            print("2.Withdraw")
            print("3.Deposit")
            print("4.Change PIN Number")
            print("5.exit")
            
            choice = int(input("Please Enter your Choice: "))
            if choice ==1 :
                print("Your current balance is:",balance)
                
            elif choice==2:
                amount = float(input("How much you want to Withdraw?: "))
                if amount > balance:
                    print("Insufficient Balance!")
                else:
                    balance -= amount
                    print("You have withdraw ",amount)
                    print("Now your current balance is",balance)
                    
            elif choice==3:
                amount = float(input("How much you want to deposit?: "))
                balance+= amount
                print("You have deposit ",amount)
                print("Now your current balance is ",balance)
                
            elif choice==4:
                new_pin = input("Enter your new 4-digit PIN Number: ")
                if len(new_pin) == 4 and new_pin.isdigit():
                    pin = new_pin
                    print("PIN number has been changed successfully.")
                else:
                    print("Invalid PIN number!!")
                 
            elif choice == 5:
                print("Thank You!")
                break
                
        elif enterd_pin.lower() == 'exit' :
            print("Exiting the ATM!")
            break
            
        else:
            print("You have entered wrong PIN Number")
atm()