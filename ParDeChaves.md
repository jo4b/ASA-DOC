# Gerar um par de chaves ssh
1 - Gerar uma nova chave SSH
Abra Terminal.

2 - Cole o texto abaixo:
```markdown

$ ssh-keygen -t ed25519 
```
### Adicionar sua chave SSH ao ssh-agent
Antes de adicionar uma nova chave SSH ao agente para gerenciar suas chaves, você deve verificar as chaves SSH existentes e gerado uma nova chave SSH.
Inicie o ssh-agent em segundo plano.
```mardown
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```
Adicione sua chave SSH privada ao **ssh-agent**. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.
```markdown
$ ssh-add ~/.ssh/id_ed25519
```
### Adicionar sua chave privado ao serviço ssh
```markdown
$ ssh-copy-id SERVIÇO
```
