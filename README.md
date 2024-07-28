# Configuração da Instância EC2 e Volume EBS
---
Este documento descreve o processo de configuração de uma instância EC2 na AWS, a criação e o gerenciamento de um volume EBS, e a realização de operações básicas de armazenamento.

## 1. Configuração da Instância EC2

1. Acesse o Console da AWS e navegue até o serviço EC2.
2. Crie uma nova instância EC2 usando a imagem **Amazon Linux 2**.
3. Escolha o tipo de instância de acordo com suas necessidades de recursos.

## 2. Conexão via SSH

1. Após a instância ser criada, use a chave privada para conectar via SSH. O comando utilizado foi:
   ```bash
   ssh -i /caminho/para/minha_chave.pem ec2-user@<endereço_ip_da_instância>
   ```
2. Execute os comandos necessários para acessar o terminal da instância.

## 3. Gerenciando o Armazenamento

1. Explore as opções de armazenamento oferecidas pelo Amazon EC2.
2. Crie um novo volume **Elastic Block Store (EBS)** com um tamanho de sua escolha. (Por exemplo, 8 GB)
3. Anexe o volume à sua instância EC2.

## 4. Formatando e Montando o Volume

Formate o volume recém-criado usando um sistema de arquivos ext4:
   ```bash
   sudo mkfs -t ext4 /dev/xvdf
   ```
   **Observação:** Substitua `/dev/xvdf` pelo nome do seu volume, se necessário.

## 5. Criação de Arquivos

1. Acesse o diretório montado:
   ```bash
   cd /mnt/
   ```
   
2. Crie um arquivo de texto simples usando o editor de sua preferência (por exemplo, `nano`):
   ```bash
   sudo nano meu_arquivo.txt
   ```
   
3. Adicione conteúdo ao arquivo e salve-o.

## 6. Explorando Recursos

Utilize os seguintes comandos para verificar o status do volume montado, o espaço em disco disponível e o conteúdo do arquivo criado:
   - Listar arquivos no diretório:
     ```bash
     ls /mnt
     ```
   - Verificar espaço em disco:
     ```bash
     df -h
     ```
   - Verificar o ponto de montagem:
     ```bash
     mount
     ```
   - Visualizar o conteúdo do arquivo:
     ```bash
     cat meu_arquivo.txt
     ```
   

## Conclusão

Este exercício demonstrou como configurar uma instância EC2, gerenciar volumes EBS e realizar operações básicas de armazenamento. Para qualquer dúvida ou suporte adicional, consulte a documentação oficial da AWS.

---

Sinta-se à vontade para editar ou adicionar mais informações conforme necessário. Se precisar de mais alguma coisa, estou aqui para ajudar!
