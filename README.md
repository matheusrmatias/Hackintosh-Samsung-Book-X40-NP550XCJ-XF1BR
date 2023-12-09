# Samsung-Book-X40-Hackintosh

### Sobre o funcionamento no Samsung Book X40 (NP550XCJ-XF1BR)


<p align="center">
  <img width="500" height="500" src="https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/983526c0-73de-4359-9eb5-95d8be524db7">
</p>

<p align="center">

| Dispositivo                         | Status                  |
------------------------------------- | ----------------------- |
| 🤖 Intel® Core™ i5-10210U           | ✅ Funciona Normalmente |
| 💻 Gráficos UHD Intel® 620          | ✅ Funciona Normalmente |
| 🔥 8GB de RAM                       | ✅ Funciona Normalmente |
| 📁 SanDisk SSD Plus 480GB           | ✅ Funciona Normalmente |
| 🛜 Wi-fi Intel Wireless-AC 9462     | ✅ Funciona Nativamente |
| 📡 Bluetooth Intel Wireless-AC 9462 | ✅ Funciona Nativamente |
| 🌐 Realtek PCIe                      | ➖ Não Testado          |
| 🖱️ TouchPad HID                     | ✅ Funciona Normalmente |
| ⌨️ Teclado P/2                       | ✅ Funciona Normalmente |
| 🔊 Aúdio                            | ✅ Funciona Normalmente |
| 🪫 Carregamento e Bateria           | ✅ Funciona Normalmente |
| ☀️ Brilho da Tela                   | ❌ Não Funciona         |
| 💻 Nvidia GeForce Mx110             | ❌ Não Funciona         |

</p>

![Estado do Mac](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/46ad75f8-2601-4de7-83a8-ef8239ab48f3)


## Guia de Instalação
Nesse tópico irei abordar como proceder com a instalação do MacOS Big Sur no Samsung Book X40.

❗Vale ressaltar que eu fiz algumas alterações no meu notebook, como por exemplo a substituição do HD de fábrica por um SSD, algo que eu recomendo expressamente para realizar o procedimento abaixo e obter sucesso.

### Índice

- [🏁 O que será necessário](#-o-que-será-necessário)
- [💿 Alterando os Seriais](#-alterando-os-seriais)
- [💾 Fazendo o pen-drive de boot](#-fazendo-o-pen-drive-de-boot)
- [🔧 Configurando a BIOS](#-configurando-a-bios)
- [🍎 Instalando o MacOS](#-instalando-o-macos)
- [💾 Configurando EFI no macOS](#-configurando-efi-no-macos)

#### 🏁 O que será necessário
Item | Download
------------- | ------------
| PenDrive 4GB (mínimo)| Obrigatório |
| Imagem de Recovery | [Veja Aqui](macrecovery/README.md) |
| EFI| [⬇️ Download](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/releases/download/v1.0/SamungBookX40-BigSur.zip) |
| Python | [⬇️ Download](https://www.python.org/downloads/) |
| OCAuxiliaryTools | [⬇️ Download](https://github.com/ic005k/OCAuxiliaryTools/releases/tag/20230022) |

#### 💿 Alterando os Seriais
Está parte é extremamente importante para que a Apple reconheça o notebook como sendo oficial e liberando todos os recursos. Sendo assim:
- Efetue o download da EFI dísponivel neste repositório;
- Efetue o download do OCAuxiliaryTools;

Abra o OCAT (OCAuxiliaryTools), no canto superior esquerdo clique em `File`, depois em `Open` e selecione o arquivo `config.plist` dentro da pasta `EFI/OC`:

![OCAT Open File](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/1eff5556-e7d4-4d91-a8a4-04aabed2aa02)

Após isso clique em `PI (PlataformInfo)` na lateral esquerda logo após em `Genarate` na linha de `SystemProductName` e salve logo em seguida.

![Captura de tela 2023-12-09 174223](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/d46802cc-8563-4006-8979-576270fab407)

#### 💾 Fazendo o pen-drive de boot
Nesta etapa siga os seguintes passos:
- Formate o pen-drive para o sistema de arquivo `FAT-32`;
- Mova a pasta EFI (com os serais já alterados) para a raiz do pen-drive;
- Gere a imagem de recovery [aqui](macrecovery/README.md);
- Mova a pasta `com.apple.recovery.boot` para a raiz do pen-drive;

![Pen-Drive](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/97cfff5c-a0e6-437b-9bce-520d42debd38)


Pronto, o pen-drive está pronto para dar boot.

#### 🔧 Configurando a BIOS
Desligue a máquina e insira o pendrive.
Ao ligar a máquina aperte continuamente a tecla `F2` até que a mesma inicie a tela de configurações da BIOS.

![Samsung BIOS](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/9e3981c2-3778-4adb-89c1-54a446d0f510)

Após entrar nessa tela faça as seguintes configurações:
- Na aba `Security` clique em `TPM Configuration` em seguida desabilite a opção `TPM Device`;
- Na aba `Boot` desabilite a opção `Secure Boot Control`;
- Ainda na aba `Boot` acesse `Boot Device Priority` e na opção `Boot Option #1` selecione o seu pendrive;

Feito isso basta clicar em `Save` no lado direito que o computador irá iniciar o boot no pendrive.

❗ Caso dê erro de boot faça o seguinte:
- Quando o computador estiver iniciando o boot no pen-drive presisone as teclas `Windows` + `Alt` + `r` até que apareça a logo da Apple;
- Pressionar essar teclas resetará a nvram e forçará o boot na imagem de recuperação;


#### 🍎 Instalando o MacOS
Nessa parte é importante estar próximo à uma rede Wi-Fi, preferencialmente estável, para ser possível realizar o download e instalação do macOS.

Primeiro acesse `Disk Utility` e formate a seu armazenamento para `APFS`

![Captura de tela 2023-12-09 181124](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/5a00fd9e-9f90-4371-be1b-6aa85b9450fe)

Logo em seguida vá em `REinstall macOS Big Sur` e prossiga normalmente com a instalação

#### 💾 Configurando EFI no macOS
Essa etapa é essencial para que o sistema **inicialize sem o pen-drive**, sendo assim, após realizar toda a instalação e o macOS já abrir na tela inicial, faça:

- Clique em `Finder` no canto superior esquerdo e depois em `Preferências` e ative `Discos rígidos`

![Habilitar Discos Rígidos](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/59545367-5bc9-496b-9a00-257a98a52383)

- Abra o `Terminal` e digite o seguinte comando:
  ```zsh
  sudo su -
  ```
- Digite sua senha e pressione `Enter`;
- Digite o seguinte comando:
  ```bash
  diskutil list
  ```
- Após isso digite o seguinte comando com o identificador do `EFI` na lista que o último comando exibiu:
  ```bash
  diskutil mount disk#s#
  # Substitua o '#' pelo correspondente na lista
  ```
![Disco no Terminal](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/d255c297-491e-4b84-9b36-d146c1ac2f90)

O armazenamento da `EFI` agora ficará disponível na tela inicial, abra e cole a pasta `EFI` do pen-drive diretamente nela:

![Captura de Tela 2023-12-09 às 19 06 12](https://github.com/matheusrmatias/Hackintosh-Samsung-Book-X40-NP550XCJ-XF1BR/assets/115509118/001b2e55-241b-4c82-87c9-2e5e24c6103a) 

Ejete o pen-drive e reinicie o computador.

## Pronto MacOS instalado com sucesso!!!

[def]: #samsung-book-x40-hackintosh