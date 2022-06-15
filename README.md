# classemployer
class Employee:
    def __init__(self, first_name, last_name):
        self.setFirstName(first_name)
        self.setLastName(last_name)
    
    def setFirstName(self, first_name):
        self.__firstName = first_name
    
    def getFirstName(self):
        return self.__firstName

    def setLastName(self, last_name):
        self.__lastName = last_name
    
    def getLastName(self):
        return self.__lastName
    
    def printEmployee(self):
        print("My name is " + self.getFirstName() + " " + self.getLastName())
    

class CommissionEmployee(Employee):
    def __init__(self, first_name, last_name, commission_rate, gross_sales):
        super().__init__(first_name, last_name)
        self.setCommissionRate(commission_rate)
        self.setGrossSales(gross_sales)
        
    def setCommissionRate(self, commission_rate):
        self.__commission_rate = commission_rate
    
    def getCommissionRate(self):
        return self.__commission_rate
    
    def setGrossSales(self, gross_sales):
        self.__gross_sales = gross_sales

    def getGrossSales(self):
        return self.__gross_sales
    
    def printEmployee(self):
        super().printEmployee()
        print("Commission Rate:", self.getCommissionRate())
        print("Gross Sales:", self.getGrossSales())

    def earnings(self):
        self.earnings = self.getCommissionRate() * self.getGrossSales()
        print("Earnings:", self.earnings)
        return self.earnings
class BasePlusCommissionEmployee(CommissionEmployee):
    def __init__(self, first_name, last_name, commission_rate, gross_sales, base_salary):
        super().__init__(first_name, last_name, commission_rate, gross_sales)
        self.setBaseSalary(base_salary)

    def setBaseSalary(self, base_salary):
        self.__base_salary = base_salary

    def getBaseSalary(self):
        return self.__base_salary

    def printEmployee(self):
        super().printEmployee()
        print("Base Salary:", self.getBaseSalary())

    def earnings(self):

        self.earnings = self.getBaseSalary() + super().earnings()
        print("Earnings:", self.earnings)


"""from BasePlusCommissionEmployee import BasePlusCommissionEmployee
from Employee import Employee
from CommissionEmployee import CommissionEmployee

def main():


    c1 = CommissionEmployee("afied", "mumut", 10000, 0.6)
    c1.printEmployee()
    c1.earnings()

    print()
    
    b1 = BasePlusCommissionEmployee("afied", "mumut", 5000, 0.4, 300)
    b1.printEmployee()
    b1.earnings()

main()"""
