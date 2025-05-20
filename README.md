# Exemplo para documentações
Exemplo de estrutura para futuras documentações tecnicas, visando uma melhor clareza sintatica e diagramação adaptada para tecnicos e não tecnicos.

## Primeiro passo
Blocos de codigos com markdown são muito uteis para facil verificação, **copia e compartilhamento de codigo**, criando um melhor ambiente para *engenharia de infra ou de software* revisar e compartilhar o conhecimento. <sup>[2]</sup>

- Exemplo de código de um produtor de mensageria em kafka
```
from kafka import KafkaProducer
import json

producer = KafkaProducer(
    bootstrap_servers='localhost:9092',
    value_serializer=lambda v: json.dumps(v).encode('utf-8')
)

def enviar_dados(nome, email):
    dados = {"nome": nome, "email": email}
    producer.send('entrada-dados', value=dados)
    print(f"Dados enviados: {dados}")

# Exemplo de envio
enviar_dados("João Silva", "joao@example.com")
enviar_dados("Maria Oliveira", "maria@example.com")

producer.flush()
```
- É interessante deixar em evidencia alguma coisa que gostaria de deixar mais explicito no codigo, referenciando a linguagem que esta usando dentro as "aspas".<sup>[1]</sup>

```hcl
# Definiçaõ do provider
provider "aws" {
  region = "us-east-1"
}
# Definição do serviço ( resource ) que será usado
resource "aws_instance" "exemplo_ec2" {
  ami           = "ami-0c94855ba95c71c99"  # Ubuntu 18.04 LTS em us-east-1 (verifique a AMI atualizada)
  instance_type = "t2.micro"

# Tag opcional para provisionamento
  tags = {
    Name = "InstanciaExemplo"
  }
}
```



- Usando o  "" img width="300px" src=url "" eu posso subir alguma imagem, e alterar seu tamanho e formatação

 <img width="300px" src="https://github.com/user-attachments/assets/7dd9ff88-3c2e-48b4-9f70-7111f9f26439" />


# Tratamento de erro

- Podemos usar tambem além de codigos, erros gerados pelos compiladores, fazer algum tipo de comentario para solução é diferenciar as abordagens de forma visual e pratica.

```bash
$ ./instalar_webserver.sh
Iniciando instalação do servidor web fictício...
Verificando dependências...
Erro: Dependência ausente: libhttpcore
Abortando instalação do servidor.
```
> Exemplo de comentario para o erro desse webserver: 
> O script usa dpkg -s para verificar se o pacote libhttpcore está instalado (isso é apenas um exemplo fictício).
> Se o pacote não estiver instalado, o script mostra um erro e finaliza com exit 1

# Blocos e emojis

- Criação de blocos e emojis podem deixar certas infromações mais aprosentaveis.

| Nome | Serviço | Função |
| ---  | --- | --- | 
| Nuvem | :cloud: | :fire: |


# Referências

_Podemos melhorar a sintaxe dos links e tambem criar numeração para referenciar autores e encurtar links_
- [Sintaxe basica e formatos de escrita no guthub](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) <sup>[1]</sup>
- https://sesamedisk.com/using-terraform-to-create-aws-resources-with-dependencies/ <sup>[2]</sup>
  


