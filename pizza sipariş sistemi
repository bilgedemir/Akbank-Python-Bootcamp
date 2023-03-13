from typing_extensions import Self
import csv
from datetime import datetime

now = datetime.now()

# Menu.txt dosyasını oluşturma
with open("Menu.txt", "w") as file:
    file.write("* Lütfen Bir Pizza Tabanı Seçiniz:\n")
    file.write("1: Klasik\n")
    file.write("2: Margarita\n")
    file.write("3: TürkPizza\n")
    file.write("4: Sade Pizza\n")
    file.write("* ve seçeceğiniz sos:\n")
    file.write("11: Zeytin\n")
    file.write("12: Mantarlar\n")
    file.write("13: Keçi Peyniri\n")
    file.write("14: Et\n")
    file.write("15: Soğan\n")
    file.write("16: Mısır\n")
    file.write("* Teşekkür ederiz!")


# "Pizza" Üst sınıfını oluşturma
class Pizza:
    def get_description(self):
        pass

    def get_cost(self):
        pass


#"KlasikPizza"  Alt sınıfını oluşturma
class KlasikPizza(Pizza):
    def __init__(self):
        self.description = "Klasik Pizza"
        self.cost = 20.0

    def get_description(self):
        return self.description

    def get_cost(self):
        return self.cost


#"MargaritaPizza" Alt sınıfını oluşturma
class MargaritaPizza(Pizza):
    def __init__(self):
        self.description = "Margarita Pizza"
        self.cost = 22.0

    def get_description(self):
        return self.description

    def get_cost(self):
        return self.cost


#"TurkPizza" Alt sınıfını oluşturma
class TurkPizza(Pizza):
    def __init__(self):
        self.description = "Türk Pizza"
        self.cost = 25.0

    def get_description(self):
        return self.description

    def get_cost(self):
        return self.cost


#"SadePizza" Alt sınıfını oluşturma
class SadePizza(Pizza):
    def __init__(self):
        self.description = "Sade Pizza"
        self.cost = 18.0

    def get_description(self):
        return self.description

    def get_cost(self):
        return self.cost


#"Decorator"  Üst sınıfını oluşturma
class SosDecorator(Pizza):
    def __init__(self, pizza):
        self.pizza = pizza

    def get_description(self):
        return self.pizza.get_description()

    def get_cost(self):
        return self.pizza.get_cost()


#"ZeytinSosu"  Alt sınıfını oluşturma
class ZeytinSosu(SosDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Zeytin Sosu"
        self.cost = 3.0

    def get_description(self):
        return self.pizza.get_description() + ", " + self.description

    def get_cost(self):
        return self.pizza.get_cost() + self.cost


#"MantarSosu"  Alt sınıfını oluşturma
class MantarSosu(SosDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Mantar Sosu"
        self.cost = 2.0

    def get_description(self):
        return self.pizza.get_description() + ", " + self.description

    def get_cost(self):
        return self.pizza.get_cost() + self.cost  

#"KeciPeyniriSosu"  Alt sınıfını oluşturma
class KeciPeyniriSosu(SosDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Keçi Peyniri Sosu"
        self.cost = 12.0

    def get_description(self):
        return self.pizza.get_description() + ", " + self.description

    def get_cost(self):
        return self.pizza.get_cost() + self.cost  

#"EtSosu"  Alt sınıfını oluşturma
class EtSosu(SosDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Et Sosu"
        self.cost = 20.0

    def get_description(self):
        return self.pizza.get_description() + ", " + self.description

    def get_cost(self):
        return self.pizza.get_cost() + self.cost  

#"SoganSosu"  Alt sınıfını oluşturma
class SoganSosu(SosDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Soğan Sosu"
        self.cost = 8.0

    def get_description(self):
        return self.pizza.get_description() + ", " + self.description

    def get_cost(self):
        return self.pizza.get_cost() + self.cost  
  
 #"MisirSosu"  Alt sınıfını oluşturma
class MisirSosu(SosDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Mısır Sosu"
        self.cost = 5.0

    def get_description(self):
        return self.pizza.get_description() + ", " + self.description

    def get_cost(self):
        return self.pizza.get_cost() + self.cost  

#kredi kartı bilgileri girme
def get_payment_info():
 tc = input("kimlik bilgilerini giriniz: ")
 card_number = input("Kart numaranızı girin: ")
 card_password = input("Kart şifrenizi giriniz: ")
 card_expiry = input("Son kullanma tarihini girin (MM/YYYY): ")
 card_cvv = input("CVV kodunu girin: ")
 return tc, card_number, card_password, card_expiry, card_cvv


def calculate_total_price(product):
# fiyatını alma
 price = product.get_cost()
 sos_price = SosDecorator.get_cost()
# Toplam fiyatı hesaplama
 total_price = price + sos_price
 return total_price

def select_product():
# Menüden pizza seçim yapma
 #pizza = None
 print("\nLütfen bir pizza tabanı seçiniz: ")
 print("1: Klasik")
 print("2: Margarita")
 print("3: TürkPizza")
 print("4: Sade Pizza")
 pizza_type = input("Seçiminiz: ")
 
# Kullanıcının Seçimlere göre pizza oluşturma
 if pizza_type == "1":
   return KlasikPizza()
 elif pizza_type == "2":
  pizza = MargaritaPizza()
 elif pizza_type == "3":
  pizza = TurkPizza()
 elif pizza_type == "4":
  pizza = SadePizza()
 else:
  print("Geçersiz seçim.")
  exit()


# Kullanıcıdan Sos seçimi
#while True:
def select_sos():
  sos_type = input("\nLütfen sosu seçin: ")
  if sos_type == "11":
    pizza = ZeytinSosu(Pizza)
  elif sos_type == "12":
    pizza = MantarSosu(Pizza)
  elif sos_type == "13":
    pizza = KeciPeyniriSosu(Pizza)
  elif sos_type == "14":
   pizza = EtSosu(Pizza)
  elif sos_type == "15":
   pizza = SoganSosu(Pizza)
  elif sos_type == "16":
   pizza = MisirSosu(Pizza)
  else:
   print("Geçersiz seçim.")
   exit()       




def main():
    print("Hoşgeldiniz!\n")
    #menüyü ekrana yazdırma
    dosya = open("Menu.txt","r",encoding="utf-8")
    oku = dosya.read()
    print(oku)
    # ürün seçimi
    product = select_product();
    sos = select_sos()
    # miktar seçimi
    #quantity = select_quantity(product)
    # ödeme bilgileri
    tc, card_number, card_password, card_expiry, card_cvv = get_payment_info()
    # toplam fiyat hesaplama
    total_price = calculate_total_price(product)
    print("Toplam ücret: ${}}".format(total_price))
   
    

    #Veritabanı "Orders_Database.csv" dosyası
    with open("Orders_Database.csv", mode="a", newline="") as csv_file:
        fieldnames = ["Name", "TC", "Credit Card Number", "Credit Card Password", "Order Description", "Order Time"]
        writer = csv.DictWriter(csv_file, fieldnames=fieldnames)

        writer.writerow({
            'Name': [select_product],
            'TC': [tc],
            'Credit Card Number': [card_number],
            'Credit Card Password':[card_password],
            'Order Description':[f"{select_product} pizza ve {select_sos} sos"],
            'Order Time': now.strftime("%Y-%m-%d %H:%M:%S")
        })

if __name__ == "__main__":
    main()
