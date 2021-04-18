print("Welcome to Budgify")
class Budget:
    def __init__(self,category):
         self.balance = int(input("Enter budgeted amount for "+ category+" category "))
         print("The budgeted amount for ",category," category is %d" % self.balance)
    def getBalance(self):                      #method to compute category balances
        return self.balance
    def depositFunds(self, amount):           #method to deposit funds
        self.balance = self.balance + amount
    def withdrawFunds(self, amount):            #method to withdraw funds
        self.balance = self.balance - amount
    def transfer(self, amount, otherBudget):    #method to transfer from one category to another
        otherBudget.balance = otherBudget.balance + amount
        self.balance = self.balance - amount


food = Budget("food")
clothing = Budget("clothing")
entertainment = Budget("entertainment")

food.withdrawFunds(5000)
clothing.transfer(2000, entertainment)
entertainmentBalance= entertainment.getBalance()
clothingBalance = clothing.getBalance()
foodBalance = food.getBalance()
print(clothingBalance)
print(entertainmentBalance)
print(foodBalance)
