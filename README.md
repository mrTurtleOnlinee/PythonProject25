# PythonProject25
werken aan mijn portfolio, updaten vaardigheden

Hier is een eenvoudige versie, alsof het in een kladbestand wordt bijgehouden:

---

Week 1 - De Basis van Python

Opdracht 1: Naam vragen en afdrukken

Fout 1: Ik heb de input() functie niet gebruikt en een naam hardcoded ingevuld.  
```python
naam = "John"
print("Hallo, naam!")  # Fout: "naam" is als string gebruikt in plaats van de variabele.
```
Oplossing:
```python
naam = input("Wat is je naam? ")
print(f"Hallo, {naam}!")
```

Fout 2: Ik ben vergeten een f-string te gebruiken in de print-statement.  
```python
print("Hallo, {naam}")  # Dit print letterlijk "Hallo, {naam}" in plaats van de variabele.
```
Oplossing:
```python
print(f"Hallo, {naam}")
```

Fout 3: Ik heb de haakjes vergeten bij input().  
```python
naam = input "Wat is je naam?"  # Fout: Haakjes ontbreken.
```
Oplossing:
```python
naam = input("Wat is je naam?")
```

Aantekeningen:  
- Altijd een f-string gebruiken bij variabelen in print-statements.  
- input() moet altijd haakjes hebben.  
- Check of de gebruiker iets invult.

---

Opdracht 2: Seconden in een dag berekenen

Fout 1: Ik heb een rekenfout gemaakt en de verkeerde operator gebruikt.  
```python
seconden_per_dag = 60 * 60 + 24  # Fout: De +24 hoort niet, het moet een vermenigvuldiging zijn.
```
Oplossing:
```python
seconden_per_dag = 60 * 60 * 24
```

Fout 2: Ik heb vergeten het resultaat te printen.  
```python
seconden_per_dag = 60 * 60 * 24
```
Oplossing:
```python
print(f"Er zitten {seconden_per_dag} seconden in een dag.")
```

Fout 3: Ik heb input() gebruikt zonder dat het nut heeft.  
```python
seconden_per_dag = int(input("60 * 60 * 24"))
```
Oplossing:
```python
seconden_per_dag = 60 * 60 * 24
```

Aantekeningen:  
- Zorg ervoor dat je de juiste operatoren gebruikt (* voor vermenigvuldiging, niet +).  
- Print altijd het resultaat, anders zie je niets.  
- input() is hier niet nodig.

---

Week 2 - OOP, Bestandsbeheer, Modules

Opdracht 1: Car Class maken

Fout 1: Ik heb geen self gebruikt in de constructor.  
```python
class Car:
    def __init__(merk, model, bouwjaar):  # Fout: Self ontbreekt.
        merk = merk
        model = model
        bouwjaar = bouwjaar
```
Oplossing:
```python
class Car:
    def __init__(self, merk, model, bouwjaar):
        self.merk = merk
        self.model = model
        self.bouwjaar = bouwjaar
```

Fout 2: Ik probeerde een niet-bestaande methode te gebruiken.  
```python
auto1 = Car("Toyota", "Corolla", 2020)
print(auto1.get_info())  # Fout: get_info() bestaat niet.
```
Oplossing:
```python
class Car:
    def toon_info(self):
        return f"{self.merk} {self.model} uit {self.bouwjaar}"
```

Fout 3: Ik heb een spelfout in de methode-naam.  
```python
class Car:
    def tooninfo(self):  # Fout: Moet "toon_info" zijn voor consistentie.
        return f"{self.merk} {self.model} uit {self.bouwjaar}"
```

Aantekeningen:  
- Altijd self toevoegen in de constructor (__init__).  
- Methoden moeten correcte namen hebben.  
- Fouten voorkomen: Gebruik print(auto1.__dict__) om te debuggen.

---

Opdracht 2: CSV-bestand inlezen

Fout 1: Ik heb het verkeerde pad gebruikt.  
```python
df = pd.read_csv("downloads/customers-100.csv")  # Fout: Bestand staat in Downloads, niet in de projectmap.
```
Oplossing:
```python
df = pd.read_csv(r"C:\Users\berna\Downloads\customers-100.csv")
```

Fout 2: Ik heb de verkeerde delimiter gebruikt.  
```python
df = pd.read_csv("customers-100.csv", delimiter=";")  # Fout: Misschien is de delimiter een komma.
```
Oplossing:
```python
df = pd.read_csv("customers-100.csv", delimiter=",")
```

Fout 3: Ik probeer een niet-bestaande kolom op te vragen.  
```python
print(df["prijs_per_product"])  # Fout: Kolomnaam bestaat misschien niet.
```
Oplossing:
```python
print(df.columns)  # Dit laat alle kolomnamen zien om te controleren welke correct is.
```

Aantekeningen:  
- Pad goed instellen als het bestand niet gevonden wordt.  
- df.columns gebruiken om kolomnamen te checken.  
- Delimiter (, of ;) controleren als de data niet correct wordt weergegeven.

---

Week 3 - Web Scraping en Automatisering

Opdracht: Wikipedia titel scrapen

Fout 1: Ik ben requests vergeten te installeren.  
```python
import requests
from bs4 import BeautifulSoup
```
```bash
ModuleNotFoundError: No module named 'requests'
```
Oplossing:
```bash
pip install requests beautifulsoup4
```

Fout 2: Ik scrape een verkeerde tag.  
```python
titel = soup.find("h2").text  # Fout: Wikipedia-titels staan in <h1>.
```
Oplossing:
```python
titel = soup.find("h1").text
```

Fout 3: De website blokkeert mijn scraper.  
```python
response = requests.get(url)  # Fout: Geen user-agent meegegeven.
```
Oplossing:
```python
headers = {"User-Agent": "Mozilla/5.0"}
response = requests.get(url, headers=headers)
```

Aantekeningen:  
- pip install requests beautifulsoup4 installeren als modules ontbreken.  
- Gebruik "h1" in soup.find() voor titels.  
- User-Agent meegeven als websites scraping blokkeren.

---

Dit document houdt bij welke fouten ik heb gemaakt bij verschillende opdrachten en hoe ik ze kan oplossen.
