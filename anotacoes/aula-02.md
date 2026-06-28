# Aula 02 - Primeiros comandos do Terminal Linux

> **Data:** 26/06/2026

## Objetivo da aula

Nesta aula comecei a utilizar o terminal Linux, aprendendo comandos básicos para navegação, monitoramento do sistema e gerenciamento de pacotes.

---

# Monitoramento do sistema

## top

Mostra os processos que estão sendo executados em tempo real, além do consumo de CPU, memória e outros recursos do sistema.

**Observação**

Se algum processo aparecer com a letra **Z** (Zombie), significa que ele terminou sua execução, porém ainda não foi totalmente removido da memória pelo sistema. Esse processo praticamente não consome recursos, mas ainda permanece registrado até que seu processo "pai" o finalize.

---

## top + 1

Mostra o uso da CPU separado por cada núcleo do processador.

---

## Shift + E

Dentro do comando `top`, altera a unidade de medida da memória (KB, MB, GB, etc.).

---

## htop

Versão mais moderna e interativa do comando `top`, facilitando a visualização dos processos do sistema.

---

# Informações do sistema

## dmesg

Exibe as mensagens registradas pelo **Kernel** desde a inicialização do computador.

### O que é o Kernel?

O **Kernel** é o núcleo do sistema operacional Linux.

Ele faz a comunicação entre o hardware (processador, memória, disco, placa de vídeo, teclado etc.) e os programas que estão sendo executados.

Sempre que algum dispositivo é ligado, removido ou apresenta algum erro, o Kernel registra essa informação.

Por isso, o comando `dmesg` é muito utilizado para diagnosticar problemas de hardware.

---

## dmesg | grep

Filtra as mensagens do Kernel para localizar apenas informações específicas.

**Exemplos:**

```bash
dmesg | grep usb
```

Mostra apenas informações relacionadas às portas USB.

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

---

# Espaço em disco

## df -h

Mostra quanto espaço está sendo utilizado e quanto ainda está disponível nos discos, utilizando um formato fácil de ler (KB, MB, GB).

---

# Gerenciamento de pacotes

## sudo

Executa um comando com permissões de administrador (SuperUser).

---

## apt

Gerenciador de pacotes utilizado no Ubuntu e Debian para instalar, remover e atualizar programas.

---

## apt update

Atualiza a lista de programas disponíveis para instalação.

---

## apt list

Lista os pacotes instalados ou disponíveis.

---

## apt dist-upgrade

Atualiza completamente o sistema, resolvendo dependências e instalando novas versões dos pacotes.

---

# Navegação entre diretórios

## pwd

Mostra o caminho completo da pasta atual.

---

## ls

Lista os arquivos e pastas do diretório atual.

---

## ls -l

Lista os arquivos com informações detalhadas, como permissões, proprietário, tamanho e data.

---

## ls -a

Mostra todos os arquivos, incluindo os arquivos ocultos.

---

## ls -la

Combina as opções `-l` e `-a`, exibindo detalhes de todos os arquivos, inclusive os ocultos.

---

## ls -ltr

Lista os arquivos ordenados pela data de modificação.

---

## cd

Entra em uma pasta.

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

---

## info

Abre uma documentação mais detalhada de alguns comandos.

---

# Informações sobre permissões

Quando executamos:

```bash
ls -l
```

Podemos encontrar algo parecido com:

```text
drwxr-xr-x
```

### Primeira letra

- `d` → Diretório (pasta)
- `-` → Arquivo comum

### Permissões

- `r` → Read (Leitura)
- `w` → Write (Escrita)
- `x` → Execute (Execução)

### Quem possui essas permissões?

As permissões são divididas em três grupos:

- **Dono (Owner):** quem criou o arquivo.
- **Grupo (Group):** usuários pertencentes ao mesmo grupo.
- **Outros (Others):** qualquer outro usuário do sistema.

Exemplo:

```
drwxr-xr-x
```

- Dono → leitura, escrita e execução.
- Grupo → leitura e execução.
- Outros → leitura e execução.

---

# Encerramento do sistema

## sudo init 0

Desliga o computador.

Também existem outros comandos que possuem a mesma finalidade:

```bash
sudo poweroff
```

```bash
sudo shutdown now
```

```bash
systemctl poweroff
```

Todos desligam o sistema, mas atualmente `poweroff` e `shutdown` são os comandos mais utilizados.

---

# Resumo da aula

Nesta aula aprendi os primeiros comandos do terminal Linux, utilizados para monitorar processos, consultar informações do sistema, navegar entre diretórios, gerenciar pacotes e compreender como funcionam as permissões de arquivos e diretórios.
