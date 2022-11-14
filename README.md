# Scraping real estate data using beautiful soup and requests on Python :

<p align="center">
  <img src="https://user-images.githubusercontent.com/74627083/158357052-1872948e-b9b6-4283-b6df-2e51d94cd098.png" />
</p>

\title{
Objectif du projet:
}

L'objectif du projet est de récupérer un échantillon représentatif de la base de données Mubawab.ma, afin de créer une base de données XML, puis de tester quelques requêtes Xquery et Xupdate (qui représentent l'essentiel du cours) sur cette base.

\section{Présentation du site Mubawab.ma :}

La page d'accueil du site Mubawab.ma se présente comme suit :

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-01.jpg?height=800&width=1742&top_left_y=798&top_left_x=186)

Figure 1 : page d'accueil du site Mubawab.ma
![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-01.jpg?height=656&width=1678&top_left_y=1640&top_left_x=191)

Figure 2: page d'accueil du site Mubawab.ma : SUITE 

\section{La catégorie Immobilier neuf du site Mubawab.ma:}

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-02.jpg?height=852&width=1771&top_left_y=314&top_left_x=166)

Figure 3 : Aperçu de la catégorie Immobilier neuf du site.

\section{La catégorie Vente du site Mubawab.ma:}

Immobilier Maroc > Appartements à vendre

Appartement à vendre (20116 résultats) Villa a Vendre Marrakech Pas Cher / Villa a Vendre Marrakech Salle-debain

l̇ Trier
![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-02.jpg?height=492&width=982&top_left_y=1583&top_left_x=212)

Loc. vacances

Appartement à vendre à Marjane. 3 belles

3 chambres, $140 \mathrm{~m}^{2}$

Marjane à Meknes

agréable appartement à vendre. 5 pièces, 3 chambres, 2 salles de bains, $140 \mathrm{~m}^{2}$. Ter étage. moins d'un an. revêtement: carrelage, idéal si vous souhaitez acheter un appartement à marjane. ascenseur et ...En savoir plus $\rightarrow$

\# Publié aujourdhui CONTACTER

Figure 4 : Aperçu de la catégorie Vente du site. 

\section{La catégorie Location du site Mubawab.ma:}

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-03.jpg?height=656&width=1768&top_left_y=333&top_left_x=184)

Figure 5 : Aperçu de la catégorie Location du site.

\section{La catégorie Location vacances du site Mubawab.ma:}

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-03.jpg?height=642&width=1681&top_left_y=1235&top_left_x=211)

Figure 6 : Aperçu de la catégorie Location vacances du site.

A propos du site...

Implantée depuis 2012 au Maroc, Mubawab est aujourd'hui la plateforme digitale de référence dans le secteur immobilier national avec une présence à travers tout le Royaume et disponible en Français, en Arabe, en Anglais et en Espagnol. Au Maroc, Mubawab met en relation toute personne à la recherche d'un bien immobilier (location \& vente), avec les particuliers et les acteurs professionnels du secteur.

Le site Mubawab propose des annonces qui peuvent être répartis en quatre catégories qui sont:

- Immobilier neuf. Figure 3

- Vente. Figure 4

- Location. Figure 5

- Location vacances. Figure 6

Chaque catégorie d'annonces a des caractéristiques différentes des autres, notre choix pour la conception de la base s'est restreint aux trois premières catégories puisqu'elles sont mieux structures et représentent largement la base de données du site.

\section{Conception de la base de données :}

Remarque: tous les fichiers ainsi que les résultats des requêtes Xupdate et Xquery présentés dans ce document sont disponibles $\mathrm{ICl}$.

Dans cette partie, nous allons dans cette partie présenter et expliquer en détail la base de données XML, son schéma XSD (avec son diagramme) et DTD correspondant à cette base.

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-04.jpg?height=526&width=564&top_left_y=1751&top_left_x=171)

Base de Données

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-04.jpg?height=513&width=504&top_left_y=1760&top_left_x=802)

schéma dtd

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-04.jpg?height=509&width=488&top_left_y=1762&top_left_x=1382)

schéma xsd

Figure 6 : Aperçu des fichiers XML, DTD et XSD correspondant à la base de données. 

\section{Le fichier Base de données.xml :}

\section{Voici un aperçu du contenu du fichier Base de données.xml :}

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-05.jpg?height=1249&width=1781&top_left_y=438&top_left_x=172)

Figure 7 : Aperçu du contenu du fichier base de données.xml

