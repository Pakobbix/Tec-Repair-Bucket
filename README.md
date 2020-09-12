# Tec-Repair-Bucket

WWiU Steht für Windows with integrated Updates.											
Dieses Skript ist aus neugierde und aus dem Mangel an Automatismus unserer Firma entstanden.								 
Selbst unsere NAS-Server Lösung ist eher träge und erfordert zu oft einschreiten seitens der Techniker.							 	
Sofern der NAS nicht sowieso schon ausgeschaltet wurde, weil er das Intranet verlangsamt.								 				

Das Skript soll abhilfe schaffen.                                                                                                         

Was genau macht das Skript?                                                                                                            

Das Skript Verbindet verschiedene Tools um am ende eine Windows 10 Iso zu erstellen, die alle updates beinhaltet.                         
Man kann entweder direkt ein USB-Stick damit bespielen, oder die ISO einfach auf die Zielcomputer kopieren und von da aus bereitstellen.     
Anders als bei WSUSoffline muss nicht erst das Funktionsupdate gemacht werden, dann WSUS Client gestartet werden und dann hoffen,                        
dass man kein TempAdmin Account vorfindet.                                                           
Außer natürlich bei Windows S Mode Geräte. Da geht WSUS sowieso nicht.                                                 

Bei der Erstellten Windows ISO muss nichts weiter getan werden, als das Setup.exe ausgeführt werden. Das Setup führt automatisch das Funktions-Update aus,   
und installiert anschließend ohne fremde Einwirkung die Windows Kumulativen Updates.                                                      
Im Moment funktioniert das Skript soweit schonmal. Geplant ist noch:                                                                      

Eine Auto-Update funktion, um den prozess weiter zu automatisieren                                                                        

Das einfügen einer Setup.exe mit Parametern (/auto upgrade /dynamicupdate disable). Damit auch das Automatisch abläuft.                   

Das Automatische hinzufügen einer alle 2 Wochen auszuführenden Aufgabenplanung in Windows.                                                

Optimierungen der InVoke-WebRequest Befehle mit Progress Anzeige (Write-Progress funktioniert nicht mit der StopLoop function)