## Configuração do ambiente Arduino

### Linux
  
1. Instalação do Arduino  
Na linha de comando do Manjaro Linux:  

> sudo pacman -S arduino  

2. Instalando ESP8266 Add-on no Arduino IDE:  
   
2.1 No Arduino IDE, menu File > Preferences  
Preencher o campo "URLs adicionais para gerenciadores de placas" com o endereço:  
http://arduino.esp8266.com/stable/package_esp8266com_index.json  

Nota: pode-se salvar vários endereços, separando-os por vírgula.

2.2 Open the Boards Manager. Go to Tools > Board > Boards Manager…  

2.3 Pesquisar por ESP8266 e instalar o pacote “ESP8266 by ESP8266 Community“:

## Testando a porta serial  
Na linha de comando:  

> sudo dmesg | grep tty

Neste resultado foi encontrada a placa _CH341-uart_ na porta USB _ttyUSB0_.

    [11460.126173] usb 1-2: ch341-uart converter now attached to ttyUSB0

Dar permissao ao usuario comum acessar a serial:  

> sudo chmod 777 /dev/ttyUSB0  

Permissão para seriais ao inicializar sistema.  
Crie o arquivo:  

    /etc/udev/rules.d/60-serial.rules 
 
coloque dentro:  

    #KERNEL=="ttyS0", MODE="0666"  
    KERNEL=="ttyUSB*", MODE="0777"
 
Rode isso no terminal também para adicionar seu usuario no grupo uucp

> sudo gpasswd -a [nome-usuario] uucp 


Referência:  
- RANDOM NERD TUTORIALS. Disponivel em https://randomnerdtutorials.com/how-to-install-esp8266-board-arduino-ide/. Acesso em 02/09/2019.  
- Como usar o adaptador USB para ESP8266 ESP-01. Disponivel em https://www.arduinoecia.com.br/adaptador-usb-para-esp8266-esp-01/. Acesso em 02.09.2019.
- ArchLinux. Trabalhando com a porta serial no Linux. https://wiki.archlinux.org/index.php/working_with_the_serial_console#Graphical_front-ends. Acesso em 02.09.2019.  
- Configurando a porta serial no Linux. http://www.help.market.com.br/linux/index.html?testar_porta_serial.htm. Acesso em 02.09.2019.
- 
  

## Instalação do Visual Studio Code  

   Na linha de comando do Manjaro Linux:  
   > sudo pacman -S code

   Referência:  
   - Wiki ArchLinux. Visual Studio Code.  [https://wiki.archlinux.org/index.php/Visual_Studio_Code].

**Configuração da placa ESP8266 ESP-01**  

Referência:  
- sasa