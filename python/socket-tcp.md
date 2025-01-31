# Tutorial: Criando um Servidor TCP Simples em Python


## Sumário
1. Socket server
2. Socket cliente
3. Links
   
### 1. Socket server
Este tutorial explica como criar um servidor TCP simples em Python usando o módulo `socketserver`. O servidor recebe dados de um cliente, imprime os dados recebidos no console e envia de volta os dados em letras maiúsculas.

#### Passo 1: Importar o Módulo `socketserver`

Primeiro, importamos o módulo `socketserver`, que fornece classes para criar servidores de rede.

```python
import socketserver
```

#### Passo 2: Criar a Classe Manipuladora de Requisições

Criamos uma classe `MyTCPHandler` que herda de `socketserver.BaseRequestHandler`. Esta classe será instanciada uma vez por conexão ao servidor e deve sobrescrever o método `handle()` para implementar a comunicação com o cliente.

```python
class MyTCPHandler(socketserver.BaseRequestHandler):
    """
    A classe manipuladora de requisições para nosso servidor.

    Ela é instanciada uma vez por conexão ao servidor e deve
    sobrescrever o método handle() para implementar a comunicação
    com o cliente.
    """

    def handle(self):
        # self.request é o socket TCP conectado ao cliente
        self.data = self.request.recv(1024).strip()
        print("Recebido de {}:".format(self.client_address[0]))
        print(self.data)
        # apenas envia de volta os mesmos dados, mas em maiúsculas
        self.request.sendall(self.data.upper())
```

- **`handle(self)`**: Este método é chamado para tratar a requisição do cliente.
  - `self.request.recv(1024).strip()`: Recebe até 1024 bytes de dados do cliente e remove espaços em branco nas extremidades.
  - `print("Recebido de {}:".format(self.client_address[0]))`: Imprime o endereço IP do cliente.
  - `print(self.data)`: Imprime os dados recebidos.
  - `self.request.sendall(self.data.upper())`: Envia de volta os dados recebidos, mas em letras maiúsculas.

#### Passo 3: Configurar e Iniciar o Servidor

No bloco `if __name__ == "__main__":`, configuramos o servidor para escutar em um endereço e porta específicos e o iniciamos.

```python
if __name__ == "__main__":
    HOST, PORT = "10.25.2.25", 80

    # Criar o servidor, vinculando ao endereço e porta especificados
    with socketserver.TCPServer((HOST, PORT), MyTCPHandler) as server:
        # Ativar o servidor; isso manterá o servidor rodando até que
        # você interrompa o programa com Ctrl-C
        server.serve_forever()
```

- **`HOST, PORT = "10.25.2.25", 80`**: Define o endereço IP e a porta em que o servidor escutará.
- **`with socketserver.TCPServer((HOST, PORT), MyTCPHandler) as server:`**: Cria uma instância de `TCPServer`, vinculando ao endereço e porta especificados e usando `MyTCPHandler` para tratar as requisições.
- **`server.serve_forever()`**: Mantém o servidor rodando indefinidamente, tratando requisições de clientes até que o programa seja interrompido.

## 2. Socket cliente


## 3. Links
- [socketserver — A framework for network servers](https://docs.python.org/3/library/socketserver.html)
