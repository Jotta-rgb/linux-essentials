# Aula 02 - Primeiros comandos do Terminal Linux

> Data: 26/06/2026

## Objetivo da aula

Nesta aula comecei a utilizar o terminal Linux, aprendendo comandos básicos para navegação, monitoramento do sistema e gerenciamento de pacotes.

---

# Comandos estudados

## Monitoramento do sistema

### top

Mostra os processos que estão sendo executados em tempo real e o consumo de recursos do sistema.

**Observação**

Se aparecer um processo com a letra **Z (Zombie)** significa que ele já terminou sua execução, mas ainda permanece listado porque o processo pai ainda não liberou seus recursos.

---

### top + 1

Exibe o uso da CPU separado por núcleo (core).

---

### Shift + E

Dentro do comando **top**, alterna a unidade de medida da memória (KB, MB e GB).

---

### htop

Versão mais moderna e visual do comando **top**.

Possui barras gráficas e facilita o monitoramento dos processos.

---

## Informações do sistema

### dmesg

Exibe as mensagens registradas pelo **Kernel** desde que o computador foi ligado.

### O que é o Kernel?

O Kernel é o núcleo do sistema operacional Linux.

Ele é responsável por fazer a comunicação entre o hardware (processador, memória, disco, placa de rede etc.) e os programas que utilizamos.

Sempre que um dispositivo é iniciado ou ocorre algum evento importante no sistema, o Kernel registra essa informação.

---

### dmesg | grep nome

Filtra o resultado do comando **dmesg**.

Exemplos:

```bash
dmesg | grep usb
dmesg | grep disk
dmesg | grep net
```

Assim fica mais fácil encontrar apenas as informações desejadas.

---

### df -h

Mostra quanto espaço existe em cada disco.

A opção **-h** significa **human readable**, exibindo os valores em KB, MB ou GB.

---

### uname -a

Mostra informações sobre o Kernel e o sistema operacional.

---

## Gerenciamento de pacotes

### sudo

Executa um comando com privilégios de administrador (Super User).

---

### apt

Gerenciador de pacotes utilizado em distribuições como Ubuntu e Debian.

Permite instalar, remover e atualizar programas.

---

### apt update

Atualiza a lista de pacotes disponíveis.

Não instala atualizações.

---

### apt list

Lista os pacotes instalados ou disponíveis.

---

### apt dist-upgrade

Atualiza todo o sistema e resolve dependências automaticamente quando necessário.

---

## Navegação no sistema

### pwd

Mostra o caminho da pasta atual.

---

### ls

Lista os arquivos da pasta.

---

### ls -l

Lista os arquivos com detalhes.

Exibe permissões, proprietário, grupo, tamanho e data de modificação.

---

### ls -a

Mostra todos os arquivos, incluindo os ocultos.

Arquivos ocultos começam com um ponto (`.`).

---

### ls -la

Combina as opções `-l` e `-a`.

Mostra arquivos ocultos com informações detalhadas.

---

### ls -ltr

Lista os arquivos ordenados pela data de modificação.

Os arquivos mais recentes aparecem ao final da lista.

---

### cd

Entra em um diretório.

---

### cd ..

Volta para a pasta anterior.

---

### cd -

Retorna para o último diretório acessado.

---

## Ajuda

### man comando

Abre o manual oficial de um comando.

Exemplo:

```bash
man ls
```

---

### info comando

Exibe uma documentação mais completa que o comando `man` em alguns programas.

---

## Desligamento do sistema

### sudo init 0

Desliga o sistema operacional.

### Outros comandos modernos

```bash
sudo poweroff
```

Desliga imediatamente.

```bash
sudo shutdown now
```

Desliga o computador imediatamente.

```bash
sudo shutdown -h +10
```

Agenda o desligamento para 10 minutos.

---

# Permissões no Linux

Quando executamos:

```bash
ls -l
```

Podemos encontrar algo semelhante a:

```text
drwxr-xr-x
```

## Primeira letra

| Símbolo | Significado |
|---------|-------------|
| d | Diretório (pasta) |
| - | Arquivo comum |

---

## Permissões

| Letra | Significado |
|--------|-------------|
| r | Leitura (Read) |
| w | Escrita (Write) |
| x | Execução (Execute) |

---

## Quem possui essas permissões?

As permissões são divididas em três grupos:

### Dono (Owner)

É quem criou o arquivo.

---

### Grupo (Group)

Usuários pertencentes ao mesmo grupo.

---

### Outros (Others)

Todos os demais usuários do sistema.

---

## Exemplo

```
drwxr-xr-x
```

Significa:

- O dono pode ler, escrever e executar.
- O grupo pode ler e executar.
- Os outros usuários também podem ler e executar.

Como não possuem a permissão **w**, não podem alterar ou apagar o arquivo.

---

# Resumo

Nesta aula aprendi:

- Navegação entre diretórios.
- Listagem de arquivos.
- Monitoramento de processos.
- Visualização de informações do sistema.
- Gerenciamento de pacotes.
- Uso do sudo.
- Conceito de Kernel.
- Estrutura das permissões do Linux.
