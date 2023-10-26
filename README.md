# Samsung-Book-X40-Hackintosh

### Sobre o funcionamento no Samsung Book X40 (NP550XCJ-XF1BR)


<p align="center">
  <img width="500" height="500" src="https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/b606c576-8549-4b84-b737-b18d165dc012">
</p>

Dispositivo | Status
------------- | ------------
| 🤖 Intel® Core™ i5-10210U | ✅ Funciona Normalmente |
| 💻 Gráficos UHD Intel® 620 | ✅ Funciona Normalmente |
| 💻 Nvidia GeForce Mx110 | ❌ Não Funciona |
| 🔥 8GB de RAM | ✅ Funciona Normalmente |
| 📁 SanDisk SSD Plus 480GB | ✅ Funciona Normalmente |
| 🛜 Wi-fi | ✅ Funciona Via HeliPort |
| 📡 Bluetooth | ✅ Funciona Normalmente |
| 🖱️ TouchPad e Gestos | ✅ Funciona Normalmente |
| 🔊 Aúdio | ✅ Funciona Normalmente |
| ☀️ Brilho da Tela | ❌ Não Funciona |
| 🪫 Carregamento e Bateria | ✅ Funciona Normalmente |


![X40-Hackin-Info](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/b76d50e2-ed8d-4c50-b671-4384f5b7cc48)


## Guia de Instalação
Nesse tópico irei abordar como proceder com a instalação do MacOS Big Sur no Samsung Book X40.

❗Vale ressaltar que eu fiz algumas alterações no meu notebook, como por exemplo a substituição do HD de fábrica por um SSD, algo que eu recomendo expressamente para realizar o procedimento abaixo e obter sucesso.

### Índice
- <a href="#o-que-será-necessário">(Passo 1) O que será necessário</a>
- <a href="#criando-o-pen-drive-bootável">(Passo 2) Criando o Pen Drive Bootável</a>
- <a href="#configurando-a-bios">(Passo 3) Configurando a BIOS</a>
- <a href="#instalando-o-macos">(Passo 4) Instalando do MacOS</a>
- <a href="#instalação-concluída-e-agora">(Passo 5) Instalação concluída e agora?</a>
- <a href="#configurar-boot-sem-pendrive">(Passo 6) Configurar boot sem pendrive</a>
- <a href="#configurando-o-wi-fi">(Passo 7) Configurando o Wi-Fi</a>
- <a href="#alterando-o-serial">(Passo 8) Alterando o Serial</a>
- <a href="#créditos">Créditos</a>

#### O que será necessário
Antes de tudo é importante ter a imagem do Big Sur e a EFI (disponível nesse repositório), como também alguns softwares que iram ser necessários para que a instalação seja bem sucedida, abaixo listo o que será necessário e onde pode ser feito o download.
Algo que vale descatar é que caso você só tenha a máquina que fará a instalação do macOS veja <a href="#outra-forma-de-instalar"> Outra forma de Instalar</a>

