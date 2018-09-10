from time import *

sted=5
a=1

while True:
    navn=input("Hei! Hva heter du?")
    print("Hei", navn)
    introduksjon=input("Vil du ha en introduksjon til spillet?")
    
    if introduksjon=="Ja" or introduksjon=="ja":
        print("Du vil starte i en skog, endelig framme etter å ha lett lenge etter "
              "skatten. Rundt deg er det 9 steiner (3x3) hvor noen av dem har skrevet "
              "spørsmål på seg. Du må svare riktig for å få et hint, og hvis du "
              "svarer feil vil steinen lure deg. (Når du går til en stein med hint, " 
              "må du svare på hintet før du går videre, selv om du har vært der før. "
              "Men da gjør det ingenting om du svarer feil hvis du har fått hintet tidligere.) "
              "Skatten ligger bare ved én av steinene, ved alle de andre venter"
              "døden: med andre ord, hvis du graver feil sted vil du dø.")
        sleep(15)
    
    print(" ")
    print("""Dette er kommandoene du kan bruke:
        nord: for å flytte deg én stein nordover
        sør: for å flytte deg én stein sørover
        øst: for å flytte deg én stein østover
        vest: for å flytte deg én stein vestover
        grav: for å grave i ruta du står i""")
        
    sleep(10)
    print(" ")
    print("Nå starter spillet")
    sleep(2)
    print("Du står i midten av banen, hvor vil du gå?")
    
    while a==1:
        bevegelse=input()
        if bevegelse=="nord":
            sted-=3
        elif bevegelse=="sør":
            sted+=3
        elif bevegelse=="øst":
            sted+=1
        elif bevegelse=="vest":
            sted-=1
        elif bevegelse=="grav":
            if sted==6:
                a+=1
            else:
                a-=1
        else:
            print("Dette er ikke en kommando")
        
        if sted<=0 or sted>=10:
            print("Du har gått ut av området med steiner. Gå tilbake samme veien som du kom.")
        if sted==1 or sted==2 or sted==6 or sted==7:
            print("Her er det ingenting, men du kan jo grave om du vil, eller gå videre da...")
        if sted==3:
            print("Skriv de neste fem desimalene til pi")
            svar=input("3,14")
            if svar=="15926":
                print("Skatten ligger ved steinen til venstre for steinen som spør etter Eulertallet")
            else:
                print("Skatten ligger ved steinen til høyre for steinen som spør etter Eulertallet")
        if sted==4:
            print("Hvilket tall er yokto? (skriv uten parenterser)")
            svar=input()
            if svar=="10E-24" or svar=="10^-24":
                print("Skatten ligger ved en stein som har fem steiner rundt seg")
            else:
                print("Skatten ligger ved en stein som har tre steiner rundt seg")
        if sted==5:
            print("Nå er du der du starta (i midten). Her ligger det ikke noe hint, men du kan grave, eller gå videre.")
        if sted==8:
            print("Skriv de neste 10 desimalene til e")
            svar=input("2,718")
            if svar=="2818284590":
                print("Steinen i nord-østre hjørne lyver!")
            else:
                print("Steinen i sør-østre hjørne lyver!")
        if sted==9:
            print("Hva er formelen for energi i masse?")
            svar=input("e=")
            if svar=="m*c^2" or svar=="mc^2" or svar=="m*cE2" or svar=="mcE2":
                print("Skatten ligger på den østlige steinraden")
            else:
                print("Skatten ligger på den vestlige steinraden")
    
    while a==2:
        print("Du fant skatten, gratulerer", navn, "!!")
        if input("Vil du spille igjen?")=="ja" or input("Vil du spille igjen?")=="Ja":
            a-=1
            
    while a==0:
        print("Gratulerer", navn, ", du har gravd opp døden....")
        if input("Vil du spille igjen?")=="ja" or input("Vil du spille igjen?")=="Ja":
            a+=1
