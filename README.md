while True:

    name = input("Student name: ")
    budget = float(input("Weekly Budget: "))

    print("==================================")
    print("")
    print("Weekly Expense -- Categories")
    print("")
    print("==================================")
    print("1. Food & Drinks")
    print("2. Transportation")     
    print("3. Mobile / Internet")
    print("4. School Supplies")   
    print("5. Entertainment")
    print("==================================")
    
    categories = {
        "1." : "Food & Drinks",
        "2." : "Transportation",
        "3." : "Mobile / Internet",
        "4." : "School Supplies",
        "5." : "Entertainment"
    }

    expenses = {}
    total_spent = 0
    
    for i in range(1, 5):
        
        print(f"\n --- Expense {i} ---")
        cate = int(input("Category (0 to skip): "))
        
        if cate == "0":
            continue
        
        
        elif cate < 0: 
            print("Invalid Input")
            
            continue
        
        
        
        desc = input("Description: ")
        am = float(input("Amount: "))
        
        
        
        if cate not in expenses: 
            expenses[cate] = []
            
            expenses[cate].append((desc, am))
            
            
    print("\n===========================================")
    print(f"    {name.upper()} Weekly Expense Log        ")
    print("=============================================")
    
    print(f"Weekly Budget: P{budget}")
        
    for idx, cate in enumerate(expenses, start=1):
        print(f"  [{idx}] {categories[cate]}")
    
    for desc, amt in expenses[cat]:
        alert = "  ! High Expense Alert!" if amt >= 150 else ""
        print(f"      {desc:<35} P{amt:.2f}{alert}")
            
        print("------------------------------------------------------")

    print(f"  Total Spent    : P{total_spent:.2f}")

    remaining = weekly_budget - total_spent
    print(f"  Remaining      : P{remaining:.2f}")

    if remaining < 0:
        status = "Over budget!"
    elif remaining < 100:
        status = "Warning: Close to limit."
    else:
        status = "Budget OK! Keep it up."

    print(f"  Status         : {status}")
    print("======================================================")
        
        
        