Item | Download
------------- | ------------
| PenDrive 16GB| Obrigatório |
| Mouse USB| Obrigatório |
| Imagem do Big Sur| [⬇️ Download](https://www.olarila.com/topic/6278-olarila-vanilla-images-macos-installer/) |
| EFI| [⬇️ Download]([https://www.olarila.com/topic/6278-olarila-vanilla-images-macos-installer/](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/releases/download/v1.0/SamungBookX40-BigSur.zip)) |
| Balena Etcher| [⬇️ Download](https://etcher.balena.io/#download-etcher) |
| Python | [⬇️ Download](https://www.python.org/downloads/) |
| ProperTree| [⬇️ Download](https://github.com/corpnewt/ProperTree) |
| GenSMBIOS | [⬇️ Download](https://github.com/corpnewt/GenSMBIOS) |
| MountEFI | [⬇️ Download](https://github.com/corpnewt/MountEFI) |
| HeliPort| [⬇️ Download](https://github.com/OpenIntelWireless/HeliPort)|

❗É indispensável ter um pendrive de no mínimo 16GB e um mouse usb, pois o touchpad e teclado só funcionarão alguns passos após a instalação.

#### Criando o Pen Drive Bootável
Com a imagem do Big Sur em mãos e um pendrive de no mínimo 16GB abra o software Balena Etcher siga os seguintes passos:
1. Escolha a opção "Flash from file" e selecione a imagem que você fez o download;
2. Após isso escolha "Select target" e selecione o seu pendrive;
3. Em seguida clique em flash e aguarde processo de criação do pendrive bootável, essa etapa leva um tempo.

![Balena Etcher](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/29b62940-d695-4d69-aea7-f4bd635fed3d)

#### Configurando a BIOS
Desligue a máquina e insira o pendrive.
Ao ligar a máquina aperte continuamente a tecla "F2" até que a mesma inicie a tela de configurações da BIOS.

![Samsung BIOS](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/9e3981c2-3778-4adb-89c1-54a446d0f510)

Após entrar nessa tela faça as seguintes configurações:
- Na aba "Security" clique em "TPM Configuration" em seguida desabilite a opção "TPM Device";
- Na aba "Boot" desabilite a opção "Secure Boot Control";
- Ainda na aba "Boot" acesse "Boot Device Priority" e na opção "Boot Option #1" selecione o seu pendrive;

Feito isso basta clicar em "Save" no lado direito que o computador irá iniciar o boot no pendrive.

#### Instalando o MacOS

❗Nessa etapa é de suma importância o mouse estar conectado no notebook para ser possível realizar a instalação.

- Após o boot selecione a opção "Install macOS Big Sur".

- Vá até "Utilitário de Disco" selecione seu HD ou SSD que deseja realizar a instalação e em seguida no topo do janela selecione "Apagar" e selecione o formato APFS.

- Feche a aba de "Utilitário de Disco" e clique em "Instalação do macOS Big Sur", aceite os termos, selecione seu disco formatado anteriormente e aguarde o fim da instalação.

#### Instalação Concluída e Agora?
Antes de configurar seu usuário é necessário mudar o EFI de boot, sendo assim desligue o computador e em outro formate o pendrive e coloque os seguintes arquivos nele:

- A pasta EFI;
- Python
- ProperTree;
- MountEFI
- GenSMBIOS
- HeliPort

Feito isso basta dar boot novamente no computador através do pen-drive, o sistema já estará instalado e o pendrive vai ser utilizado para dar boot.

#### Configurar Boot Sem PenDrive
Com a máquina inicializada, já na tela do macOS pronto para uso é necessário configurar alguns arquivos para que o pendrive não seja mais necessário para inicializar a máquina, sendo assim:
- Faça a instalação do Python;
- Na pasta do "MountEFI" clique em "Mount EFI Automator Quick Action.zip" e execute o arquivo extraído fazendo sua instalação.

![Instalação Mount EFI](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/f463b0bf-32c7-479e-8438-afc1e7583425)

Feito isso na tela inicial clique em "Finder" depois em "Preferências" e habilite "Discos rígidos".
![Habilitar Discos Rígidos](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/59545367-5bc9-496b-9a00-257a98a52383)

Dessa forma a tela inicial irá mostrar os volumes dos discos rígidos. Clique com o botão direito (no caso do mac os dois dedos) no volume onde está a instalação e em seguida em "Mount EFI" e digite sua senha, assim aparecerá um novo volume na tela inicial.

![Captura de Tela 2023-10-26 às 12 56 04](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/c84a0c32-4c50-469e-93f5-e2dc3d24b5ea)

Entre no volume "System" e apague a pasta EFI, posteriormente copie a pasta EFI que estiver no pendrive para essa pasta.
Pronto, agora o sistema inicializará sem o pendrive.

#### Configurando o Wi-Fi
Como mencionado no início desse README o wi-fi só funcionará via HeliPort, sendo assim, basta executar o arquivo "HeliPort.dmg" e realizar sua instalação. Após instalado basta abri-lo e selecionar a rede Wi-Fi através do segundo ícone de Wi-Fi no canto superior direito do macOS.

#### Alterando o Serial
Essa é uma etapa crucial para garantir que o macOS possua algumas funcionalidades, pois iremos colocar um serial que a Apple reconheça como sendo um dispositivo dela.
- Para começar execute o "GenSMBIOS.command", após isso digite 3 e pressione a tecla "Enter", aguarde o programa baixar os pacotes necessários e pressione "Enter" novamente;
![GenSMBIOS 1](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/cea0c9a2-52bb-4d0c-938e-ce0dfc4430f4)
- Nessa tela digite "MacBookPro16,3" e precione "Enter";
![GenSMBIOS 2](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/da4413a8-9c62-4910-9dd0-576cb45ea000)
- Ele irá gerar alguns seriais que usaremos adiante.
![GenSMBIOS 3](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/49d18e07-8063-4479-b6aa-79e03f954a9a)
- Mantenha a aba com os códigos gerados aberta e execute o "ProperTree.command"
- Com o ProperTree aberto, clique em "File" em seguida "Open" e selecione o arquivo "config.plist" disponível em "SYSTEM/EFI/OC"
![ProperTree 1](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/85a303f1-d28c-4555-a289-2887e4877645)
- Após abrir o arquivo substitua os seguintes campos da aba "PlataformInfo/Generic":
  - O valor "Board Serial" do "GenSMBIOS" deve substituir o valor de "MLB"
  - O valor "Serial" deve substituir o valor do "SystemSerialNumber"
  - O valor "SmUUID" deve substituir o valor do "SystemUUID"

ProperTree | GenSMBIOS
------------- | ------------
| MLB| Board Serial |
| SystemSerialNumber | Serial |
| SystemUUID| SmUUID |

![ProperTree 2](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/acb2ea81-39fb-404e-8852-c40f375de61d)

Feito isso basta salvar as alterações do "Config.plist" e reiniciar o computador.

##### Agora sua máquina está pronta !!!

## Créditos

A EFI base eu utilizei do [taarkov](https://github.com/taarkov/Honor-MagicBook-X15-Hackintosh) que fez o hackintosh num Honor MagicBook X15 que possui o mesmo processador do Samsung Book X40 (i5-10210u).
Fora isso adicionei algumas Kexts adicionais (cujas quais não me recordo de onde retirei) para que houvesse pleno funcinamento de alguns dispositivos.

[➡️ taarkov](https://github.com/taarkov/)
[➡️ Python](https://www.python.org/downloads/)
[➡️ ProperTree](https://github.com/corpnewt/ProperTree)
[➡️ GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
[➡️ MountEFI](https://github.com/corpnewt/MountEFI) 
[➡️ HeliPort](https://github.com/OpenIntelWireless/HeliPort)