Le fichier présenté dans la Figure 7 est un VRAl échantillon de la base de données du site Mubawab.ma, son contenu est tiré du site officiel de Mubawab à l'aide d'un programme python du web scrapping avec la bibliothèque Scrapy. 

\section{Analyse du contenu du fichier :}

La première ligne du document est la ligne suivante :

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-06.jpg?height=127&width=1713&top_left_y=419&top_left_x=171)

Figure 8 : déclaration $X M L$ du fichier base de données.xml

Cette ligne (Figure 8 ) c'est un marquage qui fait référence à XML, elle présente la version d'XML utilisée (dans notre cas 1.0), il'y a aussi la version d'encodage dans notre cas UTF-8).

La $2^{\text {éme }}$ ligne du document est la ligne suivante :

Figure $9: 2^{e ́ m e}$ ligne du fichier base de données.xml

Cette ligne permet de lier notre fichier base de données.xml avec son schéma DTD correspondant (c'est le fichier schéma dtd.dtd : Figure 6), le schéma DTD permet de décrire les autorisations d'imbrication et l'ordre d'apparition des éléments et de leurs attributs.

La $3^{\text {éme }}$ ligne du document est la ligne suivante :

Figure $10: 3^{\text {éme }}$ ligne du fichier base de données.xml

Cette ligne permet de lier notre fichier base de données.xml avec son schéma XSD correspondant (c'est le fichier schéma xsd.xsd : Figure 6), le schéma XSD définit les mêmes choses que le schéma DTD mais il est plus détaillé et apporte beaucoup plus d'informations sur le fichier XML correspondant.

Le reste des lignes du fichier base de données.xml est la base de données, on va expliquer la structure de cette base dans la partie suivante après avoir présenté les fichiers : schéma xsd.xsd et schéma dtd.dtd 

\section{Le fichier schéma xsd.xsd :}

Voici un aperçu du contenu du fichier schéma xsd.xsd :

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-07.jpg?height=1247&width=1781&top_left_y=450&top_left_x=169)

Figure 11 : Aperçu du contenu du fichier schéma xsd.xsd

Le fichier schéma xsd.xsd (dans les figures : Figure 6 et Figure 11) a été générer à partir du fichier : base de données.xml avec XML COPY EDITOR, 

\section{Diagramme XSD de la base de données :}

\section{Ce diagramme a été générer à partir du fichier schéma xsd.xsd avec XSD DIAGRAM V1.2}

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-08.jpg?height=1261&width=1781&top_left_y=524&top_left_x=172)

Figure 12 : Diagramme XSD de la base de données. (Partie 1) 

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-09.jpg?height=1791&width=718&top_left_y=262&top_left_x=191)

Les figures: Figure 12 et Figure 13 montent bien la structure générale de notre base de données,

Figure 13 : Diagramme $\mathbf{X S D}$ de la base de données. (Partie 2). 

\section{Le fichier schéma dtd.dtd :}

Voici un aperçu du contenu du fichier schéma dtd.dtd:

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-10.jpg?height=1570&width=1760&top_left_y=455&top_left_x=168)

Figure 14 : Aperçu du contenu du fichier schéma dtd.dtd

Le fichier schéma dtd.dtd (dans les figures : Figure 6 et Figure 13) a été générer à partir du fichier : base de données.xml avec XML COPY EDITOR, 

\section{Analyse d'un exemple :}

Pour justifier la structure de la base de données choisie, Analysons l'exemple suivant (lien disponible $\mid \mathrm{IC}$ ) :

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-11.jpg?height=553&width=762&top_left_y=526&top_left_x=172)

\section{A louer meublée Appartement}

2 chambres, $200 \mathrm{~m}^{2}$

Souissi à Rabat

a louer, tres bel appartement avec terrasse a l'orangeraie du souissi. d'une superficie totale de $200 \mathrm{~m}^{2}$ dont $80 \mathrm{~m}^{2}$ de terrasse, cet appartement joliment meuble, se compose d'un salon avec coin salle a ...En savoir plus $\rightarrow$

Publié aujourdhui

Figure 15 : Exemple d'annonce de locations du site Mubawab : partie 1

\section{Description complète}

A louer, tres bel appartement avec terrasse a l'orangeraie du Souissi.

D'une superficie totale de $200 \mathrm{~m}^{2}$ dont $80 \mathrm{~m}^{2}$ de terrasse, cet appartement joliment meuble, se compose d'un salon avec coin salle a manger, une salle d'eau invites, une cuisine equipee, 2 chambres a coucher dont une avec acces a la terrasse et 2 salles de bain.

