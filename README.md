# python_development_environment-
Configurando um ambiente de desenvolvimento python Pyenv + virtualenv + zsh + ohmyzsh no Ubuntu 20.04

### Pyenv
É um gerenciador de versões de Python, ele facilita a instalação de multiplas versões de python no seu ambiente de desenvolvimento.

#### virtualenv
Permite criar multiplos ambientes virtuais no seu ambiente de desenvolvimento.

Antes de iniciar a instalação prepare o ambiente instalando os seguintes pacotes:

```
sudo apt install --no-install-recommends \
  make build-essential libssl-dev zlib1g-dev \
  libbz2-dev libreadline-dev libsqlite3-dev \
  wget curl llvm libncurses5-dev xz-utils \
  tk-dev libxml2-dev libxmlsec1-dev libffi-dev \
  liblzma-dev gcc libreadline8 python3-tk tk-dev
```

#### ZSH + Oh My Zsh
Opcionalmente instale o zsh e o Oh My Zsh:

Primeiro instale a fonte powerline:
```
sudo apt-get install -y fonts-powerline
```
Em seguida siga as instruções dos links abaixo:

[Instale o ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)

[Instale Oh My ZSH](https://github.com/ohmyzsh/ohmyzsh)

### Instalação do pyenv:
	
```
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

Opcional:
```  
cd ~/.pyenv && src/configure && make -C src
```

Após a instalação adicione algumas linhas: 

No arquivo ~/.zprofile adicione:
```
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
```
	
No arquivo ~/.profile adicione:
```
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
```

No arquivo ~/.zshrc adicione:
```
eval "$(pyenv init -)"
```

### Instalação do pyenv-virtualenv:
```
git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv
```

Após a instalação do pyenv-virtualenv, adicione a seguinte linha no final do arquivo ~/.zshrc
```
eval "$(pyenv virtualenv-init -)"
```

Agora seu ambiente de desenvolvimento Python está pronto para ser usado.


