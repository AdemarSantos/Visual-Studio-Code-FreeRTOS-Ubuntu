# Guia de Instalação e Configuração do FreeRTOS e VSCode no Ubuntu

## Recursos e Links Úteis

- **Vídeo de Referência**: [Configuração do FreeRTOS no Ubuntu](https://www.youtube.com/watch?v=wZmXPj1YvBg)
- **Site para baixar FreeRTOS**: [FreeRTOS Official](https://freertos.org)
  - Baixe a versão `.deb` conforme indicado na imagem.
- **Site para baixar Visual Studio Code**: [VSCode Official](https://code.visualstudio.com/)
  - Baixe a versão `.deb` conforme indicado na imagem.

## Dicas de Terminal

- `pwd` - Exibe o diretório atual.
- `ls` - Lista os arquivos no diretório atual.
- `cd <Destino>/` - Navega para um diretório específico.
- `mv <nome_do_arquivo> <Destino>/` - Move o arquivo.
- `unzip <nome_do_arquivo>` - Extrai o arquivo.
- `Ctrl+l` - Limpa a tela do terminal.
- `Ctrl+Shift+c` - Copia.
- `Ctrl+Shift+v` - Cola.
- `Ctrl+Alt+t` - Abre o terminal.

Lembre-se da diferenciação entre maiúsculas e minúsculas e confirme as instalações com 'Y+Enter' ou 'Enter'.

## 1. Descompactando e instalando arquivos

```bash
# Abra o terminal
# Instale meta pacotes fundamentais para compilação
sudo apt install build-essential

# Acesse os arquivos baixados em Downloads
cd Downloads

# Liste os arquivos
ls

# Instale o Visual Studio Code
sudo dpkg -i <nome do arquivo .deb do VSCode>

# Descompacte o FreeRTOS
unzip <nome do arquivo .zip do FreeRTOS>

# Mova a pasta do FreeRTOS para a pasta Home
mv <nome da pasta FreeRTOS> ~/

# Instale o Git
sudo apt install git

# Configure a variável de ambiente para o FreeRTOS
export FREERTOS_PATH=~/<nome da pasta FreeRTOS>

# Para manter a configuração após reiniciar, adicione ao .profile
cd
nano .profile
# Cole `export FREERTOS_PATH=~/<nome da pasta FreeRTOS>` no fim do arquivo
# Salve com 'Ctrl+x', 'y', 'Enter'
# Para testar, execute:
source .profile
# Inicie o VSCode via terminal
code

# Clone o repositório
# No VSCode, selecione 'Clone Git Repository' e cole o link do repositório
https://github.com/vsserafim/twotasks-posix-gcc.git

# Crie uma pasta sem espaços para os projetos, por exemplo:
mkdir ~/Documentos/Projetos_FreeRTOS

# Abra a pasta clonada
cd ~/Documentos/Projetos_FreeRTOS/twotasks-posix-gcc

# Instale extensões necessárias de C e C++
# Abra o arquivo 'main' e execute a tarefa de build com 'ctrl+shift+b'

# Para executar o programa, use:
cd build
./modelo-posix-gcc
