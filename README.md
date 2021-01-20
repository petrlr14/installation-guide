# Cosas a instalar

## **Customizaci&oacute;n de la terminal** :art:

Pasamos mucho tiempo en la terminal, por ello, queremos que nuestro tiempo en ella sea lo m&aacute;s productivo y amigable posible.

- ## zsh
  Bash es el shell predeterminado donde sea que veas. Y est&aacute; bien, pero puede ser mejor. Personalmente prefiero utilizar <a href="https://www.zsh.org/">zsh</a> por su uso interactivo. Su instalaci&oacute;n es sencilla, ya que se encuentra alojado en el manejador de paquetes de la distribuci&oacute;n:
  - ### Ubuntu y derivados
  ```bash
  sudo apt install zsh
  ```
  - ### OpenSUSE
  ```bash
  sudo zypper install zsh
  ```
  No necesitamos hacer nada m&aacute;s por el momento porque se configurar&aacute; con el siguiente elemento.
- ## Oh My ZSH!
  [Oh My ZSH!](https://ohmyz.sh) es un framework de zsh. Es quien nos permitir&aacute; configurar, personalizar y extender las funcionalidades que ya nos provee zsh. El se encargara de configurar los plugins, temas y demas que utilizaremos.
  - ### Utilizando cURL
  ```bash
  sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```
  - ### Utilizando Wget
  ```bash
  sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
  ```
  Luego de ejecutar el comando empezaremos un wizard para configurar tanto zsh como Oh My ZSH!
- ## Plugins

  Los elementos que nos permite sentirnos con mayor velocidad en la terminal son sin duda los plugins que podemos instalar a On My Zsh! Aqu&iacute; los que utilizo:

  - ### Autosuggestions
    El plugin [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) nos permite habilitar una muy util funcionalidad que esta presente en el shell [Fish](http://fishshell.com/). Lo que hace es, a partir de comandos que ya hemos escrito, mostrar sugerencias de autompletado. Primero debemos clonar el repositorio localmente:

  ```bash
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  ```

  Luego tenemos que agregar _zsh-autosuggestions_ a la lista de plugins en el archivo de configuraci&oacute;n _~/.zshrc_:

  ```bash
  plugins=(zsh-autosuggestions)
  ```

  - ### Highlighting
    El plugin [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) nos permite habilitar una muy util funcionalidad que esta presente en el shell [Fish](http://fishshell.com/). Lo que hace es, mostrar con colores los comandos reconocidos por nuestra terminal . Primero debemos clonar el repositorio localmente:

  ```bash
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  ```

  Luego tenemos que agregar _zsh-syntax-highlighting_ a la lista de plugins en el archivo de configuraci&oacute;n _~/.zshrc_:

  ```bash
  plugins=(zsh-autosuggestions zsh-syntax-highlighting)
  ```

  - ### Fzf
    [Fzf](https://github.com/junegunn/fzf) no es en realidad un plugin que se instala con Oh My ZSH!, pero al intalarse se integra y se autoconfigura en el archivo <i>~/.zshrc</i>. Para instalaci&oacute;n solo se deben ejecutar 2 comandos:

  ```bash
  $ git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
  $ ~/.fzf/install
  ```

Luego de terminar las intalaciones se deben realizar los cambios del archivo _~/.zshrc_ . Simplemente tenemos que ejecutar el comando:

```bash
source ~./zshrc
```

- ## Tema

  Este apartado puede ser muy volatil, pero los ultimos a&ntilde;os he utilizado el tema [Powerlevel10k](https://github.com/romkatv/powerlevel10k) y no he utilizado m&aacute;s de lo que el propio wizard me proporciona.

  Para la instalaci&oacute;n del tema haremos uso de Oh My ZSH! Primero debemos bajar el tema con `git`

  ```bash
  git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
  ```

  Luego debemos configurar el tema en el archivo _~/.zshrc_:

  ```bash
  ZSH_THEME="powerlevel10k/powerlevel10k"
  ```

  Antes de empezar con la configuraci&oacute;n del tema deberemos instalar una fuente que soporte de glifos y s&iacute;mbolos que se necesitan. Las recomendadas son las siguientes:

  - [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
  - [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
  - [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
  - [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

  Habiendo descargado la fuente que deseamos, instalarla en nuestro sistema y configurar nuestra terminal para que la utilice.

  Ahora tenemos que ejecutar el comando:

  ```bash
  source ~./zshrc
  ```

  Al hacer esto empezar&aacute; el proceso de configuraci&oacute;n del tema. Configurar seg&uacute;n el mood.

## **Herramientas** :wrench:

- ### No gr&aacute;ficas

  - Nvm

    La forma m&aacute;s sencilla de instalar [Node.js](https://nodejs.org/en/) es utilizando [nvm](https://github.com/nvm-sh/nvm). Su instalaci&oacute;n es muy sencilla:

    - cURL

    ```bash
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
    ```

    - Wget

    ```bash
    wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
    ```

    Solamente ejecutando uno de los comandos anteriores nvm ya queda instalado en el sistema. Ahora solo falta notificarle a nuestra shell de la existencia de nvm. Para ello tenemos que agregar la siguientes lineas al final del archivo de configuraci&oacute;n de nuestra shell:

    ```bash
    export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"

    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
    ```

    Ahora tenemos que ejecutar el comando:

    ```bash
    source ~./zshrc
    ```

  - Docker

    Para esta instalaci&oacute;n solamente pondre los comandos para sistemas basados en Debian, ya que es en el que me encuentro al momento de escribir esto (Pop OS).

    1. Eliminar instalaciones previas de Docker

    ```bash
    sudo apt remove docker docker-engine docker.io containerd runc
    ```

    2. Actualizar paquetes de apt

    ```bash
    sudo apt update
    ```

    3. Habilitar HTTPS para apt

    ```bash
    sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
    ```

    4. Agregar llave de identificaci&oacute;n de docker

    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
    | sudo apt-key add - \
    && sudo apt-key fingerprint 0EBFCD88
    ```

    5. Agregar el release estable al manejador de paquetes

    ```bash
    sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
    ```

    6. Instalar la versi&oacute;n estable de docker

    ```bash
    sudo apt update && sudo apt-get install docker-ce docker-ce-cli containerd.io
    ```

    7. Verificar instalaci&oacute;n

    ```bash
    sudo docker run hello-world
    ```

    8. Agregar tu usuario al grupo de docker (opcional)

    Por defecto, docker solo se puede usar con permisos de usuario root. Para agregar nuestro usuario al grupo de docker debemos ejecutar los siguientes comandos:

    ```bash
    sudo groupadd docker
    ```

    ```bash
    sudo usermod -aG docker $USER
    ```

    ```bash
    newgpr docker
    ```

- ### Gr&aacute;ficas

Aqu&iacute; la lista de herramientas que no puden faltar:

- Visual Studio Code.
- Google Chrome.
- Discord
