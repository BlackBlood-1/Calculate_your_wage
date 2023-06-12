# Calculate_your_wage
Calculate how much you earn in file and the total amount you have earned
import csv
wages = []
new = 0
wagenew = 0

Date = input("Enter the date of work ")
Hours = float(input("Enter the hours worked "))
#wage per hour --> WPH
WPH = float( input ("Enter your hourly wage "))
Sum = Hours * WPH

with open("wage.csv", "a") as file:
    writer = csv.DictWriter(file, fieldnames = ["Date","Hours", "Sum"])
    writer.writerow({"Date":Date, "Hours": Hours, "Sum": Sum})
with open("wage.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        wages.append({"Sum": row["Sum"]})
for wage in wages:
    wagenew = float(f"{wage['Sum']}")
    new = new + wagenew
    print(new)
Total = new
with open("wageT.csv", "a") as file:
    writer = csv.DictWriter(file, fieldnames = ["Date","Hours", "Sum","Total"])
    writer.writerow({"Date":Date, "Hours": Hours, "Sum": Sum, "Total":Total})
