# Aula 02 - Primeiros Comandos do Terminal Linux

> **Data:** 26/06/2026

---

# Objetivo da aula

Nesta aula comecei a utilizar o terminal Linux, aprendendo comandos para monitoramento do sistema, consulta de informações, navegação entre diretórios, gerenciamento de pacotes e permissões de arquivos.

---

# Comandos estudados

# Monitoramento do sistema

## top

Mostra os processos que estão sendo executados em tempo real, além do consumo de recursos como CPU e memória.

É um dos comandos mais utilizados por administradores de sistemas para verificar o funcionamento do computador.

### Observação

Se aparecer a letra **Z** (Zombie) na coluna de estado de um processo, significa que aquele processo já terminou sua execução, porém seu processo "pai" ainda não removeu seu registro da tabela de processos.

Esse tipo de processo praticamente não utiliza memória nem CPU, sendo apenas um registro temporário.

---

## top + 1

Mostra o uso da CPU separado por cada núcleo (core) do processador.

Facilita a identificação de qual núcleo está sendo mais utilizado.

---

## Shift + E

Dentro do comando `top`, altera a unidade utilizada para mostrar o consumo de memória.

Exemplo:

- KB
- MB
- GB

---

## htop

Versão mais moderna e visual do comando `top`.

Possui uma interface mais amigável, com barras de utilização de CPU, memória e lista de processos.

---

# Informações do sistema

## dmesg

Exibe todas as mensagens registradas pelo **Kernel** desde que o computador foi ligado.

Essas mensagens mostram tudo o que aconteceu durante a inicialização do sistema e durante o funcionamento do hardware.

É muito utilizado para diagnosticar problemas em dispositivos como:

- HD ou SSD
- Pendrive
- Mouse
- Teclado
- Placa de rede
- Placa de vídeo
- USB

---

## O que é o Kernel?

O **Kernel** é o núcleo do sistema operacional Linux.

Ele é responsável por fazer a comunicação entre o hardware e os programas.

Sempre que um programa precisa utilizar algum componente físico do computador, como processador, memória ou disco, ele solicita essa ação ao Kernel.

O Kernel controla:

- Processador
- Memória RAM
- Disco
- Placa de vídeo
- USB
- Rede
- Drivers

Sem o Kernel, o sistema operacional não conseguiria controlar o hardware do computador.

---

## dmesg | grep

Permite filtrar as mensagens do Kernel para encontrar apenas aquilo que você procura.

### Exemplos

```bash
dmesg | grep usb
```

Mostra apenas mensagens relacionadas às portas USB.

```bash
dmesg | grep disk
```

Mostra mensagens relacionadas aos discos.

```bash
dmesg | grep net
```

Mostra mensagens relacionadas à rede.

---

## uname -a

Mostra informações completas sobre o Kernel e o sistema operacional.

Exibe informações como:

- Nome do sistema
- Versão do Kernel
- Arquitetura
- Nome da máquina

---

# Espaço em disco

## df -h

Mostra quanto espaço existe nos discos do computador.

A opção `-h` significa **Human Readable**, ou seja, apresenta os tamanhos em um formato mais fácil de entender (MB, GB e TB).

---

# Gerenciamento de pacotes

## sudo

Executa um comando com permissões de administrador.

A palavra **sudo** significa:

> Super User Do

Ou seja:

"Execute este comando como administrador."

---

## apt

É o gerenciador de pacotes utilizado nas distribuições Ubuntu e Debian.

Com ele é possível:

- Instalar programas
- Remover programas
- Atualizar programas

---

## apt update

Atualiza a lista de programas disponíveis nos repositórios.

Não instala atualizações, apenas verifica quais versões novas existem.

---

## apt list

Lista todos os pacotes instalados ou disponíveis.

---

## apt dist-upgrade

Atualiza completamente o sistema operacional.

Além de instalar versões mais recentes, também resolve dependências e pode instalar ou remover pacotes quando necessário.

---

# Navegação entre diretórios

## pwd

Mostra o caminho completo da pasta atual.

Exemplo:

```text
/home/joao/Documentos
```

---

## ls

Lista os arquivos e pastas do diretório atual.

---

## ls -l

Lista os arquivos com informações detalhadas.

Mostra:

- Permissões
- Dono
- Grupo
- Tamanho
- Data
- Nome

---

## ls -a

Lista todos os arquivos, inclusive os ocultos.

Arquivos ocultos normalmente começam com um ponto (`.`).

Exemplo:

```text
.bashrc
.profile
```

---

## ls -la

Combina as opções `-l` e `-a`.

Mostra detalhes de todos os arquivos, inclusive os ocultos.

---

## ls -ltr

Lista os arquivos ordenados pela data de modificação.

---

## cd

Entra em uma pasta.

Exemplo:

```bash
cd Documentos
```

---

## cd ..

Volta para a pasta anterior.

---

## cd -

Retorna para o último diretório acessado.

---

# Ajuda

## man

Abre o manual de um comando.

Exemplo:

```bash
man ls
```

Cada comando do Linux possui sua própria página de manual.

---

## info

Mostra uma documentação mais detalhada que o `man` para alguns programas.

---

# Permissões de arquivos

Quando executamos:

```bash
ls -l
```

Podemos encontrar algo parecido com:

```text
drwxr-xr-x
```

## Primeira letra

Ela identifica o tipo do arquivo.

- `d` → Diretório (pasta)
- `-` → Arquivo comum

---

## O significado das letras

- `r` → Read (Leitura)
- `w` → Write (Escrita)
- `x` → Execute (Execução)

---

## Quem possui essas permissões?

As permissões são divididas em três grupos.

### Owner (Dono)

É quem criou o arquivo.

Normalmente possui controle total.

---

### Group (Grupo)

Usuários que pertencem ao mesmo grupo do arquivo.

---

### Others (Outros)

Qualquer outro usuário do sistema.

---

## Exemplo

```text
drwxr-xr-x
```

Significa:

**Owner**

- Leitura ✅
- Escrita ✅
- Execução ✅

**Group**

- Leitura ✅
- Execução ✅

**Others**

- Leitura ✅
- Execução ✅

Como não existe a letra **w** para Grupo e Others, eles não podem alterar nem excluir esse diretório.

---

# Encerramento do sistema

## sudo init 0

Desliga o computador.

Também é possível utilizar:

```bash
sudo poweroff
```

```bash
sudo shutdown now
```

```bash
systemctl poweroff
```

Todos possuem a mesma finalidade: desligar o sistema.

Atualmente, `poweroff` e `shutdown` são os comandos mais utilizados.

---

# Resumo da aula

Nesta aula tive meu primeiro contato com o terminal Linux, aprendendo comandos para monitoramento do sistema, consulta de informações, gerenciamento de pacotes, navegação entre diretórios e permissões de arquivos.

Também compreendi a função do Kernel, a importância do comando `dmesg` para diagnóstico do sistema e como utilizar o terminal para administrar um ambiente Linux de forma mais eficiente.
