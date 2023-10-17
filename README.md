# aula-nginx

### Instalacao ubuntu

$ sudo apt install nginx
 sudo systemctl status nginx
 sudo nginx -s stop
nginx -h


### Docker

docker run -v /data/www/:/usr/share/nginx/ -v /data/conf/nginx.conf:/etc/nginx/nginx.conf -p 80:80 -d nginx

### Principais arquivos

worker_processes: Define o número de processos de trabalho (workers) que o Nginx utilizará para manipular solicitações. Neste exemplo, está configurado com apenas um processo.

events: Especifica configurações relacionadas ao modelo de eventos do Nginx, que controla a maneira como o servidor lida com conexões e solicitações.

worker_connections: Define o número máximo de conexões simultâneas que um único processo de trabalho pode tratar. Neste caso, é definido como 1024.
http: Define as configurações gerais do servidor web HTTP.

include mime.types: Inclui um arquivo que define os tipos MIME para o servidor. Isso é importante para a definição dos tipos de conteúdo servidos.

default_type: Define o tipo MIME padrão que será enviado para o navegador se não for especificado em uma resposta HTTP. Neste caso, é application/octet-stream.

sendfile: Ativa o uso da função de envio de arquivos do sistema operacional para entregar arquivos estáticos de maneira mais eficiente.

keepalive_timeout: Define o tempo máximo que uma conexão pode permanecer aberta em segundos. Após esse período de inatividade, a conexão será encerrada.

server: Define as configurações para um servidor virtual (server block).

listen 80: Especifica a porta na qual o servidor deve escutar. Neste caso, ele escuta na porta 80, que é a porta padrão para solicitações HTTP.

server_name localhost: Define o nome do servidor, que é usado para determinar qual servidor virtual deve manipular uma solicitação com base no nome do host na solicitação.

location /: Define as configurações para uma localização específica. Neste caso, é a raiz do servidor.

root /usr/share/nginx/html: Especifica o diretório raiz onde os arquivos estão localizados.

index index.html: Define o arquivo padrão a ser servido quando um diretório é acessado. Neste caso, index.html.