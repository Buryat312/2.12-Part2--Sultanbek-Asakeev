# 2.12-Part2--Sultanbek-Asakeev
class Staff:
    def __init__(self, full_name, id_num, salary, hours_worked, num_of_sales):
        self.full_name = full_name
        self.id_num = id_num
        self.salary = salary
        self.hours_worked = hours_worked
        self.num_of_sales = num_of_sales
        # print(f'ID - {self.id_num} Full name - {self.full_name}, Salary - {self.salary}, Hours worked - {self.hours_worked}, Number of sales - {self.num_of_sales}')

    def payment_calculation(self):
        print(f'Personal ID - {self.id_num} Full name - {self.full_name}, Salary - {self.salary}, Hours worked - {self.hours_worked}, Number of sales - {self.num_of_sales}')
      
# c= Staff('Барсбек Канаткулов', 1, 45000, 18, 0)


class Manager(Staff):
    def __init__(self, full_name, id_num, salary, hours_worked, num_of_sales):
        super().__init__(full_name, id_num, salary, hours_worked, num_of_sales)
        print(f' Position - Manager')

    def payment_calculation(self):
        super().payment_calculation()


class Secretary(Staff):
    def __init__(self, full_name, id_num, salary, hours_worked, num_of_sales):
        super().__init__(full_name, id_num, salary, hours_worked, num_of_sales)
        print(f' Position - Secretary')

    def payment_calculation(self):
        super().payment_calculation()


class Seller(Staff):
    def __init__(self, full_name, id_num, salary, hours_worked, num_of_sales):
        super().__init__(full_name, id_num, salary, hours_worked, num_of_sales)
        self.salary = self.salary +self.num_of_sales * 50
        print(f' Position - Seller')

    def payment_calculation(self):
        super().payment_calculation()
        

class Shop_worker(Staff):
    def __init__(self, full_name, id_num, salary, hours_worked, num_of_sales):
        super().__init__(full_name, id_num, salary, hours_worked, num_of_sales)
        self.salary = hours_worked * 100
        print(f' Position - Shop Worker')

    def payment_calculation(self):
        super().payment_calculation()

class Shop_worker2(Staff):
    def __init__(self, full_name, id_num, salary, hours_worked, num_of_sales):
        super().__init__(full_name, id_num, salary, hours_worked, num_of_sales)
        self.salary = hours_worked * 100
        print(f' Position - Shop Worker2')

    def payment_calculation(self):
        super().payment_calculation()

class Part_secretary(Staff):
    def __init__(self, full_name, id_num, salary, hours_worked, num_of_sales):
        super().__init__(full_name, id_num, salary, hours_worked, num_of_sales)
        self.salary = hours_worked * 100
        print(f' Position - Shop Worker2')

    def payment_calculation(self):
        super().payment_calculation()


class Total_salary:
    def __init__(self, sum_total, people):
        self.sum_total = sum_total
        self.people = people
    
    def all_sum(self):
        salary_list = []
        for i in t_salary.sum_total:
            salary_list.append(i.salary)
        # print(f'Salary list {salary_list}')
        Total_sum = sum(salary_list)
        list_of_names = {}
        # new_lst = {i.id_num: [i.full_name for i in t_salary.people, count +=1] for i in t_salary.people} #failed
        lst1 = {}
        count =0
        for i in t_salary.people:
            list_of_names[i.id_num] = lst1
            for j in t_salary.people:
                lst1[j.full_name] = j.salary #  не получается вытащить только одно Имя и ЗП как занчение для ключа
                count +=1

        return f'Total salary: {Total_sum}, People: {list_of_names}'

        
manager = Manager('Барсбек Канаткулов', 1, 45000, 18, 0)
manager.payment_calculation()
secretary = Secretary('Алымкул Тилекбаев', 2, 20000, 38, 0)
secretary.payment_calculation()
seller = Seller('Айпери Шалымбекова', 3, 20000, 38, 20)
seller.payment_calculation()
worker = Shop_worker('Бакыт Рустамов', 4, 0, 20, 0)
worker.payment_calculation()
worker2 = Shop_worker2('Алтынай Ширинбаева', 5, 0, 45, 0)
worker2.payment_calculation()
part_secretary = Part_secretary('Жанар Рыскулов', 6, 0, 33, 0)
part_secretary.payment_calculation()

print()

t_salary = Total_salary(sum_total=[manager, secretary, seller, worker, worker2, part_secretary], people=[manager, secretary, seller, worker, worker2, part_secretary])
print(t_salary.all_sum())

