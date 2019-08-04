Bronkhort_MFC_Arduino

Program for writting and reading on a Bronkhorst's MFC with an Arduino PC Board.

Requested devices :
Bronkhorst's instrument (use the rs232 connection)
rs232 to ttl converter
Arduino's UNO PC board

"port_com_trames" 
--> create the object "monPort" with SoftwareSerial
--> choose the trame in the list for the requested parameter and send it to the MFC by "monPort.print(BHT_parameter_XX)"
--> read the MFC's answer and store it in variable R "R=monPort.readStringUntil('\n')
--> can print R on the serial monitor of the Arduino UNO "Serial.println(R)"

With the Bronkhorst's manuel "RS232 interface with FLOW-BUS protocol for digital multibus Mass Flow / Pressure instruments"
Usable datas in R (MFC's answer) must be isolated from the answer trame
--> create the variable (a String) with only needed datas by maReponse=R.substring(13,31)

"converter_n_hexaDecimal_to_n_char"
This module with inlet hexa decimal String convert each hexa decimal in a caracter regarding ASCII table
--> send the String maReponse in this module
--> return the information as caracter string, lisible.

"converter_4hexaDecimal_to_1float"
This module with inlet 4 hexa decimal convert the String in a float regarding IEEE574

"converter_1float_to_4hexaDecimal"
This module with inlet 1 float convert in a 4 hexa decimal String regarding IEEE574