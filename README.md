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
