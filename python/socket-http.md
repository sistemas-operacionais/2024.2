# Tutorial: Criando um Servidor TCP Simples em Python

## Informações gerais
- **Público alvo**: alunos da disciplina de SO (Sistemas Operacionais) do curso de TADS (Superior em Tecnologia em Análise e Desenvolvimento de Sistemas) no CNAT-IFRN (Instituto Federal de Educação, Ciência e Tecnologia do Rio Grande do Norte - Campus Natal-Central).
- disciplina: **SO** Sistemas Operacionais
- professor: [Leonardo A. Minora](https://github.com/leonardo-minora)
- texto gerado pelo [Microsoft Copilot](https://copilot.microsoft.com/)

## Experimento 1
1. executar o servidor http, código abaixo
2. executar cliente, código abaixo
   1. apenas 1 cliente
   2. 2 clientes simultâneos
   3. 5 clientes simultâneos
   4. 10 cliente simultâneos
3. analizar e explicar o comportamento do cliente e do servidor para cada um dos 4 casos acima

**data da entrega** 13/02/2025

**código servidor**
```python
import http.server
import socketserver
from socketserver import ThreadingMixIn

# Definir o conteúdo HTML fixo
html_fixo = """
<!DOCTYPE html>
<html>
<head>
    <title>Servidor HTTP Multithread</title>
</head>
<body>
    <h1>Olá, mundo!</h1>
    <p>Este é um servidor HTTP multithread em Python.</p>
</body>
</html>
"""

class MeuManipulador(http.server.SimpleHTTPRequestHandler):
    def do_GET(self):
        # Imprimir informações da requisição no console
        print(f"Requisição recebida de: {self.client_address}")
        print(f"Caminho solicitado: {self.path}")
        print("Cabeçalhos da requisição:")
        for nome, valor in self.headers.items():
            print(f"{nome}: {valor}")

        # Enviar resposta de código 200
        self.send_response(200)
        self.send_header("Content-type", "text/html")
        self.end_headers()
        # Enviar o conteúdo HTML fixo
        self.wfile.write(html_fixo.encode("utf-8"))

class ThreadingHTTPServer(ThreadingMixIn, http.server.HTTPServer):
    """Servidor HTTP que trata cada requisição em uma nova thread."""
    daemon_threads = True

# Definir o endereço e a porta do servidor
endereco = ("", 8000)

# Criar o servidor
with ThreadingHTTPServer(endereco, MeuManipulador) as httpd:
    print("Servidor HTTP multithread rodando na porta 8000...")
    # Manter o servidor rodando
    httpd.serve_forever()

```


**código cliente**
```python
import http.client

def fazer_requisicao_get():
    # Conectar ao servidor localhost na porta 8000
    conexao = http.client.HTTPConnection("localhost", 8000)

    # Fazer a requisição GET
    conexao.request("GET", "/")

    # Obter a resposta
    resposta = conexao.getresponse()

    # Ler o conteúdo da resposta
    conteudo = resposta.read()

    # Imprimir o status e o conteúdo da resposta
    print(f"Status: {resposta.status}")
    print(f"Motivo: {resposta.reason}")
    print("Conteúdo:")
    print(conteudo.decode("utf-8"))

    # Fechar a conexão
    conexao.close()

# Chamar a função para fazer a requisição GET
fazer_requisicao_get()

```