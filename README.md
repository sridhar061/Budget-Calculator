# Budget-Calculator
w_item = [] #giving the empty list as w_item is want item
n_item = [] #giving the empty list as n_item is need item
p_item = [] #giving the empty list as for the p_item is proirity item
v_item = [] #giving the empty list for the v_item
def sort(n_list, p_list, v_list): #calling the function sort with the n_list with p_list and v_list
    l = len(n_list) #l gives the length of n_list
    for i in range(l): #using the for loop i to the required range of l
        for j in range(0, l-i-1): #using the again for loop of j to decrement the range
            if(n_list[j] < n_list[j+1]): #using the if condition in the for loops gives the list with j and j+1
                n_list[j],n_list[j+1] = n_list[j+1],n_list[j] #swapping the v_items of the j and j+1 with assisgning the list
                p_list[j], p_list[j+1] = p_list[j+1], p_list[j] #swapped with the j and j+1 of list(p_list)  
                v_list[j], v_list[j+1] = v_list[j+1], v_list[j] #swapped with the j and j+1 of list(v_list)
            else: #using the perfect condition, if statement is failed 
                pass #pass the equation to next as a argument
    return n_list #calling the function sort with return n_list
    return p_list #calling the function to return the listp_list
    return v_list #calling the function to return the listv_list

def need(): #giving the function need
    salary = int(input("Enter your monthly salary:")) #assisngning the element salary to ask the user to enter the salary
    savings = int(input("Enter the money you want to save:")) #asking the money regard of the savings 
    wallet = salary - savings #giving the wallet and assisinging them as a formula
    if(savings>salary): #using the condition if savings are greater than salary 
        print("Savings cannot be greater than salary!!!") #it prints the statement
    elif(wallet<0): #if not possible with the if statement goes to elif and seems to be wallet is lessthan 0
        print("Invalid Entries!!!") #it prints the statement condition is impossible from user
    else: #final judgement to give the condition regarding the suit
        
        print(wallet, "is the amount you want to use...") #it prints the given statement with the wallet  
        n1 = int(input("Enter the number of n_item you have:")) #giving the n1 as the no.of n_item to be given by user
        for i in range(0,n1): #using the for loop to upto the user can give it
            n1 = input("Enter your need:") #giving the n1 as a input to give the user to put the need
            p1= int(input("Enter Its p_item:")) #giving the p1 as a integer to give its p_item
            v1= int(input("Enter its price:")) #giving the v1 as a integer to give its price
            print("\n") #prints new line for the n_item
            n_item.append(n1) # n_item must to be added via giving the user
            p_item.append(p1) #p_item gives to add the integer in the n_item 
            v_item.append(v1) #v_item can be added by giving the input from user
        
        sort(p_item, v_item, n_item) #making to sort the elements into this
    
        print(p_item) #it prints the statement 
        print(v_item) #prints the v_item is value item
        print("\n") #it prints in new line
    
        for i in range(len(p_item)): #using the for loop with the range of length of p_item
            if(wallet>v_item[i]): #using the condition if wallet is greater than v_item
                print("Buying the product", n_item[i], "With highest p_item", p_item[i]) #if it is done prints the statement
                wallet = wallet - v_item[i] #wallet gives the user wallet and the v_item
            elif(wallet<v_item[i]): #passes to condition elif wallet is less than v_item with the following of range
                print("Sorry,,, Its price is too high!!!")#following the elif statement it prints the statement
                pass #passes to else condition
            else:# final conditon to the if statement depending about the input 
                pass#passes the conditon if it is exceeds the amount
        
        print(wallet, "Is left with you after spending on all the n_item...")#prints the given statement
    

def want():#giving the function want  
    salary = int(input("Enter your salary:"))#assisngning the element salary to ask the user to salary
    savings = int(input("Enter the money you want to save:"))#asking the regard of the savings
    wallet = salary - savings#giving the wallet and assisngnig them as a formula
    if(savings>salary):#using the condition if savings are greater than salary 
        print("Savings cannot be greater than salary!!!")#it prints the statement
    elif(wallet<0):#if not possible with the if statement goes to elif and sees to wallet is lessthan 0
        print("Invalid Entries!!!")#it prints the statement condition is possible
    else:#final judgement to give the condition regarding the suit
        
        print(wallet, "is the amount you want to use...")  #it prints the given statement   
        n = int(input("Enter thenumber of w_item you have:"))#giving the n as the no.of n_item to be given by user
        for i in range(0,n):#using the for loop to upto the user can give it
            n = input("Enter your want:")#giving the n as a input to give the user to put the need
            p= int(input("Enter Its p_item:"))#giving the p as a integer to give its p_item
            v= int(input("Enter its price:"))#giving the v as a integer to give its price
            print("\n")#prints new line for the n_item
            w_item.append(n)# w_item must to be added via giving the user
            p_item.append(p)#p_item gives to add the integer in the n_item
            v_item.append(v)#v_item can be added by giving the input from user
        
        
        sort(p_item, v_item, w_item)#making to sort the elements into this
    
        print(p_item)#it prints the statement 
        print(v_item) #prints the v_item
        print("\n")#it prints in new line
    
        for i in range(len(p_item)):#using the for loop with the range of length of p_item
            if(wallet>v_item[i]):#using the condition if wallet is greater than v_item
                print("Buying the product", w_item[i], "With highest p_item", p_item[i]) #if it is done prints the statement
                wallet = wallet - v_item[i]#wallet gives the user wallet and the v_item
            elif(wallet<v_item[i]):#passes to condition elif wallet is less than v_item with the following of range
                print("Sorry,,, Its price is too high!!!")#following the elif statement it prints the statement
                pass #passes to else condition
            else:# final conditon to the if statement depending about the input 
                pass#passes the conditon if it is exceeds the amount
        
        print(wallet, "Is left with you after spending on all the n_item...") #it prints the statement with the amount left
        
        
print("***********MAIN-MENU*************")#it prints the statement
print("Enter 1. for needs", "\n")# it prints the statement for n_item
print("Enter 2. for wants", "\n") #it prints the statement for w_item 
a = int(input("Enter your choice:")) #asking the user to give their choice

if(a==1): #using the condition if the user gives to choice 1 goes to need
    need() # all the above function tends to need
elif(a==2):# using the condition elif to user gives the choice 2 goes to w_item 
    want() #all the above functions tends to w_item
else: #using the final condition other than 1 and 2
    print("Invalid Entry!!!") #it prints the given statement.

