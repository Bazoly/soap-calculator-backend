# Dokumentáció - soap-calculator-backend

## Lépések:

### SOAP típusú webszolgáltatás megismerése
Az első lépésem az volt, hogy utánnanéztem, hogy mi is ez a SOAP API és miben különbözik az általunk sokszor használt REST API-tól. Továbbá megnéztem még, hogy hogyan lehet leimplementálni Eclipse-ben.

### Eclipse IDE telepítése és haszálata
Ezután feltelepítettem az Eclipse-et. Kellett egy kis idő mire megszoktam az Eclipse-et az IntelliJ után. Például az Eclipse-ben az autocomplete teljesen máshogy működik, mint az IntelliJ-ben

### Dynamic Web Project elkezdése
A legtöbb időmet a projekt elindítása vette el. Többször kellett újra létre kellett hoznom a projektet, mivel különböző hibákat kaptam amikor web service-t szerettem volna készíteni.

Ezt a `NoClassFoundError` -t akkor kaptam amikor el akartam indítani a Tomcat szervert.
![NoClassFoundError](DOCUMENTATION_IMG/NoClassDefFoundError.png)

De volt olyan eset hogy ezt a hibaüzenetet kaptam az Eclipse-től: **IWAB0489E** Error when deploying Web service to Axis runtime.

#### Végül is ezekkel a beállításokkal sikerült megcsinálnom a projektet.
![Dynamic Web Project](DOCUMENTATION_IMG/Dynamic_Web_Project.png)

A Configuration résznél még hozzá kellett adnom az Axis2 Web Services-t.
![Add Axis2](DOCUMENTATION_IMG/Add_Axis2.png)

Az Axis2 Runtime helyét is meg kellett adnom a Preferences/Web Services menüpontban.
![Missing Axis2 runtime](DOCUMENTATION_IMG/Missing_Axis2_runtime.png)

### Kalkulátor implementálása
Maga a kalkulátor implementálása gyorsan ment. A lenti képen látható az implementált kalkulátor metódusai és az éppen futó Tomcat webszerver.
![Run on Tomcat server](DOCUMENTATION_IMG/Run_on_Tomcat.png)

### Kalkulátor tesztelése SoapUI segítségéval
Valami okból kifolyólag a SoapUI alkalmazást nem tudtam elindítani a parancsikonjával. Amikor a parancsikonra kattintottam így nyitotta meg a filet egy text editor-ban.
![SoapUI not run](DOCUMENTATION_IMG/SoapUI_not_run.png)

Úgyhogy megpróbáltam terminálból elindítani a shell script-ét és úgy már sikerült elindítanom a SoapUI.
![SoapUI run in the terminal 1](DOCUMENTATION_IMG/SoapUI_run_in_terminal_1.png)
![SoapUI run in the terminal 2](DOCUMENTATION_IMG/SoapUI_run_in_terminal_2.png)

Először hozzáadtam a WSDL filet a projekthez.
![Add WSDL location](DOCUMENTATION_IMG/Add_WSDL_location.png)

Majd végül leteszteltem a webszolgáltatásokat.
- Összeadás:
![SoapUI addition](DOCUMENTATION_IMG/SoapUI_addition.png)

- Kivonás:
![SoapUI subtraction](DOCUMENTATION_IMG/SoapUI_subtraction.png)

- Szorzás:
![SoapUI multiplication](DOCUMENTATION_IMG/SoapUI_multiplication.png)

- Osztás:
![SoapUI divison](DOCUMENTATION_IMG/SoapUI_divison.png)