- residence securisee

- 2 places au garage

Loyer: $18000 \mathrm{dhs} / \mathrm{mois}$

* Caractéristiques supplémentaires:

Terrasse

$\checkmark$ Garage

Cuisine équipée

Emplacement

- Rabat, Rabat-Salé-Zemmour-Zaër

Figure 16: Exemple d'annonce de locations du site Mubawab : partie 2 

\section{(2) 06 (Afficher le numéro}

\section{Agence immobilière}

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-12.jpg?height=297&width=491&top_left_y=586&top_left_x=752)

Cabinet Immobilier Said Bennis

\section{Cabinet immobilier said Bennis}

Figure 17 : Exemple d'annonce de locations du site Mubawab : partie 3

À partir des figures: Figure 15, Figure 16 et Figure 17, l'annance posséde :

- Une catégorie: Location

- Une Adresse : Souissi à Rabat

- Loyer:18000 DH

- Vendeur et son numéro de telephone: Agence immobilière : Cabinet immobilier said Bennis, 0661256961 Figure 17

- Des infos : superficie, nombre de chambres, état ...etc. Figure 15 et Figure 16

- Une description: Figure 16

- Des caractéristiques supplémentaires: Figure 16 

\section{Voici le code XML correspondant à cette annonce :}

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-13.jpg?height=1320&width=1784&top_left_y=321&top_left_x=168)

Figure 18 : code XML correspondant à l'annonce dans la Figure 15

Le code XML dans la Figure 18, reprend l'annonce dans la Figure 15, tout en respectant le diagramme XSD Figure 12 

\section{Description du schéma XSD de la base de données :}

L'Architecture de la base XML est la suivante :

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-14.jpg?height=391&width=1778&top_left_y=428&top_left_x=171)

Figure 19 : Aperçu du contenu du fichier base de données.xml (de la ligne 1 à 145)

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-14.jpg?height=241&width=1778&top_left_y=904&top_left_x=171)

Figure 20 : Aperçu du contenu du fichier base de données.xml (de la ligne 3726 à 3784)

Le plan général selon lequel on a construit notre base de données est le suivant :

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-14.jpg?height=274&width=1765&top_left_y=1367&top_left_x=185)

Figure 21 : Extrait du contenu du fichier schéma xsd.xsd

Cette structure (Figure 21) a été inspirer à partir de plusieurs exemples (par exemple Figure 15) du site Mubawab,

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-14.jpg?height=171&width=1751&top_left_y=1861&top_left_x=184)

Figure 22 : L'élément Annonce de la base de données.

L'élément Annonce c'est l'élément contenant le plus de données partie dans la base de données, la base comporte 269 annonces ( $>3700$ lignes de code $\mathrm{XML}$ ). Contenu de l'élément Annonce :

- catégorie:

<!ELEMENT catégorie (\#PCDATA)>

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-15.jpg?height=507&width=1270&top_left_y=584&top_left_x=170)

L'élément catégorie est de type String.

Chaque agence doit obligatoirement avoir un seul élément catégorie.

Les trois énumérations possibles pour l'élément catégorie, sont : (Location, Vente et Immobilier Neuf)

- Adresse:

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-15.jpg?height=109&width=1162&top_left_y=1382&top_left_x=167)

<! ELEMENT Adresse (\#PCDATA)> - Prix:

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-15.jpg?height=78&width=941&top_left_y=1891&top_left_x=169)

- Loyer:

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-15.jpg?height=90&width=1022&top_left_y=2134&top_left_x=172)

L'élément Adresse est de type String.

Chaque agence doit obligatoirement avoir un seul élément

Adresse.

\section{L'élément Prix est de type Int.}

\section{L'élément Loyer est de type float.}

Chaque Annonce doit avoir impérativement soit un Prix soit un Loyer, (cela dépend de la catégorie de l'annonce). 

![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-17.jpg?height=1319&width=1443&top_left_y=251&top_left_x=206)


![](https://cdn.mathpix.com/cropped/2022_11_14_33c2c8e35f698d7a2fc0g-18.jpg?height=686&width=1704&top_left_y=334&top_left_x=189)

\section{L'élément caractéristiques_Suplementaires est de type caractéristique_SuplementairesType : c'est un type complexe. caractéristiques_SuplementairesType : est un élément complexe contenant les éléments suivants :}

- caracteristique : de type String : non obligatoire

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
