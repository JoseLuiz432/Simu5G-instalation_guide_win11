# Simu5G-instalation_guide_win11
Guia para instalação do Simu5G no simulador wsl-ubuntu no Windows 11

# Computação Móvel IME-MAC5743

### Membros
  José Luiz Maciel Pimenta - 11896720
  Hamed Panjeh  - 9630952
    
Table of contents
=================
<!--ts-->
   * [EP03](#ep01-description)
      * [Pré-requisitos](#prerequisites)
      * [Intalação](#instalação)
      * [Apresentação](#apresentação)
      * [Experiment](#experiment)
<!--te-->


## EP01 Descrição
Neste EP iremos simular dispositivos se comunicando numa rede 5G. O simulador utilizado foi o [simu5G](http://www.simu5g.org/index.html). Dessa forma, será feito um tutorial de como instalar o simulador e utilizá-lo no windows 11 utilizando o wsl-ubuntu. Dividindo o Ep da seguinte forma:

1. Tutorial de instalação;
2. Tutorial para executar a primeira simulação;
3. Video da simulação;

### Pré-requisitos
Antes de iniciar você deve instalar no wsl-ubuntu os seguintes pacotes:
[OMNeT++ 6.0 Preview 11](https://github.com/omnetpp/omnetpp/releases/tag/omnetpp-6.0pre11)

```
$ wget https://github.com/omnetpp/omnetpp/releases/download/omnetpp-6.0pre11/omnetpp-6.0pre11-src-linux.tgz
$ tar -xvzf omnetpp-6.0pre11-src-linux.tgz
```

[INET 4.3.2](https://github.com/inet-framework/inet/releases/tag/v4.3.2):
```
$ wget https://github.com/inet-framework/inet/releases/download/v4.3.2/inet-4.3.2-src.tgz
$ tar -xvzf inet-4.3.2-src.tgz
```

[Simu5G](https://github.com/Unipisa/Simu5G)
```
$ git clone https://github.com/Unipisa/Simu5G.git
```

### Experimento
Para iniciar o experimento você deve "buildar" os pacotes da seguinte forma:

1. OMNet:
obs.: Podem acontecer alguns erros por falta de pacotes como o gcc e g++, então observe o erro e instale o pacote necessário.
```
$ cd omnetpp-6.0pre11
$ . setenv
$ ./configure
$ make
```

2. INET:
```
$ cd inet4.3
$ . setenv
$ make makefiles
$ make
```

2. INET:
```
$ cd Simu5G
$ . setenv
$ make makefiles
$ make
```

3. É necessário "setar" o display do wsl-ubuntu:
```
$ export DISPLAY=:0
```

4. Execute um experimento:

```
$ cd simulations/NR/ALGUM_EXPERIMENTO
$ ./run
```

### Apresentação
O vídeo apresentação de uma simulação no Simu5G -> [Video]()
