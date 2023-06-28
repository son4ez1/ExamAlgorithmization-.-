Python:
import random
import datetime


today = datetime.date.today()
all = []
for i in range(7):
    raschet = today - datetime.timedelta(days=i)
    all.append(raschet)
    #print(all)


data_izotovlenie = random.choice(all)
price = random.randint(100,1000)
crok = random.randint(1, 7)
print (f"Дата изготовления: {data_izotovlenie}")
print (f"Цена: {price}")
print (f"Срок годности: {crok}")


raz = (today - data_izotovlenie).days
#print(f"Сколько лежит уже товар: {raz}")


if raz == 0:
    print(f"Цена: {price}")
elif raz>1 and raz<=crok:
    o = (price-(price*0.2))
    print(f"Так как товар  просрочен на {raz} дн, цена: {o}")
else:
    print("Бесплатно")

C#:
Random rnd = new Random();

DateTime date = DateTime.Today; //сегод дата
DateTime seven = date.AddDays(-7); // сегодн - 7дн
DateTime six = date.AddDays(-6);
DateTime five = date.AddDays(-5);
DateTime four = date.AddDays(-4);
DateTime three = date.AddDays(-3);
DateTime two = date.AddDays(-2);
DateTime one = date.AddDays(-1);
DateTime[] all = { date, seven, six, five, four, three, two, one };

DateTime data_izgotov = all[rnd.Next(all.Length)]; // рандомно выбираем день
int crok = rnd.Next(1, 7); // срок годности
int price = rnd.Next(100, 1000); // цена

Console.WriteLine($"Дата изготовления: {data_izgotov.ToString("yyyy-MM-dd")}");
Console.WriteLine($"Цена: {price}");
Console.WriteLine($"Срок: {crok}");

int raz = (date - data_izgotov).Days;

if (raz == 0)
{
    Console.WriteLine($"Цена: {price}");
}
else if (raz >= 1 && raz<=crok)
{
    Console.WriteLine($"Товар просрочен на {raz} дн., цена {price-(price*0.2)}");
}
else {
    Console.WriteLine("Беслпатно");
}
