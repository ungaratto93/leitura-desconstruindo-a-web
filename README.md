# leitura-desconstruindo-a-web

Comandos por capítulo

<h2>Capítulo 1</h2>

<h6>Ver quantos processos foram criados do chrome para requisicao:
</h6>
  <code>
➜ ps xufa | grep [c]hromium | wc -l 19
</code>

<h2>Capítulo 2</h2>

<h6>Utilizando funcao getaddrinfo:
</h6>
  <code>
    ➜ python3 -c 'import socket;print(socket.getaddrinfo("desconstruindoaweb.com.br", "http"))'
  </code>

<h2>Capítulo 3</h2>
<p>Consulta o dns</p>
<p>
  <code>➜ dig desconstruindoaweb.com.br</code>
</p>
<p>
  <code>➜ dig ungaratto93.github.io</code>
</p>

<p>Listando os processos do chrome</p>
<p>
  <code>➜ ps aux | grep 'google'</code>
</p>
<p>
  <code>❯ ps aux | grep 'opt/google/chrome/chrome --'</code>
</p

<p>Usando strace para observar syscall usadas no pid (Process Identifiers) do chrome para por fim atribuir a sockets </p>
<p>
  <code>➜ sudo strace -f -e socket,connect -p 10036</code>
</p>

<p>Observando o caminho para resolucao do dns</p>
<p><code>➜ dnstracer -s . -4 -o desconstruindoaweb.com.br</code></p>

<h2>Capitulo 4</h2>
<p>Executando telnet e recuperando conteudo textual da pagina</p>
<p>
  <code>
telnet www.google.com 80
  </code>
  <br>
<code>
GET / HTTP/1.1
  
HOST: www.google.com</code>
</p>

<h2>Capitulo 5</h2>
<p>Verificando os certificados instalados no SO</p>
<p><code>➜ ls /etc/ssl/certs/
</code></p>
<br>
<p>Testando a conexao https manualmente</p>
<p><code>openssl s_client -connect desconstruindoaweb.com.br:443</code></p>

<h2>Capitulo 6</h2>
<p>Descobrindo quais partes da ethernet estamos usando</p>
<p>
  <code>sudo ethtool eno1</code>
</p>
<br>
<p>Listando o dispositivo utilizado para conectar na rede wireless</p>
<p><code>➜ lsusb | grep -i wi</code></p>
<br>
<p>Procurando por modulos que implementem a funcionalidade do hardware</p>
<p>
<code>
➜ lsmod | grep -i 818
</code>
</p>
<br>
<p>Verificando a quantidade de redes wifi e seus canais</p>
<p><code>➜ nmcli device wifi list | grep Infra | wc -l
</code></p>
<br>
<p>Verificando os canais</p>
<p><code>➜ nmcli device wifi list | grep Infra | sed 's/.*Infra\s\+\([0-9]\
∙ +\).*/\1/g' | sort -n</code></p>
<br>
<p>Verificando quem está entre nosso dispositivo de origem e o dispositivo destino</p>
<p><code>sudo traceroute -q 1 -T desconstruindoaweb.com.br</code></p>
<h2>Capitulo 7</h2>
<p>Acompanhando os processos do nginx</p>
<p><code>strace -f nginx</code></p>
<br>
<p>Observando os processos em execucao</p>
<p><code>ps fexa -o pid,cmd | grep "[n]ginx:"</code></p>
