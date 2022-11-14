# Scraping real estate data using beautiful soup and requests on Python :

<p align="center">
  <img src="https://user-images.githubusercontent.com/74627083/158357052-1872948e-b9b6-4283-b6df-2e51d94cd098.png" />
</p>

```python
# Python program to scrape website
# and save annoucements from website
import requests
from bs4 import BeautifulSoup, NavigableString, Tag
from xml.dom import minidom
import xml.etree.cElementTree as ET
import os
import csv


URL = "https://www.mubawab.ma/fr/listing-promotion"
r = requests.get(URL)

soup = BeautifulSoup(r.content, 'html5lib')

announcements = []  # a list to store announcments links

table = soup.find('ul', attrs={'id': 'nl-list-main'})

for row in table.findAll('div',
                             attrs={'class': 'detail-promotion colAgencyContent col-8'}):
        link = row['linkref']
        # quote['theme'] = row.h5.text
        # quote['url'] = row.a['href']
        # quote['img'] = row.img['src']
        # quote['lines'] = row.img['alt'].split(" #")[0]
        # quote['author'] = row.img['alt'].split(" #")[1]
        announcements.append(link)

print(announcements)




def scrappingpage(List):
    for i in range(0,len(List)):
        link=List[i]
        offreName=""
        location=""
        price=""
        etatdavacement=""
        avgPrice=""
        classe=""
        telephones=[]
        description=""


        URL = link
        r = requests.get(URL)

        soup2 = BeautifulSoup(r.content, 'html5lib')

        announcements = []  # a list to store announcments links

        table = soup2.find('div', attrs={'class': 'immoneufPage promotionPage'})


        for row in table.findAll('h1',
                                     attrs={'class': 'SpremiumH2'}):
            offreName = row.text
        for row in table.findAll('span',
                                     attrs={'class': 'immoDetails vAlignM darkblue'}):
            try:
                location=row.text
            except Exception as e:
                location=""
        for row in table.findAll('h2',
                                 attrs={'class': 'SpremiumH2 orangeText'}):

            price=row.text
        for row in table.findAll('span',
                                     attrs={'class': 'SpremiumDetails'}):
            try:
                avgPrice = row.text
            except Exception as e:
                print(e)
        if len(table.findAll('p',attrs={'class': 'immoBadge'}))==3:
            row=table.findAll('p',attrs={'class': 'immoBadge'})[0]
            try:
                classe = row.text
            except Exception as e:
                print(e)




        for row in table.findAll('div',
                                     attrs={'class': 'promotionInfoBox lHeight1 col-1 centered'}):
            etatdavacement=row.p.text
        for row in table.findAll('span',
                                     attrs={'id': 'phoneBtnClosed'}):
            telephones.append(row.text)
        for input in table.findAll('p',
                                     attrs={'class': 'changeDescrip'}):
            try:
                soup2 = BeautifulSoup(input)

                for br in soup2.findAll('br'):
                    next_s = br.nextSibling
                    if not (next_s and isinstance(next_s, NavigableString)):
                        continue
                    next2_s = next_s.nextSibling
                    if next2_s and isinstance(next2_s, Tag) and next2_s.name == 'br':
                        text = str(next_s).strip()
                        if text:
                            description=text

            except Exception as e:
                print(e)
        print("les donnes sont:\n ", offreName, location, price, avgPrice, classe, etatdavacement, telephones,description)
        createNode(offreName, location, price, avgPrice, classe, etatdavacement, telephones, description)





            # quote['theme'] = row.h5.text
            # quote['url'] = row.a['href']
            # quote['img'] = row.img['src']
            # quote['lines'] = row.img['alt'].split(" #")[0]
            # quote['author'] = row.img['alt'].split(" #")[1]
            #announcements.append(link)


def createNode(offreName,location,price,avgPrice,classe,etatdavacement,telephones,description):


    root = ET.Element("Annonces")
    annonce = ET.SubElement(root, "annonce")

    details=ET.SubElement(annonce, "detail de l'offre", Titre=offreName)
    #ET.SubElement(doc, "field2", name="asdfasd").text = "some vlaue2"
    ET.SubElement(details,'Adresse du logement').text=location
    ET.SubElement(details, 'prix Total').text = price
    Vendeur=ET.SubElement(annonce,"Vendeur")
    tree = ET.ElementTree(root)
    tree.write("filename.xml")




    if avgPrice!="":
        ET.SubElement(details, 'Prix moyen par mètre carré').text = avgPrice

    if classe!="":
        ET.SubElement(details, 'Classe').text = classe
    if etatdavacement!="":
        ET.SubElement(details, 'Avancement des travaux').text = etatdavacement

    if description!="":
        ET.SubElement(annonce, 'Description').text = description
    if telephones!='':
        ET.SubElement(Vendeur, 'Telephone').text = telephones



    xml_str = root.toprettyxml(indent="\t")

    save_path_file = "fichier.xml"

    with open(save_path_file, "w") as f:
        f.write(xml_str)
scrappingpage(announcements)

print("le nombre d'annonce dans cette pages est:", len(announcements))

```
